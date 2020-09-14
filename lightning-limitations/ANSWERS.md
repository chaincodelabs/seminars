## Some Responses to the Discussion Questions

### Limitations of lightweight clients
Q: As a service, why is it easier to send funds than receive them?  
A: It is far safer because it saves us from monitoring the blockchain and inbound liquidity is necessary to receive funds and we don’t have the tools to address this yet.

### Fee Management
Q: Why would the fundee care about the size the fees if it’s a funder that’s paying the fees?  
A: Because the higher the fee the higher the threshold for HTLC is to be viable. An HTLC is only valuable if it is above the fee or dust limit.

Q: If you disagree about the fees with your peer, how do you negotiate them?  
A: If you disagree about the fees you close the channel there is no negotiation protocol. This is the reason many channels are closed with fees spike.

### Balance Probing Attack
Q: It sounds like randomly denying a percentage of payment requests would be an efective countermeasure. Outside of the potential loss of routing fees, are there any other downsides?  
A: It is not a good solution. Aside from loss of routing fees (if everyone does it equally that would not even be the case actually), the downsides are: A) Increase in routing failures for all users which leads to worse UX which needs to be much improved already. Setting that parameter "right" would also be really hard as number of hops vary a lot from payment to payment. B) It would not really hinder analysis. If routes still go through eventually the attacker just needs to run his analysis/send fake payment requests a few more times and would still get to the same result. (FJ)
