## 💎 modern zk proving systems

<br>

### tl; dr

<br>

* zk proofs represent programas as circuits where a prover generates a proof from public and private inputs, and the verifier computes that the output if the statement is correct (without any information regarding the private input).
* refer to “succinct proofs” instead of “zero-knowledge proofs” when the zero-knowledge property is not present.



<br>

----

### zk proofs use cases

<br>

* **private transactions**
  - blockchains such as zcash, with privacy-preserving txs
  
* **verifiable computations**
  - decentralized oracle networks, providing smart contracts with access to off-chain data
  
* **highly-scalable and secure l2s**
  - verifiable computations through methods such as zk-rollups, validiums, and volition by they use l1s as a settlement layer
  
* **decentralized identity and authentication**
  - zkps can underpin identity management systems to enable users to validate their identity

<br>

---

### in this dir

<br>

* [zk-SNARKS](zkSNARKS.md)
* [zk-STARKS](zkSTARKS.md)
* [zkEVM](zkEVM.md)
* [zkSync](zkSync.md)
* [halo2](halo2.md)
* [machine learning](ml.md)
* [privacy-enhancing technologies](privacy_enhancing_technologies.md)


<br>

---

### resources

<br>

* [what are zk proofs, ethereum foundation](https://ethereum.org/en/zero-knowledge-proofs/)
* [zero knowledge postcast youtube](https://www.youtube.com/@zeroknowledgefm)
* [the state of zk applications in ethereum, by andyguzman.eth](https://mirror.xyz/andyguzman.eth/p4nNk7Rr-2i-uZDO_lTHJEWtNv3nYt2N2z3Cwly8RHc)
* [rollups are not real, by jon charbonneau](https://joncharbonneau.substack.com/p/rollups-arent-real)


<br>


##### projects

<br>

* [ethereum foundation applied zkp team](https://appliedzkp.org/)
* [unirep, a private reputation system based on zkp](https://github.com/Unirep/Unirep)
* [axiom, zk coprocessor for ethereum](https://www.axiom.xyz/)
  - support for reads for any JSON-RPC query to an archive node, usable on-chain. This includes ZK proofs for states, transactions, and receipts.
  - support computations too large to be done on-chain.
* [risc zero, general purpose zk vm](https://www.risczero.com/)
* [sunccint, with telepathy using zkSNARKS](https://www.succinct.xyz/)


