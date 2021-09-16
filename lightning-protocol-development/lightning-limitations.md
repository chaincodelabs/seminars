# Lightning Limitations

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Lightning Network 2.0](https://blog.theabacus.io/lightning-network-2-0-b878b9bb356e#:~:text=Lightning%20Problem%201%3A%20Liquidity) \(starting at Lightning Problem 1: Liquidity\) | 20 |
| [Lightning Limitations](http://btctranscripts.com/boltathon/2019-04-06-alex-bosworth-major-limitations/) | 35 |
| [Spamming the Lightning Network](https://github.com/t-bast/lightning-docs/blob/master/spam-prevention.md) | 30 |
| [Limitations of lightweight clients](https://youtu.be/ULVItljEiFE) | 18 |
| [Fee Management](https://youtu.be/r8S3iELg9_U) \(until min 21\) | 21 |
| [Incentive problems in the network](https://btctranscripts.com/chaincode-labs/chaincode-residency/2018-09-18-alex-bosworth-incentive-problems-in-the-lightning-network/) | 34 |
| [Routing Failures](https://youtu.be/z5vEyvc2vrE) | 17 |
| [Griefing attacks](https://bitcoinmagazine.com/technical/good-griefing-a-lingering-vulnerability-on-lightning-network-that-still-needs-fixing) | 10 |
| [Lightning Attack Vectors](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-25-fabrice-drouin-attack-vectors-of-lightning-network/) | 30 |
| [Pinning Attacks](https://github.com/t-bast/lightning-docs/blob/master/pinning-attacks.md) | 40 |
| [Solutions to inbound capacity problem in Lightning Network](https://medium.com/lightningto-me/practical-solutions-to-inbound-capacity-problem-in-lightning-network-60224aa13393) | 10 |
| [Channel probing in the face of parallel channels](https://s-tikhomirov.github.io/lightning-probing/) | 25 |

## Discussion Questions

1. What are the incentives around on-chain fees for the funding tx? Does the fundee care if the funder submits a funding tx with very low fee?

### Major Limitations of Lightning

1. What is the danger of being able to associate a base layer bitcoin node with the owner’s lightning node?
2. What problem do anchor outputs resolve? Why don't they solve the pinning problem?

### Spamming the Lightning Network

1. What variables other than `htlc_min_val` and `max_num_htlcs` could be tweaked to make it harder or less attractive for an attacker to try and lock up a channel?

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

1. What's to prevent an attacker from temporarily drying up network liquidity by sending himself payments using really long routes without completing the payments? By using X amount of funds, an adversary can potentially lock up an amount several times of X, depending on how long she wants to construct the routes. This attack would not cost the attacker any money, only time. It would not be possible to attribute fault to the attacker as LN is onion-routed, so the routing nodes would have no idea where exactly the money is held up. The routing nodes could also be doing this attack among themselves, to compete for market share.

### Pinning Attacks

1. Can including fees in channel transactions be abused by attackers? How do anchors seek to fix this?
2. If a channel is being closed unilaterally, and the commitment tx has a low fee, can one of the parties bump the fees with CPFP \(spend their output with a high fee\)? If not, why not?

### On the Difficulty of Hiding the Balance of Lightning Network Channels

1. What are the effects of upfront fees for HTLC on malicious probing and "honest" probing?
2. Is randomly denying a percentage of payment requests an effective countermeasure to the balance probing attack? Outside of the potential loss of routing fees, are there any other downsides?
3. Another countermeasure was to remove error messages when a route fails. Besides having less clarity as to why a path failed when trying to find a route for a payment, are there any other reasons to include these error messages? When trying to find a path, if one of the links did not have enough capacity and you got a generic error message, you'd still keep trying enough paths and eventually get the payment through. If the problem was something else, like in the attack the destination node doesn't have the preimage for the HTLC, then after enough fails the sender would realize the problem is likely in the destination node. Is there a good use case for keeping the path error messages?
