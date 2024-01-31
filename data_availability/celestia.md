## celestia's DAS network

<br>

### tl; dr

* Celestia is a modular data availability (DA) network that scales with the number of users, by decoupling execution from consensus and introducing a new primitive, **data availability sampling** (DAS).
* Celestia DA layer consists of a PoS blockchain (celestia app), an application that provides transactions to faciliate the DA layer, and is built using Cosmos SDK.
* Rollups and L2s use Celestia as a network for publishing and making transaction DA available (Celestia can scale to the data throughput needed for millions of rollups without compromising on security).

<br>
<p align="center">
<img src="https://github.com/go-outside-labs/decentralized-protocols-research/assets/1130416/9e6e7363-de60-482d-a83a-6095f3c68b0e" width="80%" align="center" style="padding:1px;border:1px solid black;" title="Jan 7th"/>
</p>




<br>

##### data availability sampling (DAS)

* DA answers the question "has the data for this blockchain been published?".
  - Celestia solves the problem of having to download all the blockchain data by making it possible for users to verify very large blocks with data availability sampling.
  - This new primitive enables Celestia light nodes to, instead of downloading all data, download only **block headers that contain commitments** (i.e. Merkle roots) of the block data (i.e. the list of transactions).
  - To make DAs possible, Celestia uses as 2D Reed-Solomon encoding scheme to encode the block data: every block data is split into `k x k` chunks, arranged in a `k x k` matrix, and extended with parity data into a `2k x 2k` extended matrix by applying multiple times Reed-Solomon encoding.
* Celestia does not require a majority of the consensus (i.e. block producers) to be honest to guarantee data availability.
  - If the extended data is invalid, the original data might not be recoverable, even if the light nodes are sampling sufficient unique chunks.
  - As a solution, fraud proofs of incorrectly generated extended data enable light nodes to reject blocks with invalid extended data.
  - Such proofs require reconstructing the encoding and verifying the mismatch.



<br>
<p align="center">
<img src="https://github.com/go-outside-labs/decentralized-protocols-research/assets/1130416/af34dcef-230a-4fb7-b877-228ae287ec5d" width="80%" align="center" style="padding:1px;border:1px solid black;" title="Jan 7th"/>
</p>



<br>  

##### namespaced merkle trees 

* Celestia partitions the block data into **multiple namespaces**, one for every application (e.g. rollup), using the DA layer.
  - Every application needs to download only its own data and can ignore the data of other applications.
  - For this to work, the DA layer must be able to prove that the provided data is complete, i.e., all the data for a given namespace is returned.
* A NMT is a Merkle tree with the leafs ordered by the namespace identifiers and the hash function modified so that every node in the tree includes the range of namespace of all its descendants.
  - When an application requests the data for namespace 2, the DA layer must provide the data chunks D3, D4, D4, D6, and the nodes N2, N8, N7 as proof.
  - The application is able to check that the provided data is part of the block data. Furthermore, the application can verify that all the data for namespace 2 was provided. If the DA layer provides only the data chunks D4 and D5, it must also provide nodes N12 and N11 as proofs. However, the application can identify that the data is incomplete by checking the namespace range of the two nodes, i.e., both N12 and N11 have descendants part of namespace 2.


<br>
<p align="center">
<img src="https://github.com/go-outside-labs/decentralized-protocols-research/assets/1130416/9fb8fb21-c68b-4bff-9613-f87c0d17347b" width="80%" align="center" style="padding:1px;border:1px solid black;" title="Jan 7th"/>
</p>


<br>

##### building a pos blockchain for da

* Celestia-app is built on top of celestia-core, a modified version of the Tendermint consensus algorithm. It ensures:
  * the erasure coding of block data (using the 2D Reed-Solomon encoding scheme).
  * the replacement of regular Merkle tree used by Tendermint to store block data wiht a Namespaced Merkle tree that enables the above layers (execution and settlement) to only download the needed data.
* celestia-core nodes are still using the Tendermint p2p network.
* Similarly to Tendermint, celestia-core is connected to the application layer (i.e., the state machine) by ABCI++.
* The celestia-app state machine is necessary to execute the PoS logic and to enable the governance of the DA layer.
  - However, the celestia-app is data-agnostic -- the state machine neither validates nor stores the data that is made available by the celestia-app.    


<br>

##### lexicon

* **Blobs**: data is posted to Celestia's DA layer by using `MsgPayForBlobs` transactions to the core network.
* **Namespaces**: Celestia partitions the block data into multiple namespaces, one for every application. This allows applications to only download their data, and not the data of other applications.
  
<br>

---

#### references

* **[celestia docs](https://docs.celestia.org/learn/how-celestia-works/data-availability-layer#namespaced-merkle-trees-nmts)**

