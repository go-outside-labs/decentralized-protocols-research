## ⛓🫱🏻‍🫲🏽 zero-knowledge proofs notes and resources

<br>

<p align="center">
<img src="https://user-images.githubusercontent.com/1130416/234397705-090a0c7b-5d96-49f8-8eaa-183297e3fe37.png" width="50%" align="center" style="padding:1px;border:1px solid black;"/>

<br>
<br>

### tl; dr



* **zero-knowledge proofs** represent **programs as circuits**, where a **prover** generates a proof from public and private inputs, and a **verifier** computes that the output if the statement is correct (without any information regarding the private input).


* three fundamental characteristics define a ZKP:
  * completeness (if a statement is true, then an honest verifier can be convinced by an honest prover that they possess knowledge about the correct input),
  * soundness (if a statement is false, then no dishonest prover can unilaterally convince an honest verifier that they have knowledge about the correct input), and
  * zero-knowledge (if the state is true, then the verifier learns nothing more from the prover other than that).

* zk proofs use cases:
  * **private transactions**: blockchains such as zcash, with privacy-preserving txs.
  * **verifiable computations**: decentralized oracle networks, providing smart contracts with access to off-chain data.
  * **highly-scalable and secure l2s**: verifiable computations through methods such as zk-rollups, validiums, and volition by they use l1s as a settlement layer.
  * **decentralized identity and authentication**: zkps can underpin identity management systems to enable users to validate their identity.



<br>

---

### in this dir

<br>

* **[zk-EVMs](zkEVM)**
* **[number theory](number_theory)**
* **[proof systems](proofs)**
* **[cryptographic primitives](primitives)**
* **[machine learning](applications/ml.md)**
* **[privacy-enhancing technologies](applications/privacy_enhancing_technologies.md)**
* **[incomplete catalog of zkp projects](applications/zkp_projects.md)**


<br>

----


### external resources

<br>

* **[0xparc on circom](https://learn.0xparc.org/circom/)**
* **[0xparc on halo2](https://learn.0xparc.org/halo2/)**
* **[zk-learnng](https://zk-learning.org/)**
* **[zkiap](https://zkiap.com/)**
* **[pse's mirror](https://mirror.xyz/privacy-scaling-explorations.eth)**
* **[zero knowledge postcast youtube](https://www.youtube.com/@zeroknowledgefm)**
* **[rollups are not real, by jon charbonneau](https://joncharbonneau.substack.com/p/rollups-arent-real)**
* **[what are zk proofs, ethereum foundation](https://ethereum.org/en/zero-knowledge-proofs/)**
* **[the zk-ECDSA landscape, by pse (ethereum foundation)](https://mirror.xyz/privacy-scaling-explorations.eth/djxf2g9VzUcss1e-gWIL2DSRD4stWggtTOcgsv1RlxY)**
* **the state of zk applications in ethereum, by andyguzman.eth: [1](https://mirror.xyz/andyguzman.eth/p4nNk7Rr-2i-uZDO_lTHJEWtNv3nYt2N2z3Cwly8RHc) and [2](https://mirror.xyz/andyguzman.eth/ZZRLBlx2KjlNnQ84v1doMKg_8QO-XRjYxFfT1Fm_ZDw)**
* **[zero knowledge dapp from 0 to production, by vivian plasencia](https://vivianblog.hashnode.dev/how-to-create-a-zero-knowledge-dapp-from-zero-to-production)**
* **[an evolution of models for zkps, with sarah meiklejohn](https://youtube.com/watch?v=HO97kVMI3SE&t=2s)**
* **[an incomplete guide to folding](https://taiko.mirror.xyz/tk8LoE-rC2w0MJ4wCWwaJwbq8-Ih8DXnLUf7aJX1FbU)**


