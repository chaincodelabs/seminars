# Some Responses to the Discussion Questions

## Rendezvous Routing

Q: Explain rendezvous routing in plain English.  
A: **Problem:** Sender knows too much about the receiver when routing, since the sender has to select the route.  
**Solution:** To remain hidden the receiver decides on the last part of the route: He chooses a random, well connected node as a rendez-vous node RV (i.e. meeting point), where the sender should route to. The receiver passes encrypted routing information for the RV-node in the invoice. The RV-node encrypts the routing information and continues to route to the next hop. The next hop might be the receiver or just one hop on the route chosen by the receiver.

Q: Would it make sense to chain multiple rendezvous meeting points?  
A: The rendezvous node, even if it's a sybil of the sender, should only know the next hop. Onion routing should hide the rest of the route from the rendezvous node to the receiver.

## Watchtower

Q: How do watchtowers work with non-advertised channels when part of the graph is not known? Or with trampoline when the routing calculation is outsourced?  
A: Channels are not relevant to watchtowers as they only need to watch the chain for specific closing transactions.
