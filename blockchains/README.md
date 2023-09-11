## 🧱⛓ intros to blockchain 

<br>

---

### Understading Sparse Merkle Trees

<br>



**Merkle trees** are the canonical and original example of an **authenticated data structure**, designed for **easy inclusion proofs** but not **exclusive proofs** (*e.g.*, a prover can efficiently convince the verifier that a particular entry is present but not absent). In addition, since **inserting at a specific position cannot be done efficiently** (as the whole tree would need to be recomputed), these trees are unsuitable for authenticated key-value maps.

**Sparse Merkle trees**, on the other hand, provide **efficient exclusion proofs** by design. They can be built on a key-value map, where each possible `(K, V)` entry corresponds to a unique leaf node and is linked to its position in the tree. Due to the **history independence** of the Merkle root from element insertion order, Sparse Merkle trees are the suitable choice to authenticate key-value maps.



<br>


---

#### Representing `(K, V)` pairs as leaf nodes

<br>


In a Sparse Merkle tree, a particular `(K, V)` is represented by the leaf node and its path from the root encoded by its hash digest. 

Leaf nodes should allow every possible value of the cryptographic hash function to map a `(K, V)` value (through a `H_leaf(K, V)`). Therefore, if the function is represented by `N` bits, the tree's height is `N`, and the paths down to the `2^N` leaf nodes are represented by (`N`-nodes-deep) bit-strings. When the `(K, V)` entry is not present in the map, an empty leaf is assigned (for instance, with an all-`0` digest).


In the case of SHA-256, the tree has a height of `256` and `2^{256}` leaf nodes represented by `256-bit` paths.

<br>

<p align="center">
<img src="https://github.com/go-outside-labs/decentralized-protocols-research/assets/138340846/26186c07-57c9-4857-843a-f51390481055" width="60%" align="center" style="padding:1px;border:1px solid black;"/>
</p>

<br>



---

#### Internal nodes

<br>


Branch nodes have left and right subtrees given by the digest of its child subtrees digest (something like `H_branch(Digest, Digest)`, a concatenated hash of its child nodes). Note that different hash functions should be used for leaf and branch nodes to prevent [preimage attacks](https://en.wikipedia.org/wiki/Preimage_attack).


Each child subtree position is found by looking at the bits of `H(K)`. A left branch is denoted as `0` and a right branch as `1`, so the most left leaf's key is `0x000..00`, the next is `0x00..0`, the most right key is `0x11..11`, and so on.

Most leaf nodes are empty, and the hashes of empty nodes are identical. The same is true for interior nodes whose children are all empty: subtrees with no leaf nodes are represented as an empty subtree with a digest such as the all-`0` digest.


<br>


---

#### The root node

<br>

Parent branch nodes are obtained by hashing together two child nodes recursively until the top to the Merkle root of the tree. 

The root hash is the commitment of the tree. This value is either digest of the root node (either all-`0` digest or a `H_branch()` function). 


<br>

<p align="center">
<img src="https://github.com/go-outside-labs/decentralized-protocols-research/assets/138340846/e401050e-d502-45e9-815f-5e06400031c2" width="60%" align="center" style="padding:1px;border:1px solid black;"/>
</p>



<br>



---

#### Space complexity



<br>

To naively create a Sparse Merkle tree, one can generate all possible `2^N` outputs of the hash function as a leaf in the tree and initialize them to the empty value. This generates a nearly unbounded number of data.

Since required storage is only proportional to the number of items inserted into the tree, some optimizations are possible:

  - Items on the leaf node are initially `None` and, therefore, do not need to be stored.
  - Subtrees with no leaf nodes are represented as "empty subtree", with an all-`0` digest.
  - Internal nodes all have fixed predictable values that can be re-computed as hashes of `None` values.

Therefore, a Sparse Merkle Tree can simply store a set of leaf nodes for the `(K, V)` pairs plus a set of empty hashes representing the sparse areas of the tree.



<br>

---

#### Performance


<br>



A Sparse Merkle is nearly balanced. If there are `N` entries in the tree, a particular entry could be reached in `log2(N)` steps.



<br>

---

#### How do we know that each key is in a unique leaf?

<br>

Each leaf is a unique representation of the `2^N` possibilities presented by the digest size `N` of the cryptographic hash function.

Since cryptographic hash functions (or, in particular, SHA-256) are expected to be collision resistant (*i.e.,* it's infeasible to find two strings `s1` and `s2` such that `H(s1) == H(s2)`), each key is in a unique leaf.


<br>


---

#### Which hash function assumption does represent the empty subtree by the all-`0` digest rely upon?

<br>

The deterministic/predictable characteristics of one-way hash functions. 

In other words, `H(0)` is a constant value, and so `H(H(0))`, `H(0, 0)`, `H(H(0, 0))`, etc.

(and big chunks of the tree can be cached).

<br>


----

#### Suppose two sparse Merkle trees differ in exactly one key, but their digests are the same. Why does this break collision resistance?

<br>

Even if the two keys differ by exactly one key, their digest should be completely different. 

If that's not the case, the collision resistance assumption of the cryptographic function is broken (*i.e.,* "it's infeasible to find two strings `s1` and `s2` such that `H(s1) == H(s2)`.")
<br>

---

### more in this dir

<br>

* **[ethereum blockchain](ethereum.md)**


<br>

----

### resources

<br>


* **[leaves of hash, by trailofbits](https://blog.trailofbits.com/2019/06/17/leaves-of-hash/)**
* **[how merkle trees work, by consensys](https://media.consensys.net/ever-wonder-how-merkle-trees-work-c2f8b7100ed3)**
* **[on uploading your soul to the interplanetary sys](https://mirror.xyz/steinkirch.eth/A3iJGhXTJI5fgQoZVgIu3ovPV1P8zrxigpwngm0n4I0)**
* **[a survey of execution client diversity, from ethstaker](https://paragraph.xyz/@ethstaker/execution-client-diversity)**
