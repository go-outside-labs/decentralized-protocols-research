## notes and resources on protocol economy


<br>



#### 👉 start with [how blockchain works](blockchains)

#### 👉 check [this curated list of protocols and projects](bulding_protopia) that are authentic to their values and are committed to building a healthy and responsible future




<br>

---

### 🕹 game theory

<br>

* [columbia cryptoeconomics workshop 2022](https://www.youtube.com/playlist?list=PLpktWkixc1gUqkyc1-iE6TT0RWQTBJELe)

* [standford class on game theory](https://www.coursera.org/learn/game-theory-1#syllabus) and [advanced course](https://www.coursera.org/learn/game-theory-2)

* [finding pure strategy nash equilibrium in finite simultaneous games](https://www.youtube.com/watch?v=gINERi_wbbg)

* [censorship resistance in on-chain auctions, pai et al.](https://github.com/eljhfx/Decentralized-Auctions/blob/main/Censorship_Resistance_in_On-Chain_Auctions.pdf)
  - single proposer blockchains are not ideal for holding time sensitive auctions when the number of potential bidders is large. collusion arrangements are extremely profitable for the colluding bidder but only marginally profitable for the proposer. order agnostics mechanism should solve mev.

<br>


-----

### 🛵 protocol design

<br>

#### proposer-builder separation

* [notes on pbs, by barnabe.eth](https://barnabe.substack.com/p/pbs)
  - thoughts on in-protocol pbs, market structure and allocation mechanism, whole vs. partial block building, block vs. slot auctions, inclusion lists, capturing true pbs value via consensus bid and protocol capture.
  
* [decentralizing the builder role, by j. charbonneau](https://joncharbonneau.substack.com/p/decentralizing-the-builder-role)

* [exploring cryptokitties midwives](https://medium.com/block-science/exploring-cryptokitties-part-2-the-cryptomidwives-a0df37eb35a6)
   - `giveBirth()` as an example of flawed economic incentive and randomization.

* [bookmark list for consensus researchers, by a. obadia](https://collective.flashbots.net/t/bookmarks-relevant-for-consensus-researchers/1204)
   - nice list from flashbots on canonical papers on consensus


<br>

#### eip-1559

* [transaction fee mechanism design for ethereum, by tim roughgarden](https://timroughgarden.org/papers/eip1559.pdf)
  - thoughts on how eip-1559 proposes a major change to ethereum's transaction fee mechanism, the market for ethereum transactions, incentive-compatible transaction fee mechanisms, and alternative designs.

* [congestion control and eip1559, by barnabe.eth](https://barnabe.substack.com/p/congestion-control-and-eip1559)
* [understanding fees in eip-1559](https://barnabe.substack.com/p/understanding-fees-in-eip1559)
* [mev and eip1559](https://github.com/MEV-WAIFU-LABS/mev/blob/main/MEV_on_Ethereum/eip-1559.md)

<br>

#### mev-smoothing

* [burning mev through block proposer auctions, by domothy](https://ethresear.ch/t/burning-mev-through-block-proposer-auctions/14029)


<br>

#### algorithmic game theory

* [algorithmic game theory, by tim roughgarden](https://theory.stanford.edu/~tim/papers/cacm.pdf)


<br>

#### inclusion lists

* [inclusion list economics](https://efdn.notion.site/Inclusion-list-economics-b0d61d0e21a74963a54448e48d9adc8a)


<br>

------

### 👾 models

<br>

* [CADlabs's ethereum economic model](https://github.com/CADLabs/ethereum-economic-model)

