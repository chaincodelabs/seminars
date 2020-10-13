# Some Responses to the Discussion Questions

Q: Why would some miners use parts of the version field as a nonce? What effect did this have on nodes?  
A: **Why**: the nonce value in the header field is only 32 bit, which is a trivial nonce space to burn through with any modern miner (say, at 16TH/s), and after overflow updating a nonce in the coinbase needs a (partial) merkle tree recompute, so it's the most efficient way, I guess"" and ""nTime can be used as well, though as that value is in seconds and there's strict requirements on it, there's not that much wiggle room as the 16 extra version bits give"" -- Wladimir J. van der Laan (twitter discussion) Also that it's easier to update the version bits to change the nonce in an ASIC then to change the nonce in the coinbase.
**Side effect**: This caused spurious Unknown block versions being mined"" error messages." Learn more [here](https://github.com/bitcoin/bitcoin/pull/15471).

Q: How does the FIBRE network work and what were the motivations to iterate on the original Relay Network?  
A: **What?** The Fast Internet Bitcoin Relay Engine (FIBRE) is is a protocol and implementation designed to relay blocks within a network of nodes with almost no delay beyond the speed of light through fiber.
**How?** FIBRE improves on the design of the Bitcoin Relay Network primarily in two ways: it eliminates latency spikes by sending extra data to compensate for packet loss (UDP and forward-error-correction) and is based on the compression provided by the Compact Block work in Bitcoin Core.
**Why?** Miners want to know ASAP if a new block is found to start mining on it. The previously used TPC is not suitable to relay blocks over long distances with high latency (i.e. around the globe), since TCP needs a round trip for error correction. See [here](http://bitcoinfibre.org/fibre-howto.html).

Q: What is a share withholding attack? Why isn't it used more often? What is the defense?  
A: **What?** The block or share witholding attack cause financial harm to a pool operator. A pool miner that solves a block can withhold a valid hash after finding one. The cost to the miner is trivial (from not being awarded the one share) but the cost to the pool is large as the pool loses a chance to earn the block award subsidy + fees.  
**Why?** No profit for the withholding miner, only harm to the pool operator.

Q: How far back into the past can the timestamp in blocks be? Is this validated? How can this be attacked?  
A: See [time-warp attack](https://bitcoin.stackexchange.com/a/75834).

Q: Have we seen the difficulty algorithm be manipulated in other projects? Is this a threat to Bitcoin?  
A: See Bcash and [coin hopping](https://medium.com/nikoin/coin-hopping-attack-what-after-a-month-of-bitcoin-hardfork-f5a92151fb7b)

Q: What is the difference between overt and covert ASIC Boost?  
A: **Overt**: version-rolling method which is completely transparent in the blockheader of each boosted Bitcoin block.  
**Covert**: Recalculation of the merkle tree which is easier with small or empty blocks. Learn more [here](https://www.asicboost.com/single-post/2018/03/01/opening-asicboost-for-defensive-use/) and [here](https://bitslog.com/2017/04/10/the-relation-between-segwit-and-asicboost-covert-and-overt/).
