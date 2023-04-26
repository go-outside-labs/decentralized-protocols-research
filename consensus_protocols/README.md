## consensus protocol and rollups

<br>

### tl; dr

<br>


* rollups move computation (and state storage) off-chain, but keep some data per tx on-chain, using compression tricks to replace data with computation whereve possible (but scalability is still limited by the data bandwidth of the underlying blockchain).

<br>

<img width="589" src="https://user-images.githubusercontent.com/1130416/234379326-901ed83c-4bc5-4c97-bad8-3b9d96dfb1b7.png">

* zk-rollups write transactions to ethereum as calldata, using compression techniques to reduce transaction data.




<br>

##### how rollups work

1. an on-chain smart contract maintains a state root (the merkle root) of the state of the rollup.
2. anyone can publish a batch (collection of txs, compressed to form the previous state root and the new state root).
3 the contract checks that the previous state root in the batch matches the current state root - if not, it switches the state root to the new state root.
4. for depositing and withdrawing, txs can have input or output outside the follupe state (processed within the batches).
5. optimistic (fraud proof) or zk (validity proof) rollups are solutions to know that the post-state roots in the batches are correct.


<br>
<img width="500" src="https://user-images.githubusercontent.com/1130416/234379163-f55493b4-7ad5-4d0d-9021-0f722cbe34a6.png">




<br>

---

### in this dir

<nr>

* **[ethereum](ethereum)**
* **[snowman](snowman)**
* **[tendermint](tendermint)**


<br>


---

### resources

<br>

* **[upgrading ethereum book, by b. edgington](https://eth2book.info/bellatrix/)**
* **[go-outside-labs eigenlayer toolkit](https://github.com/go-outside-labs/eigenlayer-toolkit)**
* **[an incomplete guide to rollups, by vitalik](https://vitalik.ca/general/2021/01/05/rollup.html)**
* **[validity rollups on bitcoin, by john light](https://bitcoinrollups.org/)**
* **[covenants, by bitcoin optech](https://bitcoinops.org/en/topics/covenants/)**
* **[shared sequencing, by expresso](https://hackmd.io/@EspressoSystems/SharedSequencing)**
* **[a rollup-centric ethereum roadmap](https://ethereum-magicians.org/t/a-rollup-centric-ethereum-roadmap/4698)**
