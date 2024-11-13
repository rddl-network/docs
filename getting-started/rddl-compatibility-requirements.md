---
description: A list of requirements that qualify a device to be RDDL-compatible.
hidden: true
---

# 🤓 Compatibility Requirements

RDDL Network maintains a reference implementation of [Tasmota](https://github.com/rddl-network/Tasmota), supporting all the basic functionalities to participate in the RDDL Network protocol.

* Support of a **unique machine identifier (Machine ID)** in the form of a public-private key pair. This key pair works as the anchor of Trust and can reside in a hardware-based [Trust Anchor](trust-anchor.md) or within a unique firmware.
* **Network configuration** needs to be possible so that the Testnet and Mainnet can be configured for the device:
  * ChainID: the chainid of the network the device is connected against.
  * API: the API of a node or validator
  * Denominator token: TRDDL vs RDDL&#x20;
  * Key initialization: setting of a Mnemonic to recover in the case of disaster recovery.
* **Behavioural configuration**
  * Machine Attestation configuration
  * Asset attestation periodicity
* **Actionability**
  * Export public keys to enable account funding on Planetmint
  * Attest itself to the network
  * Attest assets/CIDs
  * Store CIDs and corresponding data for at least 45 days
  * Implement the [PoPChallenge](https://github.com/rddl-network/Tasmota/blob/rddl-development/tasmota/tasmota\_support/support\_command.ino#L942) command for MQTT/XMPP as defined in the reference implementation at the [RDDL-Tasmota](https://github.com/rddl-network/Tasmota/) repository.
