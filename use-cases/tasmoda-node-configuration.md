---
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

# 🛠 Tasmoda Node configuration

The nodes come with a firmware from [https://github.com/rddl-network/Tasmota](https://github.com/rddl-network/Tasmota) and are compatible to [https://github.com/planetmint/planetmint-go](https://github.com/planetmint/planetmint-go).

Initially, you have to

* search for the tasmota nodes wifi hot spot
* connect to it
* configure your own wifi
* and reconnect on your local wifi so that the node has internet connectivity
* identify the local IP of your tasmota node and connect to it (e.g. using nmap to search for IP addresses or look it up on your router/switch)

Having that you are able to connect to the node by browsing the IP address with HTTP

<div>

<img src="https://www.notion.so/rddlnetwork/Using-a-Tasmota-Node-a7ad083c54fa401da2c61622e9052897?pvs=4#3d221cb27da845269da202bf5fdc6194" alt="Untitled">

 

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

</div>

Follow the menu to Consoles→Console

<div>

<img src="https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a5443cc6-a507-4c93-a714-ad3d6caad7bc/Untitled.png" alt="Untitled">

 

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

</div>

Enter the command **Mnemonic**

<div>

<img src="https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c704eaef-c231-49f5-8340-e9f9c5e2583a/Untitled.png" alt="Untitled">

 

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

</div>

Enter the command **PublicKeys** to get to know your addresses and keys

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Optional: Enter the command **MachineCID** to set the MachineCID for the initial MachineToken creation

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Enter the command **PlanetmintAPI** to set the URL to connect to the planetmint blockchain API

Go to your Planetmint Faucet \<planetmint-node>:4500 and fund your address (e.g. cosmos1vkvcqr5vwtdjrtr7vq3e0twfgqejyjd8exg740)

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Go to

* the planetmint blockchain API (e.g. [http://0.0.0.0:1317/#/Query/CosmosAuthV1Beta1Accounts](http://0.0.0.0:1317/#/Query/CosmosAuthV1Beta1Accounts))
* query all accounts and
* search for your address cosmos1vkvcqr5vwtdjrtr7vq3e0twfgqejyjd8exg740

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Take the account\_number from there (in this case **9**) and execute the **AccountID 9** command to set the account ID on your tasmota device

<figure><img src="../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

The tasmota is now able to create, sign and broadcast transactions to your planetmint node.

It does so every 3 minutes or if you execute the **Status 8** command

The machine attestation transaction can now be inspected via the [http://0.0.0.0:1317/#/Query/PlanetmintgoMachineGetMachineByPublicKey](http://0.0.0.0:1317/#/Query/PlanetmintgoMachineGetMachineByPublicKey) blockchain API call:

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

You can also see that each transaction will consume 2 tokens:

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>
