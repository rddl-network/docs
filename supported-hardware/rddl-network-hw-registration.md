# RDDL Network HW registration

Every hardware interacting with RDDL Network needs to be attested before being able to start interacting. RDDL Networks assumes that hardware comes with a hardware secure element such as integrate in the [Trust Anchor](onboarding-machines-to-the-rddl-network/trust-anchor.md) and expects that Trust Anchors are registered to the network before interaction starts.&#x20;

Trust Anchors are identified via their a public/private keypair that is provisioned to them and might never change. The public key is registered to the chain via the TrustAnchor Attestation serivce [https://testnet-ta.rddl.io](https://testnet-ta.rddl.io).

The service deploys new random identites to downloaded firmwares and in the case of the testnet, enalbe the registration of public keys in the format of string of characters representing a the [bytes of the public secp256k1 public key](https://github.com/rddl-network/ta\_attest/blob/main/cmd/ta/main.go#L203).

{% hint style="info" %}
The machineID and the corresponding public private key pair are used for the machine on-boarding onto the network. This key pair is unrelated to the key material used to interact with the chain directly (e.g. to sign transactions, hold funds, ...).
{% endhint %}

RDDL Network expects HW OEM vendors to register their devices on chain so that they are able to start interacting after attesting their machines.&#x20;

The RDDL testnet allows a more flexible handling of the machineID in order to ease the on-boarding of new hardware and machines. Details about the workflows can be found at [onboarding Machines.](onboarding-machines-to-the-rddl-network/)
