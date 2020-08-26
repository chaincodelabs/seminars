# Lightning Routing

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[Network topology creation & maintenance](https://www.youtube.com/watch?v=j2l_Ut4k1qI) | 34 min | routing, video |
[Routing problems and solutions (rendezvous, trampoline)](https://www.youtube.com/watch?v=1O-bhcbh9vE) | 26 min | rendezvous, trampoline, video |
[Gossip Protocol/Path Finding](https://youtu.be/MeEFUaRnMak) | 56 min | gossip protocol, video |
[Onion Routing](https://youtu.be/toarjBSPFqI) | 11 min | onion routing, video |
[Onion Routing - deep dive](https://youtu.be/D4kX0gR-H0Y) | 38 min | onion routing, video |
[Amount-independent payment routing in Lightning Networks](https://medium.com/coinmonks/amount-independent-payment-routing-in-lightning-networks-6409201ff5ed) | 6 min | routing |
[Atomic multi-path payments (AMP)](https://youtu.be/Og4TGERPZMY) | 21 min | AMP, video |
[Fee Management](https://youtu.be/r8S3iELg9_U) | 29 min | fees, video |
[Neutrino](https://blog.lightning.engineering/posts/2018/10/17/neutrino.html) | 10 min | neutrino |
[Sphinx](https://cypherpunks.ca/~iang/pubs/Sphinx_Oakland09.pdf) | Intro through 2.1, 10 min | sphinx, _optional_ |

## Discussion Questions

### Trampoline Payments
1. Can trampoline payments be combined with AML to mitigate privacy issues?

### Rendezvous Routing
2. Can you explain rendezvous routing in plain English?
3. Would it make sense to chain multiple rendezvous meeting points?

### Neutrino
4. If Neutrino becomes the preferred way of using Bitcoin, wouldn't it give too much power to the miners since Neutrino clients might blindly follow the longest chain in the case there is a fork? Should Neutrino be coupled with a trusted server (that runs a full node) by default? Should it be disabled by default in Bitcoin Core?

### Watchtowers
5. How do watchtowers work with non-advertised channels when part of the graph is not known? Or with Trampoline when routing calculation is outsourced?
