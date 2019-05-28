# Sphinx, Onion Routing and Limitations

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Gossip Protocol](https://github.com/lightningnetwork/lightning-rfc/blob/master/07-routing-gossip.md) | 25 min | gossip protocol |
[Sphinx](https://cypherpunks.ca/~iang/pubs/Sphinx_Oakland09.pdf) | Intro through 2.1, 10 min | sphinx |
[Onion Routing](https://www.youtube.com/watch?v=toarjBSPFqI) | 60 min | onion routing, video |
[Exploring Lightning Network Routing](https://blog.lightning.engineering/posts/2018/05/30/routing.html) | 12 min | routing |
[Amount-independent payment routing in Lightning Networks](https://medium.com/coinmonks/amount-independent-payment-routing-in-lightning-networks-6409201ff5ed) | 6 min | routing |
[Revocable Transactions](https://rusty.ozlabs.org/?p=450) | 10 min | revocable transactions |
[Trampoline Payments](https://bitcointechweekly.com/front/outsourcing-route-computation-with-trampoline-payments/) | 10 min | trampoline payments |
[Neutrino](https://blog.lightning.engineering/posts/2018/10/17/neutrino.html) | 10 min | neutrino |
[Lightning Network 2.0](https://blog.theabacus.io/lightning-network-2-0-b878b9bb356e) starting at Lightning Problem 1: Liquidity | 20 min | future |
[Lightning Network UX Challenges](https://medium.com/breez-technology/lightning-at-the-end-of-the-tunnel-overcoming-bitcoins-ux-challenges-5738171c759e) | 12 min | lightning UX |
[Lightning Limitations](http://diyhpl.us/wiki/transcripts/boltathon/2019-04-06-alex-bosworth-major-limitations/) | 35 min | lightning limitations |
[Lightning Security Analysis](https://diyhpl.us/wiki/transcripts/blockchain-protocol-analysis-security-engineering/2017/lightning-network-security-analysis/) | 25 min | security |

## Discussion Questions

### Trampoline Payments
1. Why not just ask 'trampoline' nodes for routing paths in an SPV/Neutrino kind of way? This seems simpler in comparison. Is this something that has been discussed? Concept seems somewhat similar to beacon nodes.
2. Can trampoline payments be combined with AML to mitigate privacy issues?

### Channel rebalancing
3.  What is the relevance of automated channel rebalancing/loop at the moment? Is it on roadmaps or is it being ignored as devs rather work on AMP? Is anyone using it currently?
4. how is Loop Out different from closing a channel & opening a new one?

### Routing
5. Explain the concept of a shadow route.
6. What is the difference between Dijkstra’s algorithm (used in lnd) and the Bellman-Ford algorithm (used in c-lightning) for path finding?

### Route Probing with "invalid" payment hashes
7. Fake payment hash probing (see c-lightning plugins from niftynei/decker) seem to enable the interpretation of individual channel balances, because the routing errors (BOLT) differentiate between end node or onion route fail. I am working on a POC to probe for channel balances along each hop of a given route by incrementing routed value and interpreting failure type, and am wondering why these error messages must leak this information. Also, it seems there is no obvious way to classify probing as "spam", right? If anybody working on lightning has looked into this, I would love to learn more. [Link](https://github.com/niftynei/sitzprobe/blob/84347d551934a1072b65c0dc04c9554db2a97884/sitzprobe.go#L199).

### Neutrino
8. If Neutrino becomes the preferred way of using Bitcoin, wouldn't it give too much power to the miners, as Neutrino clients might blindly follow the longest chain, in case there is a fork? Should Neutrino be coupled with a trusted server (that runs a full node) by default? And also disabled by default in Core if merged, for the same reason? [Link](https://medium.com/@nicolasdorier/neutrino-is-dangerous-for-my-self-sovereignty-18fac5bcdc25).

### Scripting
9. why does the main output’s revocation use CSV, but the HTLC use CLTV?

### Liquidity/Capacity
10. what’s to prevent an attacker from temporarily drying up liquidity in the network, by sending payments to himself using really long routes, but does not complete the payments? by using X amount of funds, he can potentially lock up an amount several times of X, depending on how long he wants to construct the routes. This attack would not cost the attacker any money, only time. It would not be possible to attribute fault to the attacker as LN is onion-routed, so the routing nodes would have no idea where exactly the money is held up. The routing nodes could also be doing this attack among themselves, to compete for market share.

### Watchtower
11. how do Watchtowers work with non-advertised channels, when part of the graph is not known? or Trampoline, when routing calculation is outsourced?

### HTLC
12. is this correct: under “normal” working conditions, and all payments are successful, HTLC outputs are merged back to the main outputs? So the HTLC portion of the commitment transaction rarely gets recorded on-chain?
