# How to register your Machine ID

The way the machine ID is registered depends on the machine type

1. RDDL certified hardware
2. RDDL-compatible hardware
3. unsupported hardware

The below-mentioned flow chart highlights what needs to be done in each case. Unsupported hardware can be used but needs to become compatible. Interested entities can become a 3rd party certified OEM partner and apply for a process to register machine IDs for the mainnet on their own.&#x20;

```mermaid fullWidth="true"
flowchart TD
    A[Hardware]-->B
    B{Is the HW officially supported} --> |officially supported| C
    C{Does it come with a unique\npreregistered Public Key}-->|yes| D
    D(Use your HW and attest the machine)
    C-->|no| E
    E(Download unique Firmware)-->|Flash Firmware| D
    B-->|not officially supported| J
    F(Integrate libRDDL & Implement Testnet compatibility)--> |pass the HW approval and verification process| D
		F--> G
    G(create PRP-9 PR)--> |apply for Certified 3rd Party OEM vendor| I
    I(The process to become a Certified RDDL HW OEM vendor)
		J{Is it a ESP32/C3 Device?}-->|yes| E
		J{Is it a ESP32/C3 Device?}-->|no| F
```
