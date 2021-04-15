# Payment Channels, Intro to Lightning, and HTLCs

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[History of the Lightning Network](https://www.youtube.com/watch?v=HauP9F16mUM) | 51 min | video |
[Lightning ≈ Bitcoin](https://www.youtube.com/watch?v=8lMLo-7yF5k) | 35 min | video |
[Payment Channels video](https://www.youtube.com/watch?v=4SdBa8ZOfqg) or [Understanding Payment Channels article](https://blog.chainside.net/understanding-payment-channels-4ab018be79d4)| 6 or 10 min | payment channels |
[Revocable Transactions](https://rusty.ozlabs.org/?p=450) | 10 min | revocable transactions |
[Bitcoin Timelocks Explained](https://medium.com/summa-technology/bitcoins-time-locks-27e0c362d7a1) | 16 min | timelocks |
[Hashed Timelock Contracts](https://rusty.ozlabs.org/?p=462) | 7 min | HTLCs |
[Visualizing HTLCs and the Lightning Network's Dirty Little Secret](https://medium.com/@peter_r/visualizing-htlcs-and-the-lightning-networks-dirty-little-secret-cb9b5773a0) | 10 min | HTLCs |
[Lightning Network BOLT by BOLT (up to demo - min 47)](https://www.youtube.com/watch?v=Ysj2yobFMF4) | 47 min | BOLTs, video |

## Discussion Questions

### History of the Lightning Network

1. Why was Segwit an important upgrade to the base layer for Lightning?

### Lightning ≈ Bitcoin

1. Given the fact that Lightning is punishment-based and requires nodes to be online, could an attacker trick you into publishing old states and lose all your funds?
1. How are accidental breaches handled on Lightning (since at the moment this is mostly what is seen in the the wild)?

### Payment Channels video | Understanding Payment Channels article

1. When two parties exchange the previous commitment's secrets (to invalidate previous state), how do you make sure that the exchange happen atomically? (i.e., that both receive the other's secret, or none at all)
1. How do you exchange previous commitment data if the parties aren't online on the same time?

### Revocable Transactions


### Bitcoin Timelocks Explained

1. Why do CSV and CLTV rely on nLocktime or nSequence being set in the transaction spending the outputs when the script could check if the requirements are being met by itself?
1. Can both CSV and CLTV be used in the same output and are there any known use cases for it?
1. Is it fair to say UTXO-level timelocks are superior to transaction-level timelocks since they are baked directly into the protocol and allow more flexiblity and control? Are transaction-level timelocks necessary (Assuming there's a way to implement UTXO-level timelocks without relying on nLockTime/nSequence)?

### Hashed Timelock Contracts

1. Is it correct to say that under "normal" working conditions, if all payments are successful, HTLC outputs are merged back to the main outputs? Meaning the HTLC portion of the commitment transaction rarely gets recorded on-chain?
1. Does the dust limit of the base layer affect the security of HTLCs routed on Lightning?
1. How can signature checks of arbitrary data be used to avoid storing signatures for each channel state?

### Visualizing HTLCs and the Lightning Network's Dirty Little Secret

1. What do you think of the criticism that HTLCs don't work for micropayments?

### Lightning Network BOLT by BOLT


