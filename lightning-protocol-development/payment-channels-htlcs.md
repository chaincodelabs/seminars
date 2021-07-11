# Payment Channels, Intro to Lightning, and HTLCs

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [History of the Lightning Network](https://www.youtube.com/watch?v=HauP9F16mUM) | 51 |
| [Lightning ≈ Bitcoin](https://www.youtube.com/watch?v=8lMLo-7yF5k) | 35 |
| [Payment Channels video](https://www.youtube.com/watch?v=4SdBa8ZOfqg) or [Understanding Payment Channels article](https://blog.chainside.net/understanding-payment-channels-4ab018be79d4) | 6 or 10 |
| [Revocable Transactions](https://rusty.ozlabs.org/?p=450) | 10 |
| [Bitcoin Timelocks Explained](https://medium.com/summa-technology/bitcoins-time-locks-27e0c362d7a1) | 16 |
| [Revocable transactions with LN-Penalty](https://www.derpturkey.com/revocable-transactions-with-ln-penalty/) | 10 |
| [Visualizing HTLCs and the Lightning Network's Dirty Little Secret](https://medium.com/@peter_r/visualizing-htlcs-and-the-lightning-networks-dirty-little-secret-cb9b5773a0) | 10 |
| [Lightning Network BOLT by BOLT](https://www.youtube.com/watch?v=Ysj2yobFMF4) \(up to demo - min 47\) | 47 |

## Discussion Questions

### History of the Lightning Network

1. Why was Segwit an important upgrade to the base layer for Lightning?
2. Why is restoring a non-up-to-date backup unsafe with Lightning? How recent does the backup need to be?
3. How can we prepare and anticipate for miners fees volatility when creating new payment channels? \(What is the mechanic?\)
4. What is different about transaction revocation in Eltoo?

### Lightning ≈ Bitcoin

1. Given the fact that Lightning is punishment-based and requires nodes to be online, could an attacker trick you into publishing old states and lose all your funds?
2. How are accidental breaches handled on Lightning \(since at the moment this is mostly what is seen in the the wild\)?

### Payment Channels video \| Understanding Payment Channels article

1. Why is a unidirectional channel easy to implement?
2. What is the benefit of the asymmetric commitment transactions?
3. When two parties exchange the previous commitment's secrets \(to invalidate previous state\), how do you make sure that the exchange happen atomically? \(i.e., that both receive the other's secret, or none at all\)
4. How do you exchange previous commitment data if the parties aren't online on the same time?
5. Would it be possible for channels to have a custom penalty agreement that does not take all the funds on a breach?

### Revocable Transactions

1. Why can't a transaction have an expiration date or maximum blockheight?
2. Why is revoking a transaction in bitcoin tricky? Can a user just take back a transaction?
3. How is the commitment secret used to create the breach remedy transaction?

### Bitcoin Timelocks Explained

1. Why do CSV and CLTV rely on nLocktime or nSequence being set in the transaction spending the outputs when the script could check if the requirements are being met by itself?
2. Can both CSV and CLTV be used in the same output and are there any known use cases for it?
3. Is it fair to say UTXO-level timelocks are superior to transaction-level timelocks since they are baked directly into the protocol and allow more flexiblity and control? Are transaction-level timelocks necessary \(Assuming there's a way to implement UTXO-level timelocks without relying on nLockTime/nSequence\)?
4. In what scenarios is `OP_CLTV` used in Lightning and in what scenarios is `OP_CSV` used?
5. Why can `OP_CLTV` and `OP_CSV` not touch the stack? Why are they always either followed by `OP_DROP` or at the end of the script? What are the pros and cons of real-time negotiation of channel parameters?

### Hashed Timelock Contracts

1. Is it correct to say that under "normal" working conditions, if all payments are successful, HTLC outputs are merged back to the main outputs? Meaning the HTLC portion of the commitment transaction rarely gets recorded on-chain?
2. Does the dust limit of the base layer affect the security of HTLCs routed on Lightning?
3. How can signature checks of arbitrary data be used to avoid storing signatures for each channel state?
4. Would HTLCs also work with CSV opcodes?
5. Why do we need the HTLC-Success and HTLC-Timeout transactions? Why can't we just use a sequence delay on the `to_local` output conditions of the HTLC itself?

### Visualizing HTLCs and the Lightning Network's Dirty Little Secret

1. What do you think of the criticism that HTLCs don't work for micropayments?
2. How do fees impact our ability to perform breach remedy?
3. What factors may affect the minimum payment size for a multi-hop payment?

### Lightning Network BOLT by BOLT

1. What problem do commitment transactions solve? When a revoked commitment transaction is found, what outputs need to be resolved by the penalty transaction? What happens to the HTLCs?
2. A node must be able to generate the  for all prior revoked commitments. How can they be stored efficiently? What are the challenges?
3. What is a good value for to-self-delay for the breach remedy and why?
4. Why is it okay for the channel partner to give up a channel state? What things do they need to enforce \(validate\) before releasing the secret?
5. What are the economic implications of the fact that gossiping about channel updates is free?

