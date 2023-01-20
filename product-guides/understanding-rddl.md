# ✅ Understanding RDDL

## How RDDL works

Please read the [Whitepaper](https://rddl.io/whitepaper) of RDDL network to get introduced to all the details and concepts.

RDDL Network is the implementation of a protocol that amongst achieves the following pillars:

1. Connects and notarizes **Layer 0** (industrial and consumer machines) machines and their actions
2. Tokenizes **Layer 0** entities (optional) on Liquid - the Bitcoin sidechain - (**Layer 2**)
3. Rewards oroductivity (if proven) - **Proof of Productivity** (**PoP**) - Liquid - the Bitcoin sidechain - (**Layer 2**)
4. Notarizes data and productivity on Planetmint a **Layer 1** solution

### Prerequesits

In order to connect a machine a RDDL network, a RDDL compatable needs to be attached and connected to the machine (via CAN bus). The RDDL compatable device expects internet access to connect to the RDDL network.&#x20;

The RDDl device has to run the [0x21e8 RDDL Interaction Service](https://github.com/rddl-network/0x21e8). Interaction with the service and RDDL network are usually initiatd by the [rddl-client](https://app.gitbook.com/s/z1rZjBISm39skZ4liGP8/node-setup/run-planetmint-with-all-in-one-docker).

#### Key Ceremony

The machine needs to be provisioned with a secret that will be used to derive public private keypairs and identities for Planetmint and Liquid - just before the first network interactions can take place.

### The Basics

Machines need to be attested on the network before they are able to notarize data and productivity, and participate in the PoP.

### Machine Attestation

The attestation process is executed on the RDDL community device. Detailed information can be found at [machine-attestation.md](../fundamentals/getting-started/machine-attestation.md "mention"). During the initial attestation process of al machine, the specifics about its investment capabilities can be defined. These definitions implicitly define the token issuance process of the machine.&#x20;

### Token Issuance

Amongst others, the following parameters have to be defined for the issuance process

1. **amount** of tokens that are issued e.g. something between 0 and 21 million. 0 is a corner case that indicates that no token will be issued for the given machine.
2. a **ticker**, 3 to 5 ASCII characters in length (e.g. “IPA”), used to denominate the amounts in a recognizable unit,
3. an extended **name**, 5 to 255 ASCII characters in length (e.g. “The RDDL network token”), to give a human readable name to the Issued Assets
4. a **domain** that must be controlled by the issuer (e.g. “liquid.beer”), which is used to tie together all of the above information to the entity that also controls the domain submitted to the registry.
5. the decimal **precision**, mainly useful for issuers. For instance, 2 places of decimal precision would mean that 199 satoshi of the Issued Asset should be interpreted as 1.99 units of the asset

The official documenation about how to [issue tokens on Liquid](https://docs.blockstream.com/liquid/technical\_overview.html#issued-assets) defines what needs to be defined for the machine token in more detail.&#x20;
