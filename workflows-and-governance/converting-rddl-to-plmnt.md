---
description: >-
  This guide aims to explain the conversion of RDDL to PLMNT tokens on the
  network.
---

# Converting RDDL to PLMNT

## Step by step guide

1. Send funds to rddl-2-plmnt address
   * Testnet address: `tlq1qqvzww4s5203g0jrc4pg7pw5kl0efwlwugw3vlua6mx4akqdvgvsks8mmv7e4yshjzr4l3aykx4umf2zjwchvcdr7swuegnpag`
   * Mainnet address: `lq1qq2zwjllrzsag8u22gqza38ru6pj9sg2fadu5w9sqtl0uketww3wm6wm8j76q63dfywl7sju26d78w78pnkezvq9ayxt49xgu9`
2. Wait for confirmations on liquid
3. Send tx hash to rddl-2-plmnt service with beneficiary in body
   * e.g.: `curl -X POST -H "Content-Type: application/json" -d '{"conversion": {"beneficiary": "plmnt1w5dww335zhh98pzv783hqre355ck3u4w4hjxcx","liquid-tx-hash": "b356413f906468a3220f403c350d01a5880dbd1417f3ff294a4a2ff62faf0839","descriptor": "wpkh([6a00c946/0'/0'/501']02e24c96e967524fb2ad3b3e3c29c275e05934b12f420b7871443143d05ffe11c8)#8ktzldqn"},"signature": "ICucxAHOsf1kanl9UAjxMXemLmnP0deHWwyqdav68e8XCknJeaNBPFl9t7h52Ny1/XNgiQFu8XzrGLM8qahSy38="}' https://testnet-r2p.rddl.io/mint`

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

## Example

Below you can find a curl example for sending a POST request to the rddl2plmnt service on the testnet. Replace `planetmint-address` with your address and with the transaction hash of your liquid transaction to the escrow account.

```
curl -X POST -H "Content-Type: application/json" -d '{"conversion": {"beneficiary": "planetmint-address", "liquid-tx-hash": "transactionhash", "descriptor": "addressderivationdescriptor"}, "signature": "signatureofconversionobject"}' https://testnet-r2p.rddl.io/mint
```
