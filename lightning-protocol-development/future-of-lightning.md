# The Future of Lightning

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [Breaking Down the Bitcoin Lightning Network: eltoo](https://medium.com/@brandonarvanaghi/breaking-down-the-bitcoin-lightning-network-eltoo-c48554f5ae02) | 15 |
| [Eltoo by fiatjaf](https://fiatjaf.com/ffdfe772.html) | 15 |
| \(_optional_\) [Eltoo and the Far Future](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-25-christian-decker-eltoo/) | 40 |
| \(_optional_\) [Onion Messages](https://github.com/lightning/bolts/pull/759) | X |
| [Keysend](https://lightning.readthedocs.io/lightning-keysend.7.html) (proposed BOLT12) | 15 |
| [Offers](https://bitcoinops.org/en/topics/offers/) (proposed BOLT12) | 10 |
| \(_optional_\) [Route Blinding](https://github.com/lightning/bolts/pull/765) | X |
| [Submarine Swaps](https://blog.muun.com/a-closer-look-at-submarine-swaps-in-the-lightning-network/) | 15 |
| [Loops](https://blog.lightning.engineering/posts/2019/03/20/loop.html) | 10 |
| \(_optional_\) [Submarine swaps/ Loops](https://youtu.be/qixhNBIHDyE) | 50 |
| [Splicing](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-26-rene-pickhardt-splicing/) | 30 |
| [Splices and Liquidity in the Lightning Network](https://blog.muun.com/splices-and-liquidity-in-the-lightning-network/) | 15 |
| [Dual funded channels](https://www.youtube.com/watch?v=i_GxmNZjwhk) (until min 26) | 26 |
| [Liquidity Advertisements](https://medium.com/blockstream/lightnings-missing-piece-a-decentralized-liquidity-market-a0bb47534a4f) | 15 |
| [Multi-party channels/Channel factories](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-28-christian-decker-multiparty-channels/) | 20 |
| [Payment Points: Replacing HTLCs](https://suredbits.com/payment-points-part-1/) | 15 |
| [Payment Points: "Stuckless" Payments](https://suredbits.com/payment-points-part-2-stuckless-payments/) | 15 |
| [Peer Backups](https://medium.com/@ACINQ/phoenix-wallet-part-3-backup-f63a9470d4e7) | 10 |

## Discussion Questions

### Breaking Down the Bitcoin Lightning Network: eltoo

1. Why do we need SIGHASH\_NOINPUT for eltoo?
2. What do HTLCs look like for an Eltoo channel?

### Eltoo and the Far Future

1. How does a cooperative close work with Eltoo?
2. Can channels using Eltoo or PTLC be mixed with standard channels in a multi-hop payment?
3. Since all update transactions have the same shape, what's stopping earlier update txs from binding to later txs resetting to an old state?
4. Why do settlement txs also need SIGHASH_NOINPUT?
5. Would there ever be a reason to prefer LN-penalty when creating a channel between two Eltoo-capable nodes?

### Submarine swaps

1. Can an adversary make a swap and then wait until a moment before the lock expiry to reveal the secret on one chain while using the signature on the other? If the blocks are fast, could an attacker be able to steal the money from both chains?

### Splicing

1. Is it easier to splice on an Eltoo channel?

### Multi-party channels/Channel factories

1. What are the advantages and disadvantages of multiparty channels?

### Dual funded channels

1. How do you split the fees in dual-funded channels?

### Payment Points: Replacing HTLCs

1. How does a wormhole attack work?
2. Can sender or receiver notice a wormhole attack?
