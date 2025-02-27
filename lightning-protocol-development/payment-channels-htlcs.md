# Payment Channels, Intro to Lightning, and HTLCs

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [History of the Lightning Network](https://btctranscripts.com/chaincode-residency/2018-10-22-christian-decker-history-of-lightning/) | 60 |
| [A Brief History of Payment Channels: from Satoshi to Lightning Network](https://old.reddit.com/r/Bitcoin/comments/cc9psl/technical_a_brief_history_of_payment_channels/) | 30 |
| [Lightning ≈ Bitcoin](https://btctranscripts.com/chaincode-residency/2018-10-22-christian-decker-lightning-bitcoin/) | 45 |
| [Payment Channels video](https://www.youtube.com/watch?v=4SdBa8ZOfqg) or [Understanding Payment Channels article](https://blog.chainside.net/understanding-payment-channels-4ab018be79d4) | 10 or 20 |
| [Revocable transactions with LN-Penalty](https://www.derpturkey.com/revocable-transactions-with-ln-penalty/) | 20 |
| [A Lightning penalty transaction](https://fiatjaf.com/73095980.html) | 10 |
| [HTLC Overview](https://ellemouton.com/posts/htlc/) | 20 |
| [HTLC Deep Dive](https://ellemouton.com/posts/htlc-deep-dive/) | 20 |
| [Bitcoin Timelocks Explained](https://medium.com/summa-technology/bitcoins-time-locks-27e0c362d7a1) | 30 |
| [Visualizing HTLCs and the Lightning Network's Dirty Little Secret](https://medium.com/@peter_r/visualizing-htlcs-and-the-lightning-networks-dirty-little-secret-cb9b5773a0) | 20 |
| [Lightning Network BOLT by BOLT](https://btctranscripts.com/misc/2018-07-24-la-blockchain-jim-posen-lightning-bolt-by-bolt/) \(up to demo - min 47\) | 47 |
| \(optional\) [An Overview of Lightning Network Implementations](https://medium.com/@fulgur.ventures/an-overview-of-lightning-network-implementations-d670255a6cfa) | 25 |
| \(optional video\) [Bitcoin Lightning Transactions & Protocol Deep Dive](https://www.youtube.com/watch?v=to8XItlplac) | 90 |

## Discussion Questions

### History of the Lightning Network

1. Why was Segwit an important upgrade to the base layer for Lightning?
2. Why is restoring a non-up-to-date backup unsafe with Lightning? How recent does the backup need to be?
3. How can we prepare and anticipate for miners fees volatility when creating new payment channels? \(What is the mechanic?\)

*note*: eltoo is mentioned in this presentation. You do not need to understand it at this point. We will be diving much deeper into eltoo in the future of lightning section.

### Lightning ≈ Bitcoin

1. Given the fact that Lightning is punishment-based and requires nodes to be online, could an attacker trick you into publishing old states and lose all your funds? How long can one party go offline before the security of funds in the channel are compromised?
2. How are accidental breaches handled on Lightning \(since at the moment this is mostly what is seen in the the wild\)?
3. Do you consider Lightning to be a proof-of-stake system?

### Payment Channels video \| Understanding Payment Channels article

1. Why is a unidirectional channel easy to implement?
2. What is the benefit of the asymmetric commitment transactions?
3. When two parties exchange the previous commitment's secrets \(to invalidate previous state\), how do you make sure that the exchange happen atomically? \(i.e., that both receive the other's secret, or none at all\). For example, what happens if Alice sends bob 1000 stats, but then never sends a new commitment signed after sharing revocation key?
4. How do you exchange previous commitment data if the parties aren't online on the same time?
5. Would it be possible for channels to have a custom penalty agreement that does not take all the funds on a breach?

### Revocable Transactions

1. Why can't a transaction have an expiration date or maximum blockheight?
2. Why is revoking a transaction in bitcoin tricky? Can a user just take back a transaction?
3. How is the commitment secret used to create the breach remedy transaction?

### Bitcoin Timelocks Explained

1. What are the different locations for timelocks? Why do we use CLTV instead of CSV in the HTLC output of the commitment transaction? What is Median-Time-Past?
2. Why do CSV and CLTV rely on nLocktime or nSequence being set in the transaction spending the outputs when the script could check if the requirements are being met by itself?
3. Can both CSV and CLTV be used in the same output and are there any known use cases for it?
4. Is it fair to say UTXO-level timelocks are superior to transaction-level timelocks since they are baked directly into the protocol and allow more flexibility and control? Are transaction-level timelocks necessary \(Assuming there's a way to implement UTXO-level timelocks without relying on nLockTime/nSequence\)?
5. In what scenarios is `OP_CLTV` used in Lightning and in what scenarios is `OP_CSV` used?
6. Why can `OP_CLTV` and `OP_CSV` not touch the stack? Why are they always either followed by `OP_DROP` or at the end of the script? What are the pros and cons of real-time negotiation of channel parameters?

### Hashed Timelock Contracts

1. Is it correct to say that under "normal" working conditions, if all payments are successful, HTLC outputs are merged back to the main outputs? Meaning the HTLC portion of the commitment transaction rarely gets recorded on-chain?
2. Does the dust limit of the base layer affect the security of HTLCs routed on Lightning?
3. How can signature checks of arbitrary data be used to avoid storing signatures for each channel state?
4. Would HTLCs also work with CSV opcodes?
5. Why do we need the HTLC-Success and HTLC-Timeout transactions? Why can't we just use a sequence delay on the `to_local` output conditions of the HTLC itself?
6. How do HTLCs achieve atomicity?

### Visualizing HTLCs and the Lightning Network's Dirty Little Secret

1. What do you think of the criticism that HTLCs don't work for micropayments?
2. How do fees impact our ability to perform breach remedy?
3. What factors may affect the minimum payment size for a multi-hop payment?

### Lightning Network BOLT by BOLT

1. What problem do commitment transactions solve? When a revoked commitment transaction is found, what outputs need to be resolved by the penalty transaction? What happens to the HTLCs?
2. A node must be able to generate the revocation keys for all prior revoked commitments. How can they be stored efficiently? What are the challenges?
3. What is a good value for to-self-delay for the breach remedy and why?
4. Why is it okay for the channel partner to give up a channel state? What things do they need to enforce \(validate\) before releasing the secret?
5. What are the economic implications of the fact that gossiping about channel updates is free?
