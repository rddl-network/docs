---
description: >-
  This guide aims to explain the conversion of RDDL to PLMNT tokens on the
  network.
---

# Converting RDDL to PLMNT

## Pre-requirements

* A wallet application (e.g.[Green Wallet](https://blockstream.com/green/)) for transferring the RDDL tokens on the Liquid Network
* RDDL tokens to send
* LBTC tokens to pay for the transaction fees (on the Testnet: [https://liquidtestnet.com/faucet](https://liquidtestnet.com/faucet))
* An authorized recipient (machine) on the planetmint network.

## Step-by-step guide

1.  Query the RDDL 2 PLMNT service of the Testnet or the Maintnet by calling `https://testnet-r2p.rddl.io/receiveaddress/` or `https://r2p.rddl.io/receiveaddress/` with your **planemtint address** appended, e.g. for address _`plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm`_

    this looks as follows [https://testnet-r2p.rddl.io/receiveaddress/plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm](https://testnet-r2p.rddl.io/receiveaddress/plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm)\
    or [https://r2p.rddl.io/receiveaddress/plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm](https://r2p.rddl.io/receiveaddress/plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm).\
    This call will return a JSON object with the following data:\
    `{ "liquid-address": "tlq1qq2e96fx7t0gvtq9lhk3vg7qwf7s08479ap3wqyelp2c4ds9y7wesk97fd0sla2s7qck4ezns3gy6s8h4qw3e2tqkyfnkvxs4u", "planetmint-beneficiary": "plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm" }`
2. Use the wallet of your choice (e.g.[Green Wallet](https://blockstream.com/green/) ) to transfer RDDL tokens on the Liquid network to the liquid-address mentioned above
3. The Liquid address will be supervised for 12 hours, and the funds being received on that address by the next transaction will be converted to PLMNT tokens on planetmint and, after that, transferred to the before-mentioned planetmint address/beneficiary (e.g. plmnt1atfrnm80xyg86s85xp0av2ukap8n4ap7pevptm).

More elaborate documentation about the service and a sequence diagram can be found in its [GitHub repository](https://github.com/rddl-network/rddl-2-plmnt-service).

In essence, the service acts as a bridge between the Liquid blockchain and PlanetMint blockchain, facilitating the minting of PLMNT tokens based on certain conditions met in the Liquid blockchain.
