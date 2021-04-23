# How the layers of Lightning Fit Together

## Reading

| Content                                                                                       | Time  | Tags                    |
|-----------------------------------------------------------------------------------------------|-------|-------------------------|
[A walk through the layers of Lightning](https://diyhpl.us/wiki/transcripts/scalingbitcoin/tel-aviv-2019/edgedevplusplus/lightning-network-layer-by-layer/) | 30 min | LN layers |
[The Update Layer](https://youtu.be/SoFlRCNdqDg) | 60 min | update, video |
[The Transfer Layer](https://youtu.be/CGE8I8L7BAc) | 41 min | transfer, video |
[The Multihop Layer](https://youtu.be/P7I-C0_sijg) | 72 min | multihop, video |
[The other layers (base and transport)](https://youtu.be/wyri7cc83kQ) | 17 min | base, transport, video |
[Diffie–Hellman key exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) | 10 min | Diffie–Hellman, cryptography |
[How and when do I use HMAC?](https://security.stackexchange.com/questions/20129/how-and-when-do-i-use-hmac) | 10 min | HMAC, cryptography |

## Discussion Questions

1. How would an offline vending machine work?

### A walk through the layers of Lightning

1. How does the LN-Penalty mechanism currently leak out of the update layer?

### The Update Layer

1. How would switching to PTLCs affect the update layer?
1. If LN were to upgrade the update layer, to Eltoo for example, would the network need to end-to-end upgrade?
1. Would there ever be a reason to prefer LN-penalty when creating a channel between two Eltoo-capable nodes?
1. Why are the second stage HTLC transactions not part of the commitment transaction?

### The Transfer Layer

1. Explain how the timeout mechanism works for in-flight HTLCs?
1. How is the payment hash sent to the payer?
1. Can both HTLCs and PTLCs coexist in a channel?
1. What's are the required parts of invoices?

### The Multihop Layer

1. How can nodes that are not always online prevent loss of funds?
1. What are the risks of forwarding below-dust payments?
1. What is the relationship of the revocation keys for multiple subsequent commitment transactions? What would change if revocation keys were independent?
1. How can you send a payment to a node without getting an invoice? What are the tradeoffs of this payment method?
1. Why is a grace period added to the HTLC timeout?
1. What are routing hints and why are they important for private channels? Do they leak privacy?

### The other layers (base and transport)

### Diffie–Hellman key exchange

1. What is a Diffie-Hellman key exchange used for?

### How and when do I use HMAC?

1. What's the difference between a MAC and an HMAC?


