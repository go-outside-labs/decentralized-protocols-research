## kate polynomial commitment scheme (pronounced kah-tay)

<br>

### tl; dr

<br>

* it allows a prover to compute a commitment to a polynomial, with the properties that this commitment can later be opened at any position.
* the prover shows that the value of the polynomial at a certan position is equal to a claimed value.
* once a **commitment** (an elliptic curve point) is sent to the verifier, the prover cannot change the polynomial they are working with.
* a merkle tree is a "vector commitment": using a merkle tree of depth, you can compute a commitment to a list of elements of fixed length. using merkle proofs, you can provide a proof that an element is a member of this vector at position using hashes.
* in the kate commitment scheme, the element is the commitment to the polynomial: could the prover (without knowing) find another polynomial that has the same commitment.x

<br>

----

### resources

<br>

* **[kzg polynomial commitments, by dankrad feist](https://dankradfeist.de/ethereum/2020/06/16/kate-polynomial-commitments.html)**
