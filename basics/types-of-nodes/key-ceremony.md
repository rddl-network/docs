---
description: >-
  Takes care of the key and secret initialization for the different types of
  wallets the node supports.
---

# 🔐 Key Ceremony

Keys and, therefore, identities are managed on both node types

1. Tasmota Nodes
2. Validator Nodes

## Tasmota Nodes

Tasmota nodes come with a pre-attested MachineID that enables them to start interacting with the RDDL Network. The MachineID comes as a part of the firmware or is defined with an attached crypto-chip.&#x20;

The keys used to interact with Liquid and Planetmint are created via a key ceremony on the Tasmota Nodes. Details of the process are listed and laid out in the section about [compatible devices](broken-reference).

The key ceremony includes the creation of the following identities:&#x20;

* a keypair to interact on the Liquid network
* a keypair to interact on Planetmint
  * a derived address on Planetmint

RDDL Network lets machines participate as soon as they attest themselves as part of the [Machine Attestation](broken-reference) workflow. Within the process of the machine attestation, the public keys of the machine on Liquid, Planetmint, the Planetmint address and the Machine ID are attested and associated with each other.&#x20;

It is possible to look up and verify if a given public key, address or machine ID belongs to the same machine as another given public key, address or machine ID.&#x20;

The API calls

[/github.com/planetmint/planetmint-go/machine/get\_machine\_by\_public\_key/{publicKey}](https://planetmint-go-testnet-api.rddl.io/github.com/planetmint/planetmint-go/machine/get\_machine\_by\_public\_key)

[/github.com/planetmint/planetmint-go/machine/get\_trust\_anchor\_status/{machineid}](https://planetmint-go-testnet-api.rddl.io/github.com/planetmint/planetmint-go/machine/get\_trust\_anchor\_status/)

can be used for this purpose.

## Validator Nodes

Coming soon.
