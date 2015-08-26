## Further Analysis

### Economics of Cross-Witness

If any participant cheats, his money at stake must be enough to cover for all the expenses. The contract denomination must be greater than aggregated transaction costs of all the participants, plus potential arbitration costs. The aggregated costs are proportionate to the number of participants, and therefore there must be a limit to the number of participants for each denomination of smart contract. If the number of people exceeds the contract limit, it might result in shortages/queues. This gives the malicious entities an opportunity to launch DDoS attack. One of the possible solutions: multiple contracts + one "router" contract, through which all the TX must be initiated. RANDAO algorithm should be used to assure, that router contract is fair ("nothing up my sleeve"), and besides, may not be manipulated by miners or anyone else.

### Onion Concept

We assume, that multiple iterations will be necessary to acheive the desired probability of untracebility. If we could do several iterations at once, we might save on transaction costs, execution time, and -- which might be even more important -- mental costs of initiating transaction, choosing the available contract in case of queues, and managing the multiple accounts (although this could be automated, but still requires external overhead).

Here is one of the possible solutions. During the Witness Selection step, everybody should select certain (predefined) number of witnesses, then repeatedly encrypt his data with their public keys, then publish the resulting encrypted data ("onion"). Next step remains the same, except that it must be repeated as many times, as required to "unwind the onion".

### Onion Economics

If the original version of Cross-Witness algorithm runs smoothly, it requires the following transactions: 
- initial money transfer with attached public key
- publication of encrypted dest
- publication of decrypted dest
- signing and dissolution

Now, if we add one extra iteration (in case of two-layer onion), we only add one more TX -- publication of decrypted onion layer. If we add 4 iterations (five-layer onion), the TX costs will only double, but probability of failure will be p^5. However, arbitration costs increase dramatically. So, the economic calculations should be corrected correspondingly. It might also mean, that onion extension will be economically viable only for large denomination contracts.
