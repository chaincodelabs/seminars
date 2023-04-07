# How the layers of Lightning Fit Together

## Reading

| Content | Time \(min\) |
| :--- | :--- |
| [A walk through the layers of Lightning](https://btctranscripts.com/scalingbitcoin/tel-aviv-2019/edgedevplusplus/lightning-network-layer-by-layer/) | 40 |
| [Creating a channel](https://ellemouton.com/posts/creating-a-channel/) | 20 |
| [Updating State](https://ellemouton.com/posts/updating-state/) | 20 |
| [Revocation in more detail](https://ellemouton.com/posts/revocation/) | 20 |
| [The Update Layer](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-26-rene-pickhardt-update-layer/) | 70 |
| [The Transfer Layer](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-24-fabrice-drouin-the-transfer-layer/) | 50 |
| [The Multihop Layer](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-24-rene-pickhardt-multihop-in-lightning/) | 80 |
| [The other layers \(base and transport\)](https://btctranscripts.com/chaincode-labs/chaincode-residency/2019-06-24-fabrice-drouin-base-and-transport-layers-of-lightning-network/) | 25 |
| [Message format](https://github.com/lightning/bolts/blob/master/01-messaging.md#lightning-message-format) | 10 |
| [Ok to be odd](https://github.com/lightning/bolts/blob/caae842bfcadd144ab3ec7ce74c317dca07ac78c/00-introduction.md#its-ok-to-be-odd) | 5 |
| [TLV streams](https://github.com/lightning/bolts/blob/master/01-messaging.md#type-length-value-format) | 15 |
| [Feature bits](https://github.com/lightning/bolts/blob/master/09-features.md) | 15 |
| [Diffie–Hellman key exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) | 15 |
| [How and when do I use HMAC?](https://security.stackexchange.com/questions/20129/how-and-when-do-i-use-hmac) | 15 |
| [Lightning transactions: from Zero to Hero \(optional\)](https://github.com/t-bast/lightning-docs/blob/master/lightning-txs.md) | 60+ |

## Discussion Questions

1. How would an offline vending machine work?

### A walk through the layers of Lightning

1. How does the LN-Penalty mechanism currently leak out of the update layer?

### Creating a channel

1. What factors should be considered before opening a Lightning channel with a peer?

### The Update Layer

1. How would switching to PTLCs affect the update layer?
2. If LN were to upgrade the update layer, would the network need to end-to-end upgrade?
3. Why are the second stage HTLC transactions not part of the commitment transaction?

### The Transfer Layer

1. Explain how the timeout mechanism works for in-flight HTLCs?
2. How is the payment hash sent to the payer?
3. Can both HTLCs and PTLCs coexist in a channel?
4. What's are the required parts of invoices?

### The Multihop Layer

1. How can nodes that are not always online prevent loss of funds?
2. What are the risks of forwarding below-dust payments?
3. What is the relationship of the revocation keys for multiple subsequent commitment transactions? What would change if revocation keys were independent?
4. How can you send a payment to a node without getting an invoice? What are the tradeoffs of this payment method?
5. Why is a grace period added to the HTLC timeout?
6. What are routing hints and why are they important for private channels? Do they leak privacy?

### Diffie–Hellman key exchange

1. What is a Diffie-Hellman key exchange used for?

### How and when do I use HMAC?

1. What's the difference between a MAC and an HMAC?
2. Where are HMAC and MAC implemented in lightning and why?

