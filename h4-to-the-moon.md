
### Homework [h4 - To the moon!](https://terokarvinen.com/trust-to-blockchain/#h4)
#### x) Summaries

###### Reference: Nakamoto 2008, [Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)

1. The current electronic payment system relies on trusted financial institutions, but suffers from transaction reversibility, high costs, and fraud risk. The proposed solution is a cryptographic, peer-to-peer payment system using a distributed timestamp server to provide proof of transaction order, eliminating the need for third-party intermediaries and protecting against fraud.
2. An electronic coin is a chain of digital signatures, where each owner transfers the coin by signing the previous transaction and the next owner's public key. To prevent double-spending without relying on a central authority, the system requires all transactions to be publicly announced and participants must agree on a single order history.
3. Timestamps works by hashing blocks of data and publishing these hashes. Each timestamp incorporates the previous timestamp's hash, creating a chain where each new entry reinforces all previous ones.
4. The distributed timestamp server uses a proof-of-work system where miners scan for a hash with a certain number of leading zeros. This process requires significant computational effort but is easy to verify. The longest chain with the most proof-of-work is considered the valid history, and modifying past blocks becomes computationally impractical.
5.  The network operates as follows: nodes broadcast new transactions, collect them into blocks, compete to solve proof-of-work puzzles, and broadcast solved blocks. Nodes accept valid blocks and build on the longest chain. If competing blocks emerge, nodes work on the first received but keep alternatives until one chain becomes longer. Transactions and blocks only need to reach many nodes, not all, for the system to function.
6.  The first transaction in each block creates new coins as a reward for the block creator. This reward encourages people to support the network. It also provides a way to distribute new coins, since there is no central authority to issue them. The reward can also come from transaction fees once enough coins are already in circulation. The rewards encourage people to follow the rules, because even if someone has more computing power than everyone else, they would make more money by earning rewards than by trying to undo transactions and damage the system.

---

#### a) Wallet

Creating a BitCoin testnet wallet Electrum
```
sudo apt-get update
sudo apt-get install electrum
```

The **default_wallet** is created:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/a1.JPG" width="500">


---

#### b) Faucet

Creating a request to receive fake money:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/b1.JPG" width="500">

Went to the the [https://coinfaucet.eu/en/btc-testnet/](https://coinfaucet.eu/en/btc-testnet/)

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/b2.JPG" width="500">

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/b3.JPG" width="500">

Getting the money to the wallet!

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/b4.JPG" width="500">

---

#### c) Giveway

Creating **second_wallet**:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/c1.JPG" width="500">

Creating a request to receive fake money:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/c2.JPG" width="500">

Sending money from the **default_wallet** to the **second_wallet**. I struggled with this, getting errors while trying to adjust the settings. 

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/c3.JPG" width="500">
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/c4.JPG" width="500">

Finally, I was able to send money:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/c5.JPG" width="500">
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/c6.JPG" width="500">

---

#### d) Recycle

Went again to the the [https://coinfaucet.eu/en/btc-testnet/](https://coinfaucet.eu/en/btc-testnet/) and got the address:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/d1.JPG" width="500">

Sent all the money back:

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/d2.JPG" width="500">
<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/d3.JPG" width="500">


---

#### e) Explorer

###### Reference: [Block 870908](https://blockstream.info/block/000000000000000000027c905a0596fc34307dcd488985324b29e7ba2cda239d)


<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/e1.JPG" width="800">

| Field  | Description  |
|--------|--------------|
|**Height**|  Position of a block in the blockchain|
|**Status**|"In best chain (5 confirmations)" - This means the block is part of the main blockchain and has been confirmed by 5 subsequent blocks, indicating it's very secure|
|**Timestamp**| When the block was created|
|**Size**| The actual size of the block data |
|**Virtual Size**|The size used for fee calculations|
|**Weight Units**| A measure used to calculate block weight for scaling purposes|
|**Version**| Block version number|
|**Merkle Root**| A hash that represents all transactions in the block|
|**Bits**|A compact representation of the current mining difficulty target|
|**Difficulty**|The mining difficulty at the time this block was mined|
|**Nonce**| The number miners changed to find a valid block hash|

<br/>

<img src="https://github.com/northernlady/Trust-to-Blockchain-2024/blob/main/pics/h4/e2.JPG" width="800">

| Field  | Description  |
|--------|--------------|
|	0.26228388 BTC| The transaction amount|
|	Transaction ID | A long hexadecimal string that uniquely identifies this transaction|


###### Reference: [https://learnmeabitcoin.com/technical/](https://learnmeabitcoin.com/technical/)
###### Reference: [https://river.com/learn/terms/](https://river.com/learn/terms/)
---

#### f) RogeCoin

###### Reference: [If Cryptocurrency Was Honest | Honest Ads](https://www.youtube.com/watch?v=GUs5y9leCyA)

*"Cryptocurrency is easier to lose — forget your password, get hacked, or fall victim to a scammer."*
### +
- [Mt. Gox hack lost 850,000 BTC in 2014](https://trustwallet.com/blog/mt-gox-explained)
- [QuadrigaCX CEO death resulted in $190M loss](https://www.nortonrosefulbright.com/en/knowledge/publications/168bc350/quadriga-bankruptcy)

  Quadriga stored most of its cryptocurrency deposits in digital “cold wallets” on the harddrive of encrypted laptop, which were inaccessible after his death.
- No central authority for password recovery
- Phishing scams are common 
### -
- Traditional banks also face cyber threats
- Multi-signature wallets add safety layers
- Modern exchanges offer strong security features

 <br/>

*"Cryptocurrency is more volatile. As an investment, it could triple in value overnight or plummet to total worthlessness."*
### + 
- [Bitcoin dropped from $69,000 to $16,000 in 2022](https://www.reuters.com/technology/cryptoverse-bye-bye-year-that-broke-bitcoin-2022-12-20/)
- Daily price swings are common
### -
- Traditional markets can also be volatile (2008 crisis)
- [Some stablecoins maintain steady value](https://center-forward.org/basic/the-stability-of-stablecoin/)
- Volatility has decreased as the market matures
- Can be seen as a feature for traders

<br/>
  
*"Cryptocurrency can be banned in some countries."*
### +
- [China banned crypto trading in 2021](https://www.investopedia.com/news/price-cryptocurrencies-totally-dependent-china/)
- [Some banks restrict crypto transactions](https://plasbit.com/crypto-basic/why-wont-my-card-let-me-buy-crypto)
### -
- Complete bans are hard to enforce
- [El Salvador made Bitcoin legal tender](https://www.science.org/doi/10.1126/science.add2844)
- P2P trading continues despite bans

<br/>

*"Cryptocurrency harms the environment significantly."*
### +
- Bitcoin mining uses more energy than some countries
- High carbon footprint of mining
### -
- [Many miners use renewable energy](https://ezblockchain.net/article/why-green-power-sources-matter-for-bitcoin-miners/)
- Traditional banking also has environmental costs

<br/>

*"Cryptocurrency cannot be exchanged for the vast majority of goods and services."*
### +
- Few physical stores accept cryptocurrency
### -
- Growing acceptance [(Tesla)](https://www.bbc.com/news/business-60001144)
- [Payment processors like BitPay](https://bitpay.com/directory/)
<br/>

*"Real money will become worthless the moment the government collapses — which is bound to happen any century now — but cryptocurrency will forever retain its value."*
### +
- Decentralized nature
- Not dependent on government
- Historical examples of currency collapses (Zimbabwe, Venezuela)
### -
- Requires functioning internet and electricity
