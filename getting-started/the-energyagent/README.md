# ⚡ The EnergyAgent

RDDL.io developed the EnergyAgent to overcome limitations we faced while integrating that we faced during the integration of different sets of solutions.&#x20;

The EnergyAgent's goal is to work as a rock-solid piece of hardware to notarize the consumption of a range of smart metering devices (SMDs) that cannot connect to the RDDL network.

Incoming data is collected via an MQTT service hosted on the EnergyAgent, and the RDDL network identity is managed by an attached TrustAnchor Wallet.

Multiple wireless protocols (e.g., Zigbee, LoRa, WiFi, etc.) are supported to connect various devices to the EnergyAgent. More details can be found in the respective hardware details section.

<figure><img src="../../.gitbook/assets/Energy Agent_compactV3.png" alt=""><figcaption></figcaption></figure>

### Key Feature

* **Powerful Performance**: Raspberry Pi CM4, quad-core A72, 4GB RAM and 16GB eMMC
* **Multiple Industrial Interfaces**: 3x RS485, 2x Ethernet Ports, 1x HDMI, 3x USB2.0
* **Versatile Wireless Options**: Support Wi-Fi, BLE 5.0, LoRaWAN®, Zigbee, 4G LTE
* **Perfect Fit for Building Automation System**: Support BACnet & Modbus Protocols to ensure interoperability
* **Safety and Reliability**: Hardware watchdog, UPS, EMC protection, TPM2.0/ATECC608A\* supported, 6-year lifetime, 2-year warranty

### **The Product**

The Energy Agent comes with a Trust Wallet attached. The Trust Wallet manages the keys and is pre-provisioned with a machineID key that is attested to the RDDL Network. The attested machine ID enables the Energy Agent to register to the network and attest itself to start interacting with the network.

<figure><img src="../../.gitbook/assets/Untitled-2024-06-13-1423 (3).png" alt=""><figcaption></figcaption></figure>



## How it works

The EnergyAgent service connects an MQTT service (locally or self-defined) to connect SMDs and notarizes the data of the SMDs (connected via MQTT) to the RDDL network.

Tasmota- and Shelly-compatible devices are currently supported types of SMDs. More can be added upon request (preferably PRs on the project's [Git Hub page](https://github.com/rddl-network/energyagent)).

The RDDL network identity and the needed key material are managed by the attached TrustWallet.

The RDDL network configuration (mainnet or testnet) can be set via the UI or the command line. For more details, see the [installation and configuration instructions](installation.md).





