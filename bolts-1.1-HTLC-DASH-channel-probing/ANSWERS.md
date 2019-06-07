# Some Responses to the Discussion Questions

### Balance Probing Attack
1. It is not a good solution. Aside from loss of routing fees (if everyone does it equally that would not even be the case actually), the downsides are: A) Increase in routing failures for all users which leads to worse UX which needs to be much improved already. Setting that parameter "right" would also be really hard as number of hops vary a lot from payment to payment. B) It would not really hinder analysis. If routes still go through eventually the attacker just needs to run his analysis/send fake payment requests a few more times and would still get to the same result. (FJ)

### Rendezvous Mechanism

3. **Problem:** Sender knows too much about the receiver when routing, since the sender has to select the route.
**Solution:** To remain hidden the receiver decides on the last part of the route: He chooses a random, well connected node as a rendez-vous node RV (i.e. meeting point), where the sender should route to. The receiver passes encrypted routing information for the RV-node in the invoice. The RV-node encrypts the routing information and continues to route to the next hop. The next hop might be the receiver or just one hop on the route chosen by the receiver.
5. The rendezvous node, even if it's a sybil of the sender, should only know the next hop. Onion routing should hide the rest of the route from the rendezvous node to the receiver.

### Submarine swaps
7. No, usually there will be sufficiently large offset between expirations. Of course these are negotiated between the participants but generally that should be the case.
