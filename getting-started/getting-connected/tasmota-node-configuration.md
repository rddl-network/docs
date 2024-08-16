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

# 🛠️ Configure your Hardware as a Tasmota Node

The nodes come with firmware from [https://github.com/rddl-network/Tasmota](https://github.com/rddl-network/Tasmota) and are compatible with [https://github.com/planetmint/planetmint-go](https://github.com/planetmint/planetmint-go).

Initially, you have to

* Search for the Tasmota nodes' wifi hotspot
* Connect to it
* Configure your wifi (the node IP on your local network should be displayed so that the last step can be ignored)
* Reconnect on your local wifi so you can use the node with internet connectivity.
* Identify the local IP of your Tasmota node and connect to it (e.g. using Nmap to search for IP addresses or look it up on your router/switch)

Having that, you can connect to the node by browsing the IP address with HTTP.

<figure><img src="../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

### Get to know your machine

Follow the menu to **Consoles→Console**.

<figure><img src="../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

Enter the command **Mnemonic** and store the mnemonic to recover your funds and chain interaction identities later.

<figure><img src="../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

Enter the command **PublicKeys** to get to know your addresses and keys.

<figure><img src="../../.gitbook/assets/image (49).png" alt=""><figcaption></figcaption></figure>

### Setting PlanetmintAPI & Chain-ID

Enter the command **PlanetmintAPI** to set the URL to connect to the planetmint blockchain API. [https://testnet-api.rddl.io/](https://testnet-api.rddl.io/) is set as the default value. If you want you node to interact with the mainnet set it to [https://api.rddl.io/](https://api.rddl.io/)

<figure><img src="../../.gitbook/assets/image (50).png" alt=""><figcaption></figcaption></figure>

Ensure that you also define the denomination, notarization periodicity, and the ChainID:

* `PlanetmintDenom plmnt`  Declares the token denomination used on the chain (Testnet).
* `PlanetmintChainID planetmint-testnet-1` or `PlanetmintChainID planetmint-mainnet-1` Declares the ChainID of the Testnet/Mainnet.
* `NotarizationPeriodicity 3600` Defines the notarization frequency in seconds. 3600 = 60\*60 seconds and lets the device notarize once an hour.

{% hint style="info" %}
The above three configuration steps are important for firmware upgrades. The default values are set when flashing a new firmware. The parameters must be set explicitly in case of firmware upgrades.
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot from 2023-12-07 12-02-07.png" alt=""><figcaption></figcaption></figure>

### Create an account for your machine on chain

Next, you need to create the machine account's own chain. This is necessary so that the machine can attest itself to the chain, which uses 1 PLMNT. After your machine is attested and activated, it will receive 8800 PLMNTs, which is enough to notarize data for a year if the notarization periodicity is set to 1 hour.

You can achieve this in the following ways:

1. Testnet only: Fund the machine address by sending PLMNT tokens to the address (e.g., plmnt10addjzn66e0u9kfy4ku307zjd0z3dyqd45gjh7)
2. Issue the following  command on Tasmota \
   `CreateAccount plmnt10addjzn66e0u9kfy4ku307zjd0z3dyqd45gjh7`
3. Send a request create-account  to the Trust Anchor Registration Service like :&#x20;

```
 curl -X POST -H "Content-Type: application/json" -d "{\"machine-id\":\"03a0aa69aaf9e4817c02b3d2b649efa76a8fe52013a43f933c65df9c3a4400040c\", \"plmnt-address\":\"plmnt10addjzn66e0u9kfy4ku307zjd0z3dyqd45gjh7\", \"signature\":\"0f254d93269468f5c0269430252aca8fa43af7a7095b07f26b4187e8abd747306803be9b1f1eee9bfb8347de279aa3b8fa8975c5c9b8faea80ff00cfa7ac8989\"}" https://testnet-ta.rddl.io/create-account
```

**Testnet only:** Alternatively, if you are on the testnet you can go to the Testnet Faucet [https://testnet-faucet.rddl.io/](https://testnet-faucet.rddl.io/) and fund your address (e.g. plmnt1xjfmfeuu533h40sz0jcjkc5727ph3cy8r0d4ma)

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

### Setting up MQTT for Participating in PoPs

Go to **Configuration -> Configure MQTT** and set the credentials provided [here](https://docs.rddl.io/rddl-network/basics/chains#machine-2-machine-network).&#x20;

Depending on the _network_ you are using set the following host and port found [here](https://docs.rddl.io/rddl-network/basics/chains#links) and tick the checkbox for **MQTT TLS.**

For **Client** and **Topic** set your machine's address.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Troubleshooting

#### Not finding your device on the network:

* If you cannot fund your account (i.e.: via `ta(-testnet).rddl.io/create-account` Or funding your account manually). Check if your machine address exists on the correct network under the following link:\
  [https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetMachineByAddress](https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetMachineByAddress) or [https://api.rddl.io/#/Query/PlanetmintgoMachineGetMachineByAddress](https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetMachineByAddress)\
  If not, you probably downloaded firmware for the wrong network, as your firmware will be attested for either the testnet or mainnet. Check the links posted [here](https://docs.rddl.io/rddl-network/getting-started/getting-connected/getting-a-firmware).

**Unable to connect to the MQTT service - connection error 62**

* The Tasmota version rddl-v0.43.0 and below do not recognize the newest Let's Encrypt root certificates and drop the TLS connection because of an untrusted CA. Executing the following command on the command line \
  `setoption132 1`\
  will enable certificate verification but disable the AWS IoT and Let's Encrypt certificate check. This will solve the issue as the certificates are valid, and the connection will again work as expected.&#x20;
