# Lightning Limitations

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Lightning is broken](https://www.youtube.com/watch?v=s9KMRWkcwtE) | 60 |
| [Lightning Network 2.0](https://blog.theabacus.io/lightning-network-2-0-b878b9bb356e#:~:text=Lightning%20Problem%201%3A%20Liquidity) \(starting at Lightning Problem 1: Liquidity\) | 30 |
| [Lightning Limitations](http://btctranscripts.com/boltathon/2019-04-06-alex-bosworth-major-limitations/) | 45 |
| [The price of anarchy](https://blog.bitmex.com/price-of-anarchy-from-selfish-routing-strategies/) | 30 |
| [What Are Anchor Outputs?](https://fanismichalakis.fr/posts/anchor-outputs/) | 25 |
| [Spamming the Lightning Network](https://github.com/t-bast/lightning-docs/blob/master/spam-prevention.md) | 40 |
| [Limitations of lightweight clients](https://btctranscripts.com/chaincode-residency/2019-06-26-fabrice-drouin-limitations-of-lightweight-clients/) | 25 |
| [Fee Management](https://btctranscripts.com/chaincode-residency/2019-06-25-fabrice-drouin-fee-management/) | 30 |
| [Incentive problems in the network](https://btctranscripts.com/chaincode-residency/2018-09-18-alex-bosworth-incentive-problems-in-the-lightning-network/) | 45 |
| [Routing Failures](https://btctranscripts.com/chaincode-residency/2019-06-25-fabrice-drouin-routing-failures/) | 30 |
| [Griefing attacks](https://bitcoinmagazine.com/technical/good-griefing-a-lingering-vulnerability-on-lightning-network-that-still-needs-fixing) | 15 |
| [Lightning Attack Vectors](https://btctranscripts.com/chaincode-residency/2019-06-25-fabrice-drouin-attack-vectors-of-lightning-network/) | 40 |
| [Pinning Attacks](https://github.com/t-bast/lightning-docs/blob/master/pinning-attacks.md) | 50 |
| [Solutions to inbound capacity problem in Lightning Network](https://medium.com/lightningto-me/practical-solutions-to-inbound-capacity-problem-in-lightning-network-60224aa13393) | 20 |
| [Unjamming Lightning](https://research.chaincode.com/2022/11/15/unjamming-lightning/)  | 25 |
| \(optional\) [Jamming Book](https://jamming-dev.github.io/book/about.html) | 30 |

## Discussion Questions

1. What are the incentives around on-chain fees for the funding tx? Does the fundee care if the funder submits a funding tx with very low fee?

### Major Limitations of Lightning

1. What is the danger of being able to associate a base layer bitcoin node with the owner’s lightning node?
2. What problem do anchor outputs resolve? Why don't they solve the pinning problem?

### What Are Anchor Outputs?

1. Can including fees in channel transactions be abused by attackers? How do anchors seek to fix this?

### Spamming the Lightning Network

1. What variables other than `htlc_minimum_msat` and `max_accepted_htlcs` could be tweaked to make it harder or less attractive for an attacker to try and lock up a channel?
2. Can we differentiate between the useful messages like error and trial path finding versus spam like probes?

### Limitations of lightweight clients

1. As a service, why is it easier to send funds than receive them?

### Fee Management

1. Why would the fundee care about the size the fees if it’s a funder that’s paying the fees?
2. If you disagree about the fees with your peer, how do you negotiate them?

### Incentive problems in the network

1. What kind of info would be relevant for doing local reputation tracking?
2. How would having bidirectional fees for payments affect overall routing incentives?

### Routing Failures

1. What challenges exist for making routing table synchronization efficient?

### Lightning Attack Vectors

1. What's to prevent an attacker from temporarily drying up network liquidity by sending himself payments using really long routes without completing the payments?

### Pinning Attacks

1. If a channel is being closed unilaterally, and the commitment tx has a low fee, can one of the parties bump the fees with CPFP \(spend their output with a high fee\)? If not, why not?

### On the Difficulty of Hiding the Balance of Lightning Network Channels

1. What are the effects of upfront fees for HTLC on malicious probing and "honest" probing?
2. Is randomly denying a percentage of payment requests an effective countermeasure to the balance probing attack? Outside of the potential loss of routing fees, are there any other downsides?
3. Another countermeasure was to remove error messages when a route fails. Besides having less clarity as to why a path failed when trying to find a route for a payment, are there any other reasons to include these error messages?
