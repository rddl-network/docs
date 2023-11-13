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

# 🛠 Tasmota Node Configuration

The nodes come with firmware from [https://github.com/rddl-network/Tasmota](https://github.com/rddl-network/Tasmota) and are compatible with [https://github.com/planetmint/planetmint-go](https://github.com/planetmint/planetmint-go).

Initially, you have to

* Search for the Tasmota nodes' wifi hotspot
* Connect to it
* Configure your wifi (the node IP on your local network should be displayed so that the last step can be ignored)
* Reconnect on your local wifi so you can use the node with internet connectivity.
* Identify the local IP of your Tasmota node and connect to it (e.g. using Nmap to search for IP addresses or look it up on your router/switch)

Having that, you can connect to the node by browsing the IP address with HTTP.

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption></figcaption></figure>

Follow the menu to **Consoles→Console**.

<figure><img src="../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Enter the command **Mnemonic** and store the mnemonic to recover your funds and chain interaction identities later.

<figure><img src="../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Enter the command **PublicKeys** to get to know your addresses and keys.

<figure><img src="../.gitbook/assets/image (30).png" alt=""><figcaption></figcaption></figure>

Optional: Enter the command **MachineCID** to set the MachineCID for the initial MachineToken creation

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Enter the command **PlanetmintAPI** to set the URL to connect to the planetmint blockchain API. [https://testnet-api.rddl.io/](https://testnet-api.rddl.io/) is set as the default value.&#x20;

<figure><img src="../.gitbook/assets/image (31).png" alt=""><figcaption></figcaption></figure>

Go to your Testnet Faucet [https://testnet-faucet.rddl.io/](https://testnet-faucet.rddl.io/) and fund your address (e.g. plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma)

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

The Balance of the account can be inspected via the **Balance** command.

<figure><img src="../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

The Testnet Explorer can also be used to inspect the funds of the account

[https://testnet-explorer.rddl.io/planetmint/accounts/plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma](https://testnet-explorer.rddl.io/planetmint/accounts/plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma)

Restart your node once.&#x20;

The Tasmota can now create, sign and broadcast transactions to the Planetmint Testnet. It does so every 3 minutes or if you execute the **Status 8** command. Machine attestation is performed automatically and can be witnessed by looking at the explorer.

The resulting transaction can be inspected on your account page on the [Testnet Explorer](https://testnet-explorer.rddl.io/planetmint).

{% hint style="info" %}
Be aware: Each transaction will consume 1 PLMNT token.&#x20;
{% endhint %}

