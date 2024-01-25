---
description: This tutorial configures the Node to connect to the RDDL Testnet.
coverY: 0
layout:
  cover:
    visible: false
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🛠 Configure your Hardware as a Tasmota Node

The nodes come with firmware from [https://github.com/rddl-network/Tasmota](https://github.com/rddl-network/Tasmota) and are compatible with [https://github.com/planetmint/planetmint-go](https://github.com/planetmint/planetmint-go).

Initially, you have to

* Search for the Tasmota nodes' wifi hotspot
* Connect to it
* Configure your wifi (the node IP on your local network should be displayed so that the last step can be ignored)
* Reconnect on your local wifi so you can use the node with internet connectivity.
* Identify the local IP of your Tasmota node and connect to it (e.g. using Nmap to search for IP addresses or look it up on your router/switch)

Having that, you can connect to the node by browsing the IP address with HTTP.

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

Follow the menu to **Consoles→Console**.

<figure><img src="../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

Enter the command **Mnemonic** and store the mnemonic to recover your funds and chain interaction identities later.

<figure><img src="../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

Enter the command **PublicKeys** to get to know your addresses and keys.

<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

Optional: Enter the command **MachineCID** to set the MachineCID for the initial MachineToken creation

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Enter the command **PlanetmintAPI** to set the URL to connect to the planetmint blockchain API. [https://testnet-api.rddl.io/](https://testnet-api.rddl.io/) is set as the default value.&#x20;

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

Ensure that you also define the denomination, notarization periodicity, and the ChainID:

* `PlanetmintDenom plmnt`  Declares the token denomination used on the chain (Testnet).
* `PlanetmintChainID planetmint-testnet-1`  Declares the ChainID of the Testnet.
* `NotarizationPeriodicity 3600` Defines the notarization frequency in seconds. 3600 = 60\*60 seconds and lets the device notarize once an hour.

{% hint style="info" %}
The above three configuration steps are important for firmware upgrades. The default values are set when flashing a new firmware. The parameters must be set explicitly in case of firmware upgrades.
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot from 2023-12-07 12-02-07.png" alt=""><figcaption></figcaption></figure>



Go to your Testnet Faucet [https://testnet-faucet.rddl.io/](https://testnet-faucet.rddl.io/) and fund your address (e.g. plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma)

<figure><img src="../../.gitbook/assets/image (42).png" alt=""><figcaption></figcaption></figure>

The Balance of the account can be inspected via the **Balance** command.

<figure><img src="../../.gitbook/assets/image (52).png" alt=""><figcaption></figcaption></figure>

The Testnet Explorer can also be used to inspect the funds of the account

[https://testnet-explorer.rddl.io/planetmint/accounts/plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma](https://testnet-explorer.rddl.io/planetmint/accounts/plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma)

Restart your node once.&#x20;

The Tasmota can now create, sign and broadcast transactions to the Planetmint Testnet.\
Please attest your machine now with the following command:

`AttestMachine <machine type like fridge> <machine manufacturer like DIY Inc> <CID with additional information>`

&#x20;After a successful attestation, the device will start notarizing consumption/production data. It does so every 60 minutes (3600 seconds) or if you execute the **Notarize** command. Machine attestation is performed automatically and can be witnessed by looking at the explorer.

The resulting transaction can be inspected on your account page on the [Testnet Explorer](https://testnet-explorer.rddl.io/planetmint).

{% hint style="info" %}
Be aware: Each transaction will consume 1 PLMNT token.&#x20;
{% endhint %}

