## zkEVM

<br>

### tl; dr

<br>

* with zk proofs, zk-rollup can achieve better scalability, security, and faster finality as a scaling solution for ethereum.
* zkEVM is a scaling solution compatible with ethereum. other solutions such as zksync lite, loopring, and starknet were not evm-compatible.
* example: the bundling of txs happening within a certain period and settling the proof of a block of txs on the ethereum network instead of the full list of tx that may congest the network.
* *they use [ZK-SNARK](https://github.com/go-outside-labs/blockchains-protocol-design/blob/main/zero_knowledge_proofs/proofs/zkSNARKS.md) technology to make cryptographic proofs of execution of Ethereum-like txs, either to make it much easier to verify the Ethereum chain itself or to build ZK-rollups that are (close to) equivalent to what Ethereum provides but are much more scalable.* - vitalik

<br>

#### types

<img width="540" src="https://user-images.githubusercontent.com/1130416/234139749-4dbac8ab-d742-45f3-b920-b0b51d8698b5.png">


* type 1, fully ethereum equivalent. example: taiko and the [community zkevm by pse](https://github.com/privacy-scaling-explorations/zkevm-specs).
* type 2, fully evm equivalent: might differ on data structure and state trees. example: scroll and polygon hermez.
* type 2.5, evm-equivalent, except for gas costs (increased).
* type 3, almost evm-equivalent.
* type 4, high-level-language equivalent (compatible with smart contract languages). example: zksync.

<br>

---

### in this dir

* **[zk-rollups overview](rollups.md)**
* **[zkSync](zkSync)**
* **[starkware](starkware.md)**
* **[polygon zkEVM](polygon.md)**

<br>

----

### resources

<br>

* [the different types of zk-evms, by vitalik](https://vitalik.eth.limo/general/2022/08/04/zkevm.html)
* [l2 beat scaling](https://l2beat.com/scaling/tvl)
