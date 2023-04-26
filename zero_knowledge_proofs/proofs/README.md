## zero-knowledge proofs

<br>

### tl; dr

<br>

* suppose that you have a (public) function `f`, a (private) input `x`, and a (public) output `y`. 
* you want to prove that you know an `x` such that  `f(x) = y`, without revealing what `x` is. 
* for the proof to be succinct, you want it to be verifiable much more quickly than computing itself.

<br>

<img width="284" src="https://user-images.githubusercontent.com/1130416/234407214-ed3974fd-85cc-471b-a08b-e2edf0efd1a2.png">

<br>

##### comparison of proof systems

<br>


<img width="550"  src="https://user-images.githubusercontent.com/1130416/234476377-f7c88f31-919f-4503-8b60-203ca9b0c06d.png">

<br>

<img width="600"  src="https://user-images.githubusercontent.com/1130416/234476566-df847c7f-b1ad-42cf-b5dd-85ba2cf7a997.png">



<br>

##### common reference strings, trusted setup, multi-party computation ceremony

* for some proofs to work, such as zk-snarks, it's necessary to create a Common Reference String (CRS), which provides public parameters for proving and verifying validity proofs. 
& the security of the proving system depends on the csr setup and some zk-rollups attempt to solve this problem by using a multi-party computation ceremony (mpc) with trusted individuals.


<br>

----

### in this dir

<br>

* **[zkSNARKS](zkSNARKS.md)**
* **[zkSTARKS](zkSTARKS.md)**
* **[PLONK](plonk.md)**
* **[halo2](halo2.md)**
* **[semaphore](semaphore.md)**
* **[DARK](dark.md)**
* **[nova](nova.md)**
* **[bulletproofs](bulletproofs.md)**
* **[FRI](fri.md)**
* **[Kate](kate.md)**


<br>

---

### resources

<br>

* **[the original paper for sonic, by mary maller et al](https://eprint.iacr.org/2019/099)**

