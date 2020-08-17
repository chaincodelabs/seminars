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

1. Given the fact that Lightning is punishment-based and that it requires nodes to be online, could an attacker trick you into publishing old states and lose all your funds?

### HTLCs
2. is this correct: under “normal” working conditions, and all payments are successful, HTLC outputs are merged back to the main outputs? So the HTLC portion of the commitment transaction rarely gets recorded on-chain?

### Breach Remedy
3. When 2 parties exchange the previous commitment’s secrets (to invalidate prev state), how do you make sure that the exchange happen atomically? i.e., whether both receive the other’s secret, or none at all?

4. Related to (2), how do you exchange previous commitment's data if the parties aren't online on the same time?

### CHECKSIGFROMSTACK / OP_PUSHTXDATA
5. How can signature checks of arbitrary data be used to not have to store signatures for each channel state?

### Timelocks
6. Why do CSV and CLTV rely on nLocktime or nSequence being set in the transaction that is spending the outputs when the script could check the if the requirements are being met by itself?
7. Can both CSV and CLTV be used in the same Output and are there any known use cases for it?
"all nSequence locked transactions are opting into RBF": in general why do these 2 concepts (timelock & RBF) are mixed together? why can't a nSequence-locked tx opt out of RBF (but a nTimeLock-locked tx can)? was this intentional? what are the implications of this?
8. Is it fair to say UTXO-level timelocks are superior to tx-level timelocks? as they are baked directly into the protocol & allow more flexiblity/control. Are tx-level timelocks still necessary? (Assuming there's a way to implement UTXO-level timelocks without relying on nLockTime/nSequence)

### HTLCs and micropayments
9. What do you think of the criticism that HTLCs don't work for micropayments?
