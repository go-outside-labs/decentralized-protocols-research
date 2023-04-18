## cryptographic primitives

<br>

### bls signatures

* used in the beacon chain to verify large numbers of signtures.
* invented by dan boneh, ben lynn, and hovav shacham.
* in optimistic rollups such as arbitrum and optimism, each tx must be accompanied by its own signature. these signatures are stored on l1 calldata, a read-only format that's commited as a part of a transaction rather than to (expensive) contract storage.
* storing txs and signatures as calldata is the cheapst method available for rollups to keep data on l1.
* the key property of bls signatures is that multiple signatures can be combined into one - so only one aggregate signature needs to be verified and stored on-chain (meaning less gas fees).


