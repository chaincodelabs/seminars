# Lightning Limitations

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Limitations of lightweight clients](https://youtu.be/ULVItljEiFE) | 10 min | neutrino |
[Lightning Network 2.0](https://blog.theabacus.io/lightning-network-2-0-b878b9bb356e) starting at Lightning Problem 1: Liquidity | 20 min | future |
[Lightning Network UX Challenges](https://medium.com/breez-technology/lightning-at-the-end-of-the-tunnel-overcoming-bitcoins-ux-challenges-5738171c759e) | 12 min | lightning UX |
[Lightning Limitations](http://diyhpl.us/wiki/transcripts/boltathon/2019-04-06-alex-bosworth-major-limitations/) | 35 min | lightning limitations |
[Incentive problems in the network](https://youtu.be/lByQUr7zPr0) | 34 min | limitations, video |
[Routing Failures](https://youtu.be/z5vEyvc2vrE) | 17 min | limitations, video |
[Lightning Security Analysis](https://diyhpl.us/wiki/transcripts/blockchain-protocol-analysis-security-engineering/2017/lightning-network-security-analysis/) | 25 min | security |
[Lightning Attack Vectors](https://youtu.be/R5cSrftd8nc) | 29 min | security, video |

## Discussion Questions

### Route Probing with "invalid" payment hashes
1. Fake payment hash probing (see c-lightning plugins from niftynei/decker) seem to enable the interpretation of individual channel balances, because the routing errors (BOLT) differentiate between end node or onion route fail. I am working on a POC to probe for channel balances along each hop of a given route by incrementing routed value and interpreting failure type, and am wondering why these error messages must leak this information. Also, it seems there is no obvious way to classify probing as "spam", right? If anybody working on lightning has looked into this, I would love to learn more. [Link](https://github.com/niftynei/sitzprobe/blob/84347d551934a1072b65c0dc04c9554db2a97884/sitzprobe.go#L199).

### Liquidity/Capacity
2. What’s to prevent an attacker from temporarily drying up liquidity in the network, by sending payments to himself using really long routes, but does not complete the payments? by using X amount of funds, he can potentially lock up an amount several times of X, depending on how long he wants to construct the routes. This attack would not cost the attacker any money, only time. It would not be possible to attribute fault to the attacker as LN is onion-routed, so the routing nodes would have no idea where exactly the money is held up. The routing nodes could also be doing this attack among themselves, to compete for market share.
