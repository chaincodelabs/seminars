# Mining and Network Block Propagation

If you haven't recently read the [Mining and Consensus chapter in Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook/blob/77b91b1949e2c03a36c395586a44dac20ec41533/ch10.asciidoc), please review it before diving into the content below.

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Advances in Block Propagation with Greg Maxwell](https://btctranscripts.com/greg-maxwell/2017-11-27-gmaxwell-advances-in-block-propagation/) | 60 |
| [Why Is It Taking 20 Minutes to Mine This Bitcoin Block?](http://r6.ca/blog/20180225T160548Z.html) | 10 |
| [Compact Blocks](https://bitcoincore.org/en/2016/06/07/compact-blocks-faq/) | 10 |
| [Relay Networks and FIBRE](https://bluematt.bitcoin.ninja/2016/07/07/relay-networks/) | 10 |
| [Mining: No Good, The Bad, and The Ugly](https://btctranscripts.com/magicalcryptoconference/2019/the-state-of-bitcoin-mining/) | 15 |
| \(optional video\) [Hijacking Bitcoin: Routing Attacks on Cryptocurrencies](https://www.youtube.com/watch?v=4rTp37nJzGs) | 21 |
| [The History and Future of the Stratum protocol](https://docsend.com/view/szk48syby33q28zq) | 35 |
| [Mining pool reward FAQ](https://en.bitcoin.it/wiki/Mining_pool_reward_FAQ) | 15 |
| [Why Bitcoin Mining Pools Aren't Incentivized to Broadcast Blocks Quickly](https://bitcoinmagazine.com/articles/why-bitcoin-mining-pools-aren-t-incentivized-to-broadcast-blocks-quickly-1475249510/) | 10 |
| [Majority is not Enough: Bitcoin Mining is Vulnerable](https://www.cs.cornell.edu/~ie53/publications/btcProcFC.pdf) | 30 |
| [Demystifying The Selfish Mining Bet](https://eklitzke.org/demystifying-the-selfish-mining-bet) | 10 |
| [Mining pools](https://en.wikipedia.org/wiki/Mining_pool) | 15 |
| [Overview of the covert AsicBoost allegation](https://blog.bitmex.com/an-overview-of-the-covert-asicboost-allegation-2/) | 15 |

## Optional Practical Exercise

- [Larry Ruane](https://github.com/LarryRuane) has created a [proof of work mining simulator](https://github.com/LarryRuane/minesim) along with [exercises and discussion questions](https://github.com/LarryRuane/minesim#exercises-discussion-questions).

## Discussion Questions

### Mining and Consensus

1. Why would some miners use parts of the version field as a nonce? What effect did this have on nodes?
2. How do P2Pools work? Advantages and disadvantages? Why aren't there any mainstream P2Pools today in the market?
3. How far back into the past can the timestamp in blocks be? Is this validated? How can this be attacked?
4. Have we seen the difficulty retarget algorithm be manipulated in other projects? Is this a threat to Bitcoin?
5. In your opinion, is it a good or bad thing that specialized hardware is now needed to mine bitcoin rather than letting individual users participate in that part of the ecosystem?
6. Consider the following scenario: Segwit2x didn’t happen \(or miners didn’t throw in support for it\) and UASF \(BIP148\) ended up causing a chain split on August 1st, 2017, with minority mining support \(e.g. ~10-20%\). What would likely happen as a result?
7. Can you ensure the transaction will be processed even if you send it with low fees? Which mechanisms do you have to ensure a stuck transaction (due to low fees) gets processed?

### Advances in Block Propagation

1. How can changes to Bitcoins p2p protocol affect mining?
1. How is a high stale block rate the best indicator that block propagation times are too high?
1. Alternatively, while a low stale block rate can be an indicator that block propagation times are good, it could also be an indicator of something more problematic. What could be a bad reason for there to be very few stale blocks?
1. Greg Maxwell mentioned that miners are hesitant to connect with one another directly, even though it would speed up block propagation. Why?
1. A low block-orphaning rate can be an indicator that block propagation times are good. It could also be an indicator of something more problematic. What could be a bad reason for there to be very few orphans?

### Compact Blocks

1. How could we speed up block propagation in the network like FIBRE does, but without the drawback of having to trust others?
2. Compact block relay is a good way to reduce the amount of bandwidth to propagate new blocks to full nodes, but is it the fastest method for a synced node given peers may need to request missing transactions?

### Relay Networks and FIBRE

1. How does the FIBRE network work and what were the motivations to iterate on the original Relay Network?

### Mining: No Good, The Bad, and The Ugly

1. What is a BGP Hijack attack? What prevents it? 
2. Why not encrypt all communications with pool operators?

### Majority is not Enough

1. What is the 'Selfish Mining' attack? How does it work? Is it a real threat?
2. Is it possible to identify and ignore a Selfish Miner's chain? Must we follow the most-work chain even if we identify that it came from a selfish miner?

### Mining pools

1. How do pools give work assignments to client miners? Do all miners search the same block candidates?
2. What are 'shares' and how do they help facilitate pooled mining?

### Overview of the covert AsicBoost allegation

1. What is the difference between overt and covert ASIC Boost?
