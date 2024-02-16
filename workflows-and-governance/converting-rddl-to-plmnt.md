---
description: >-
  This guide aims to explain the conversion of RDDL to PLMNT tokens on the
  network.
---

# Converting RDDL to PLMNT

## Pre-requirements

* Green Wallet app (Desktop, Android or iOS) for transferring the RDDL tokens
* Green Wallet CLI for creating the signature: [https://github.com/Blockstream/green\_cli](https://github.com/Blockstream/green\_cli)
* This PR needs to be merged: [https://github.com/Blockstream/gdk/pull/203](https://github.com/Blockstream/gdk/pull/203)
* RDDL tokens to send
* LBTC tokens to pay the fees: [https://liquidtestnet.com/faucet](https://liquidtestnet.com/faucet)

## Step by step guide

This guide uses the Liquid Testnet and the TRDDL (RDDL Testnet) token. The mnemonic used is:

```
enough tissue apple festival paper buffalo wine okay omit snack cloth maze
```

First of all create a new receive address. This is necessary because at the time of writing we cannot sign messages from the root account:

<figure><img src="../.gitbook/assets/Screenshot 2024-02-16 at 11.05.08.png" alt=""><figcaption><p>New receive address from which we can sign</p></figcaption></figure>

Here you can see the Green Wallet app containing 800 TRDDL and using address `vjTvU2YDX1ZY4YeauwQm8PDbnbpXyvoPtsVBVRfsu1Ke7Qy7oUMcEKVL682wLbPwHQPvSimM43eACJvD`:

<div>

<figure><img src="../.gitbook/assets/Screenshot 2024-02-16 at 11.09.12.png" alt=""><figcaption><p>Address used in this guide</p></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Screenshot 2024-02-16 at 11.09.07.png" alt=""><figcaption><p>Wallet containing 800 TRDDL and 0.001 L-TEST tokens</p></figcaption></figure>

</div>

Using the same mnemonic leads to the same address in the Green Wallet CLI. This step is crucial, because we need to sign with the same private key with which the TRDDL tokens are send to the RDDL-2-PLMNT service wallet:

```
$ green-cli --network electrum-testnet-liquid getnewaddress
Mnemonic: 
vjTvU2YDX1ZY4YeauwQm8PDbnbpXyvoPtsVBVRfsu1Ke7Qy7oUMcEKVL682wLbPwHQPvSimM43eACJvD
```

### Send funds to RDDL-2-PLMNT service wallet

Now we need to send the amount of TRDDL tokens that we want to convert to PLMNT tokens.&#x20;

* Testnet address: `tlq1qqvzww4s5203g0jrc4pg7pw5kl0efwlwugw3vlua6mx4akqdvgvsks8mmv7e4yshjzr4l3aykx4umf2zjwchvcdr7swuegnpag`
* Mainnet address: `lq1qq2zwjllrzsag8u22gqza38ru6pj9sg2fadu5w9sqtl0uketww3wm6wm8j76q63dfywl7sju26d78w78pnkezvq9ayxt49xgu9`

<div>

<figure><img src="../.gitbook/assets/Screenshot 2024-02-16 at 11.16.12.png" alt=""><figcaption><p>Transaction ID</p></figcaption></figure>

 

<figure><img src="../.gitbook/assets/Screenshot 2024-02-16 at 11.17.08.png" alt=""><figcaption><p>Transaction details with unblinded link</p></figcaption></figure>

</div>

Wait for confirmations on liquid. You can check the unblinded transaction here: [https://blockstream.info/liquidtestnet/tx/4af8236a2acaa078bf31d416a43a77753212cd1705fddd00b2516655ffd4c00d#blinded=80000000000,7add40beb27df701e02ee85089c5bc0021bc813823fedb5f1dcb5debda7f3da9,8c706cd4a05e88d9b1b71a1f1a1bd659f132738cec6e7cc038024645f00c67df,b8f718d53a767180f9491ad8817e03f707f50c3ea730c268123128dcc6d89d6e,100000,144c654344aa716d6f3abcc1ca90e5641e4e2a7f633bc09fe3baf64585819a49,f3dd53caa159b51141c47fe385f31f2dc9eeaf3ededfbda87999b50e7500b8cd,5862ccb47e81cbf71d2c6a175644e8b4e954e0e497269785c8049049cdef0370,70000000000,7add40beb27df701e02ee85089c5bc0021bc813823fedb5f1dcb5debda7f3da9,e4aad39d452c1f233cf079d4650ac910338d4557803a21e47ad5713af0ee0385,a14c022880c7bc889a727147aac7b0ae88f8252de0856948ecac77dec1827c96,99610,144c654344aa716d6f3abcc1ca90e5641e4e2a7f633bc09fe3baf64585819a49,0f2fc78ae655d1da04aa4aaff12b63d7dd706fc268f68d5be5d3596cd67d04ef,4b9027ddd5c87e9dbaa18f88f271022ebcec7143c57dffc5e8be3e268d3b0968](https://blockstream.info/liquidtestnet/tx/4af8236a2acaa078bf31d416a43a77753212cd1705fddd00b2516655ffd4c00d#blinded=80000000000,7add40beb27df701e02ee85089c5bc0021bc813823fedb5f1dcb5debda7f3da9,8c706cd4a05e88d9b1b71a1f1a1bd659f132738cec6e7cc038024645f00c67df,b8f718d53a767180f9491ad8817e03f707f50c3ea730c268123128dcc6d89d6e,100000,144c654344aa716d6f3abcc1ca90e5641e4e2a7f633bc09fe3baf64585819a49,f3dd53caa159b51141c47fe385f31f2dc9eeaf3ededfbda87999b50e7500b8cd,5862ccb47e81cbf71d2c6a175644e8b4e954e0e497269785c8049049cdef0370,70000000000,7add40beb27df701e02ee85089c5bc0021bc813823fedb5f1dcb5debda7f3da9,e4aad39d452c1f233cf079d4650ac910338d4557803a21e47ad5713af0ee0385,a14c022880c7bc889a727147aac7b0ae88f8252de0856948ecac77dec1827c96,99610,144c654344aa716d6f3abcc1ca90e5641e4e2a7f633bc09fe3baf64585819a49,0f2fc78ae655d1da04aa4aaff12b63d7dd706fc268f68d5be5d3596cd67d04ef,4b9027ddd5c87e9dbaa18f88f271022ebcec7143c57dffc5e8be3e268d3b0968)

<figure><img src="../.gitbook/assets/Screenshot 2024-02-16 at 11.19.49.png" alt=""><figcaption><p>Our transaction with some confirmations</p></figcaption></figure>

### Sign the request body

Now we need to tell the RDDL-2-PLMNT service which address the PLMNT tokens shall receive. To prove that we are actually eligible convert the RDDL to PLMNT tokens, we need to sign the request with the same private key from which we send the TRDDL tokens in the first place. Here is where the `green-cli` comes into play.  Note: work is currently done to integrate this functionality into the Green Wallet app.

Let's collect the necessary parts which we need to send to the RDDL-2-PLMNT service:

1. Beneficiary address (the planetmint address that shall receive the PLMNT), e.g.: `plmnt1w5dww335zhh98pzv783hqre355ck3u4w4hjxcx`
2. Liquid transaction ID from the _**PREVIOUS**_ block. From the example above click on the transaction ID next to the 800 TRDDL and copy it: `685c19345cfa77df63685da58abeb035b45fe065e77f14445fc50c8be43291cf`
3. The address descriptor that we need to verify you on our side. From the Green Wallet CLI find our address:

```
$ green-cli --network electrum-testnet-liquid getpreviousaddresses
{
  "list": [
    {
      "address": "vjTvU2YDX1ZY4YeauwQm8PDbnbpXyvoPtsVBVRfsu1Ke7Qy7oUMcEKVL682wLbPwHQPvSimM43eACJvD",
      ...
      "is_internal": false,
      "pointer": 1,
      ...
      "subaccount": 0,
      ...
      "unconfidential_address": "8sAcNCGwwCkgKbczgYJeSZ1DDecELYM6vn",
      ...
```

We are interested in `subaccount`, `is_internal` and `pointer`. You can double check the `unconfidential_address` appearing in the transaction, which you copied in the previous step.

Get the `subaccount 0`, copy the descriptor for `is_internal`` ``false` (= `0`), replace the asterisk with the `pointer 1` and remove the checksum (`#...`):

```
$ green-cli --network electrum-testnet-liquid getsubaccount 0
{
  ...
  "core_descriptors": [
    "sh(wpkh([4255a991/49'/1'/0']tpubDC2Q4xK4XH72HaaoYXZHMhUyzTK1Z8UqoxmhuRcez6rfnXTk8oth7p73Hu2QjeZjDywo61iBr8PFEpFcwGundFUYh5KQuTLix5gAGfg9zkN/0/*))#aatw8u3k",
    "sh(wpkh([4255a991/49'/1'/0']tpubDC2Q4xK4XH72HaaoYXZHMhUyzTK1Z8UqoxmhuRcez6rfnXTk8oth7p73Hu2QjeZjDywo61iBr8PFEpFcwGundFUYh5KQuTLix5gAGfg9zkN/1/*))#gu9clryf"
  ],
  ...
```

This gives us:

```
sh(wpkh([4255a991/49'/1'/0']tpubDC2Q4xK4XH72HaaoYXZHMhUyzTK1Z8UqoxmhuRcez6rfnXTk8oth7p73Hu2QjeZjDywo61iBr8PFEpFcwGundFUYh5KQuTLix5gAGfg9zkN/0/1))
```

Now we have everything to craft the request body and sign it:

```
$ REQUEST_BODY="{\"beneficiary\":\"plmnt1w5dww335zhh98pzv783hqre355ck3u4w4hjxcx\",\"liquid-tx-hash\":\"685c19345cfa77df63685da58abeb035b45fe065e77f14445fc50c8be43291cf\",\"descriptor\":\"sh(wpkh([4255a991/49'/1'/0']tpubDC2Q4xK4XH72HaaoYXZHMhUyzTK1Z8UqoxmhuRcez6rfnXTk8oth7p73Hu2QjeZjDywo61iBr8PFEpFcwGundFUYh5KQuTLix5gAGfg9zkN/0/1))\"}"
$ green-cli --network electrum-testnet-liquid signmessage vjTvU2YDX1ZY4YeauwQm8PDbnbpXyvoPtsVBVRfsu1Ke7Qy7oUMcEKVL682wLbPwHQPvSimM43eACJvD ${REQUEST_BODY}
{
  "signature": "IFlTqZaQpyJ8l8qpqtK52b88h1AQT6PKTHCKDOHiXtdiWSoAkoUIToZa4ouMWfVTY8/4k6MOv8zue9ZhDw9Dcj4="
}
```

### Send everything to RDDL-2-PLMNT service

```
$ CONVERSION="{\"conversion\":${REQUEST_BODY},\"signature\":\"IFlTqZaQpyJ8l8qpqtK52b88h1AQT6PKTHCKDOHiXtdiWSoAkoUIToZa4ouMWfVTY8/4k6MOv8zue9ZhDw9Dcj4=\"}"
$ echo ${CONVERSION}|jq
{
  "conversion": {
    "beneficiary": "plmnt1w5dww335zhh98pzv783hqre355ck3u4w4hjxcx",
    "liquid-tx-hash": "685c19345cfa77df63685da58abeb035b45fe065e77f14445fc50c8be43291cf",
    "descriptor": "sh(wpkh([4255a991/49'/1'/0']tpubDC2Q4xK4XH72HaaoYXZHMhUyzTK1Z8UqoxmhuRcez6rfnXTk8oth7p73Hu2QjeZjDywo61iBr8PFEpFcwGundFUYh5KQuTLix5gAGfg9zkN/0/1))"
  },
  "signature": "IFlTqZaQpyJ8l8qpqtK52b88h1AQT6PKTHCKDOHiXtdiWSoAkoUIToZa4ouMWfVTY8/4k6MOv8zue9ZhDw9Dcj4="
}
$ curl -X POST -H "Content-Type: application/json" -d '${CONVERSION}' https://testnet-r2p.rddl.io/mint
```

## How it works

The `rddl2plmnt` service provides a REST endpoint that expects a POST request with a beneficiary address. Here's a simplified breakdown of what the service does:

1. **Receive Conversion object and signature:**
   * The service receives a POST request containing a conversion object with a beneficiary address, a liquid transaction hash and a descriptor to the derive the liquid address as well as signature of the conversion object.
2. **Verify signature**
   * The public key in the descriptor is used to verify the signature of the conversion object. **Important:** The signature must be created with the same private key that signed the liquid transaction in order to verify that the mint request is actually from the issuer sending the RDDL token.
3. **Check Mint Request Existence:**
   * It checks if a mint request for the given transaction hash (tx) has already been issued. If yes, it responds indicating that the minting has already been done.
4. **Check Liquid Transaction:**
   * If no mint request exists, the service checks if the corresponding transaction hash is present on the Liquid side of the blockchain.
5. **Verify RDDL Amount in Liquid Transaction:**
   * If the transaction is on Liquid, it checks if the amount of the RDDL asset in that transaction is greater than zero.
6. **Calculate PLMNT Amount:**
   * If the RDDL amount is valid, the service calculates the equivalent amount in PLMNT using a predetermined conversion rate.
7. **Issue Mint Request to PlanetMint:**
   * The service then sends a mint request to the PlanetMint blockchain, including details such as the Liquid transaction hash, the calculated amount of PLMNT, and the beneficiary address on the PlanetMint side.

In essence, the service acts as a bridge between the Liquid blockchain and PlanetMint blockchain, facilitating the minting of PLMNT tokens based on certain conditions met in the Liquid blockchain.
