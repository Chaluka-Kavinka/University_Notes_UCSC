# 1. Characteristics of Digital Payments

Digital payments are categorized by three main properties: the **type of payment**, **where the money is (authorization)**, and the **time of payment** relative to the purchase.

- **Cash:** Money stays with the customer; payment happens at purchase.
- **Debit Card:** Money is in the bank; payment happens at purchase.
- **Credit Card:** Money is in the bank; payment happens _after_ purchase.
- **Pre-paid/Subscription:** Money is with the merchant; payment happens _before_ purchase.

# 2. Credit Card Payment Protocols

Securing credit card transactions over the internet involves several layers of protection:

- **TLS (Transport Layer Security):** While not a payment protocol itself, it is the most common method for providing privacy and server authentication when transmitting sensitive card data.
- **3-D Secure:** A modern protocol that authenticates the user in real-time by requiring them to answer a challenge from their issuing bank.
    - **Benefits:** Increases cardholder confidence and reduces fraudulent/disputed transactions for merchants.
- **Obsolete Protocols:** Older systems like **SET (Secure Electronic Transactions)** and **STT (Secure Transaction Technology)** have been largely replaced due to slow acceptance or complexity.
- **eCheck:** A digitally signed "promise to pay" that extends paper checking practices into the digital age.

# 3. The Shift to Cryptocurrencies

Your sources distinguish between **Digital Cash** (an electronic version of existing currency like USD) and **Digital Currency** (an entirely new currency based on cryptography, such as Bitcoin).

## The Birth of Bitcoin

Proposed by **Satoshi Nakamoto in 2008**, Bitcoin was designed to achieve several goals: secure transfer, anonymity, offline transactions, and protection against double-spending without a central authority.

## Core Mechanics: How it Works

Bitcoin functions through a decentralized architecture:

- **The Blockchain:** A public, shared list of every transaction ever made. Account balances are computed by summing all previous transactions rather than being stored in a central database.
- **Miners and Mining:** Miners use software to solve complex mathematical problems (the Bitcoin algorithm) to verify transactions.
- **Proof of Work (PoW):** A competition where miners find a hash value lower than a specific threshold (T). This proves that a large amount of computational resources (time/energy) was spent, ensuring the network can be trusted without a central bank.
- **Confirmations:** A transaction is typically considered secure after **six successive blocks** are mined, which takes approximately one hour.

# 4. Supply and Economics

- **Finite Supply:** Bitcoin is limited to a maximum of **21 million units**.
- **Halving:** The reward for mining a block (starting at 50 BTC) reduces by 50% every four years to control inflation.
- **UTXO Model:** Instead of traditional accounts, Bitcoin uses an **Unspent Transaction Output** model to track funds and prevent them from being spent twice.

# 5. Security Analysis: Bitcoin vs. Traditional Cash

|Feature|US Dollar (Cash)|Bitcoin|
|---|---|---|
|**Control**|Controlled by the government/central bank.|Controlled by users and the algorithm.|
|**Theft Risk**|Easy to steal by muggers; hard for hackers.|Hard to steal by muggers; easier for hackers.|
|**Traceability**|Hard to trace.|Hard to trace (but every transaction is public).|
|**Refunds**|Non-refundable.|Irreversible (no money-back guarantee).|

# 6. Challenges and Future Outlook

Despite its innovation, Bitcoin faces significant hurdles:

- **Irreversibility:** If you lose your private key, your money is gone forever; there is no central entity to reset a password.
- **Volatility:** The value of the currency can fluctuate drastically.
- **Anonymity:** While identities are pseudo-anonymous, heuristics allow researchers to cluster identities and track spending patterns.
- **Taxation and Regulation:** Many legal questions regarding trade and illicit use remain unanswered.