# Some Responses to the Discussion Questions

Q: Why would some miners use parts of the version field as a nonce? What effect did this have on nodes?  
A: **Why**: the nonce value in the header field is only 32 bit, which is a trivial nonce space to burn through with any modern miner (say, at 16TH/s), and after overflow updating a nonce in the coinbase needs a (partial) merkle tree recompute, so it's the most efficient way, I guess"" and ""nTime can be used as well, though as that value is in seconds and there's strict requirements on it, there's not that much wiggle room as the 16 extra version bits give"" -- Wladimir J. van der Laan (twitter discussion) Also that it's easier to update the version bits to change the nonce in an ASIC then to change the nonce in the coinbase.
**Side effect**: This caused spurious Unknown block versions being mined"" error messages." Learn more [here](https://github.com/bitcoin/bitcoin/pull/15471).

Q: How does the FIBRE network work and what were the motivations to iterate on the original Relay Network?  
A: **What?** The Fast Internet Bitcoin Relay Engine (FIBRE) is is a protocol and implementation designed to relay blocks within a network of nodes with almost no delay beyond the speed of light through fiber.
**How?** FIBRE improves on the design of the Bitcoin Relay Network primarily in two ways: it eliminates latency spikes by sending extra data to compensate for packet loss (UDP and forward-error-correction) and is based on the compression provided by the Compact Block work in Bitcoin Core.
**Why?** Miners want to know ASAP if a new block is found to start mining on it. The previously used TPC is not suitable to relay blocks over long distances with high latency (i.e. around the globe), since TCP needs a round trip for error correction. See [here](http://bitcoinfibre.org/fibre-howto.html).

Q: What is a "block withholding" attack? Why isn't it used more often? What is the defense?
A: **What?** The block or attack cause financial harm to a pool operator. A pool miner that solves a block can withhold a valid hash after finding one, while still submitting valid shares that do not meet Bitcoin's difficulty requirement. The cost to the miner is trivial (from not being awarded the one share) but the cost to the pool is large as the pool loses a chance to earn the block award subsidy + fees, while also compensating the miner for useless work.
**Why?** There are a few reasons a miner might withhold a block. One is to simply cause financial harm to the pool operator. Another is that a miner might be attempting a double-spend attack on a merchant who accepts a 0-confirmation transaction, and does not want to broadcast a block containing the transaction to be double-spent. A third is that by using the miner's knowledge of an imminent block, the miner can redirect all hashpower to the pool where the block was discovered, while withholding the valid solution for a period of time. Doing so could increase the miner's share of the eventual block reward, but at the risk of a another miner finding and broadcasting a valid block.
**How to mitigate?** One mitigation for a pool operator is to occasionally give work with a known solution to miners in the pool, and to flag participants who don't return the solution.

Q: How do P2Pools work? Advantages and disadvantages? (Mining and Consensus in Mastering Bitcoin)
A: P2Pools are peer-to-peer mining pools that operate without a pool operator. They work by relying on software that decentralizes the functions of the pool server that an operator would traditionally do. The peer-to-peer pool implements a *share chain*, which is a blockchain-like system that runs with a lower difficulty than bitcoin's, and where miners mine "shares" of the chain every 30 seconds. The miners mine on the share chain, earning shares of the eventual reward, and when one of the blocks mined on the chain also meets bitcoin's difficulty requirement, the block is propagated and the miners with shares in the share chain preceding the valid blocks receive a payout proportionate to their shares. The advantage of P2Pools is that there is no central operator who can direct the miners' efforts towards nefarious purposes (e.g. double spending). The disadvantage for miners is that it requires them to run a full bitcoin node and the P2Pool software, neither of which are required in a centralized setup because the pool operator can handle those functions.

Q: How far back into the past can the timestamp in blocks be? Is this validated? How can this be attacked?  
A: See [time-warp attack](https://bitcoin.stackexchange.com/a/75834).

Q: Have we seen the difficulty algorithm be manipulated in other projects? Is this a threat to Bitcoin?  
A: See Bcash and [coin hopping](https://medium.com/nikoin/coin-hopping-attack-what-after-a-month-of-bitcoin-hardfork-f5a92151fb7b)

Q: What is the difference between overt and covert ASIC Boost?  
A: **Overt**: version-rolling method which is completely transparent in the blockheader of each boosted Bitcoin block.  
**Covert**: Recalculation of the merkle tree which is easier with small or empty blocks. Learn more [here](https://www.asicboost.com/single-post/2018/03/01/opening-asicboost-for-defensive-use/) and [here](https://bitslog.com/2017/04/10/the-relation-between-segwit-and-asicboost-covert-and-overt/).
