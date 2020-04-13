# Sphinx, Onion Routing

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Gossip Protocol](https://github.com/lightningnetwork/lightning-rfc/blob/master/07-routing-gossip.md) | 25 min | gossip protocol |
[Gossip Protocol/Path Finding](https://youtu.be/MeEFUaRnMak) | 56 min | gossip protocol, video |
[Sphinx](https://cypherpunks.ca/~iang/pubs/Sphinx_Oakland09.pdf) | Intro through 2.1, 10 min | sphinx |
[Onion Routing](https://youtu.be/toarjBSPFqI) | 11 min | onion routing, video |
[Onion Routing - deep dive](	https://youtu.be/D4kX0gR-H0Y) | 38 min | onion routing, video |
[Exploring Lightning Network Routing](https://blog.lightning.engineering/posts/2018/05/30/routing.html) | 12 min | routing |
[Lightning Network Topology](https://youtu.be/N7rlHCnaBf8) | 34 min | routing, video |
[Amount-independent payment routing in Lightning Networks](https://medium.com/coinmonks/amount-independent-payment-routing-in-lightning-networks-6409201ff5ed) | 6 min | routing |
[Revocable Transactions](https://rusty.ozlabs.org/?p=450) | 10 min | revocable transactions |
[Trampoline Payments](https://bitcointechweekly.com/front/outsourcing-route-computation-with-trampoline-payments/) | 10 min | trampoline payments |
[Trampoline Payments Seminar Video](https://youtu.be/1WmIjHrjFsg) | 39 min | trampoline payments, video |
[Atomic multi-path payments (AMP)](https://youtu.be/Og4TGERPZMY) | 21 min | AMP, video |
[Keysend (Spontaneous Payments)](https://youtu.be/zaBY9_eEQWE) | 23 min | keysend, video |
[Fee Management](https://youtu.be/r8S3iELg9_U) | 29 min | fees, video |
[Neutrino](https://blog.lightning.engineering/posts/2018/10/17/neutrino.html) | 10 min | neutrino |


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

### Neutrino
7. If Neutrino becomes the preferred way of using Bitcoin, wouldn't it give too much power to the miners, as Neutrino clients might blindly follow the longest chain, in case there is a fork? Should Neutrino be coupled with a trusted server (that runs a full node) by default? And also disabled by default in Core if merged, for the same reason? [Link](https://medium.com/@nicolasdorier/neutrino-is-dangerous-for-my-self-sovereignty-18fac5bcdc25).

### Scripting
8. why does the main output’s revocation use CSV, but the HTLC use CLTV?

### Watchtower
10. how do Watchtowers work with non-advertised channels, when part of the graph is not known? or Trampoline, when routing calculation is outsourced?

### HTLC
11. is this correct: under “normal” working conditions, and all payments are successful, HTLC outputs are merged back to the main outputs? So the HTLC portion of the commitment transaction rarely gets recorded on-chain?
