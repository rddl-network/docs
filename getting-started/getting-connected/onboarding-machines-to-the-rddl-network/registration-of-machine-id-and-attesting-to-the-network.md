---
hidden: true
---

# ®️ Registration of Machine ID and Attesting to the Network

Every piece of hardware interacting with RDDL Network needs to be attested before it can start interacting. RDDL Networks assumes that hardware comes with a hardware secure element, such as integrated into the Trust Anchor, and expects that Trust Anchors are registered to the network before the interaction starts.&#x20;

Trust Anchors are identified via a public/private key pair that is provisioned to them and might never change. The public key is registered to the chain via the TrustAnchor Attestation service: https://testnet-ta.rddl.io.

The service deploys new random identities to downloaded firmware and, in the case of the testnet, allows the registration of public keys in the format of a string of characters representing the [bytes of the public secp256k1 public key](https://github.com/rddl-network/ta\_attest/blob/main/cmd/ta/main.go#L203).

{% hint style="info" %}
The machineID and the corresponding public-private key pair are used for the machine's onboarding onto the network. This key pair is unrelated to the key material used to interact with the chain directly (e.g., to sign transactions, hold funds, etc.).
{% endhint %}

RDDL Network expects HW OEM vendors to register their devices on the chain so that they can start interacting after attesting their machines.&#x20;

The RDDL testnet allows more flexible handling of the machineID to ease the onboarding of new hardware and machines. Details about the workflows can be found at Connecting Your[ Machine to the Network](./)[.](./)

***

If you want to work with the Testnet **AND** The Mainnet, you can use Machines with unique Firmware or Machines with a Secure Element. If you want to learn with the Testnet, you can simply use Machines with a self-registered Public Key. Be aware that these Machines are not supported on the Main net.\


## Testnet + Mainnet:

### 1. Machines with unique Firmware

The sequence diagram below shows how a unique firmware is created. The randomly inserted private injected key makes the firmware unique. The corresponding public key is notarized on Planetmint after that.

```mermaid
sequenceDiagram
    participant Operator
    participant Machine
    participant TA-Attest
    participant Planetmint
    Operator->>TA-Attest: query Firmware with pre-attested MACHINE ID
    TA-Attest->>TA-Attest: generate new random MACHINE ID public/private keys
    TA-Attest->>TA-Attest: patch firmware with private key
    TA-Attest->>Planetmint: attest TA identity (public key)
    TA-Attest->>Operator: return unique firmware
    Operator->>Machine: flash firmware
    Operator->>Machine: configure Machine: Mnemonic, PublicKeys, Planetmint-API, -Denom, -ChainID
    alt fund machine
    Operator->>Planetmint: fund machine
    else create account
    Operator->>TA-Attest: create account: MachineID, MachineIDSignature, PlanetmintAddress
    TA-Attest->>Planetmint: request TA status
    Planetmint-->>TA-Attest: TA status {activated: true/false}
    TA-Attest->>Planetmint: fund machine for self attestation
    end
    Machine->>Planetmint: Attest machine
    loop 
    Machine->>Planetmint: notarize CID/asset
    Machine-->Planetmint: Proof of Productivity
    end
```

The Tasmota reference implementation can be downloaded from

* [https://testnet-ta.rddl.io/firmware/esp32](https://testnet-ta.rddl.io/firmware/esp32) for ESP32 devices
* [https://testnet-ta.rddl.io/firmware/esp32c3](https://testnet-ta.rddl.io/firmware/esp32c3) for ESP32C3 devices.

The download will include the previously mentioned steps.&#x20;

A call to [https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetTrustAnchorStatus](https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetTrustAnchorStatus) with your machine ID, the public key of the TA, shows if your public key got properly attested and if the corresponding machine has already attested.



{% hint style="info" %}
The machine ID of the RDDL-Tasmota devices is shown by calling _**PublicKeys.**_
{% endhint %}

### 2. Machines with Secure Element

```mermaid
sequenceDiagram
    participant Operator
    participant 3rdPartyOEM
    participant Machine
    participant TA-Attest
    participant Planetmint
    3rdPartyOEM->>TA-Attest: Attest Machine ID/public key
	  TA-Attest->>Planetmint: attest TA identity (public key)
    Operator-->3rdPartyOEM: acquire machine
    Operator->>Machine: flash RDDL-compatible firmware
    Operator->>Machine: configure Machine: Mnemonic, PublicKeys, Planetmint-API, -Denom, -ChainID
    alt fund machine
    Operator->>Planetmint: fund machine
    else create account
    Operator->>TA-Attest: create account: MachineID, MachineIDSignature, PlanetmintAddress
    TA-Attest->>Planetmint: request TA status
    Planetmint-->>TA-Attest: TA status {activated: true/false}
    TA-Attest->>Planetmint: fund machine for self attestation
    end
    Machine->>Planetmint: Attest machine
    loop 
    Machine->>Planetmint: notarize CID/asset
    Machine-->Planetmint: Proof of Productivity
    end
```

## Testnet Only

3. Machines with self-registered Private Key

The sequence diagram below shows how the public key of the corresponding private key is registered on the testnet. The registration will enable individuals to onboard their machines easily without having a final RDDL-compatible firmware or hardware.

{% hint style="info" %}
This process is suggested to be used during the development and evaluation phase.
{% endhint %}

```mermaid
sequenceDiagram
    participant Operator
    participant Machine
    participant TA-Attest
    participant Planetmint
    Operator-->Machine: create unique private/public key pair
    Operator->>TA-Attest: register public key
	  TA-Attest->>Planetmint: attest TA identity (public key)
    Operator->>Machine: flash RDDL-compatible firmware
    Operator->>Machine: configure Machine: Mnemonic, PublicKeys, Planetmint-API, -Denom, -ChainID
    alt fund machine
    Operator->>Planetmint: fund machine
    else create account
    Operator->>TA-Attest: create account: MachineID, MachineIDSignature, PlanetmintAddress
    TA-Attest->>Planetmint: request TA status
    Planetmint-->>TA-Attest: TA status {activated: true/false}
    TA-Attest->>Planetmint: fund machine for self attestation
    end
    Machine->>Planetmint: Attest machine
    loop 
    Machine->>Planetmint: notarize CID/asset
    Machine-->Planetmint: Proof of Productivity
    end
```

An HTTP POST request to  https://testnet-ta.rddl.io/register/\<pub key as hex string> will let you register your public key. Here is a sample call\
`curl -X POST https://testnet-ta.rddl.io/register/02d52a0163ae5f0b22cf46e9c415a12024bc1e9e6833e2fe78b4f0754f3d52404a`\
with `02d52a0163ae5f0b22cf46e9c415a12024bc1e9e6833e2fe78b4f0754f3d52404a` being the representation of the public key.

A call to [https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetTrustAnchorStatus](https://testnet-api.rddl.io/#/Query/PlanetmintgoMachineGetTrustAnchorStatus) with your machine ID, the public key of the TA, shows if your public key got properly attested and if the corresponding machine has already attested.
