# Some Responses to the Discussion Questions

### Balance Probing Attack
Q: It sounds like randomly denying a percentage of payment requests would be an efective countermeasure. Outside of the potential loss of routing fees, are there any other downsides?  
A: It is not a good solution. Aside from loss of routing fees (if everyone does it equally that would not even be the case actually), the downsides are: A) Increase in routing failures for all users which leads to worse UX which needs to be much improved already. Setting that parameter "right" would also be really hard as number of hops vary a lot from payment to payment. B) It would not really hinder analysis. If routes still go through eventually the attacker just needs to run his analysis/send fake payment requests a few more times and would still get to the same result. (FJ)
