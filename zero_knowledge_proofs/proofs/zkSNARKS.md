## zk-SNARKS

<br>

### tl; dr

<br>

* **zk-snarks stands for "zero-knowledge succint non-interactive argument of knowledge"**, and refers to a proof construction where one can prove possession of certain information, without revealing the information nor any interaction between the prover and verifier.
* a **"succinct" proof is one where both the size of the proof and the time required to verify it grow much more slowly than the computation to be verified**". succint zk proofs can be verified within a few milliseconds**, with a **proof length of only a few hundred bytes** even for large statements.
* this entails enconding the computation into polynomials. **a polynomial commitment** is way to hash a polynomial, and the equations between polynomials can be checked by checking equations between hashes.
* **zcash was the first widespread application of zk-snarks**. in may '22, zcash introduced the orchad shielded payment protocol, which utilizes the halo 2 zk proving system.


<br>

---

### resources

<br>


* **[what are zk-snarks, by z-cash](https://z.cash/technology/zksnarks/)**
* **[libsnark, C++ lib for zkSNARKS](https://github.com/scipr-lab/libsnark)**
* **[bellman, a crate for building zk-SNARK circuits](https://github.com/zkcrypto/bellman)**
* **[an approximate introduction to how zk-snarks are possible, by vitalik](https://vitalik.ca/general/2021/01/26/snarks.html)**

<br>

##### halo2

* **[intro to PLONKish/halo2, by ying tong](https://docs.google.com/presentation/d/1UpMo2Ze5iwzpwICPoKkeT04-xGFRp7ZzVPhgnidr-vs/edit#slide=id.g133c45f1bcd_3_36)**
