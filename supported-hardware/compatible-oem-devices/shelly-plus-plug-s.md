# 🔌 Shelly Plus Plug S

The [**Shelly Plus Plug S**](https://www.amazon.de/Shelly-Plus-Plug-programmierbare-Sprachsteuerung/dp/B0BTJ1DTBX/ref=sr\_1\_2?keywords=shelly%2Bplug%2Bs\&sr=8-2\&th=1) does not have an **RDDL Network**-compatible Tasmota firmware. Instead, it comes with a Mongoose OS.

It is possible to install an RDDL Network Tasmota version with the help of a [Mongoose OS to Tasmota converter.](https://github.com/tasmota/mgos32-to-tasmota32)

The following steps need to be executed:

1. Setup your Shelly Plus Plug S and connect it to your network (see the manual)
   1. Connect to the ShellyPlusPlugS-Wifi of the device
   2. Browse to 192.168.33.1 to configure your device
   3. Configure your Wifi
   4. Upgrade your firmware
   5. Be sure to refresh the shelly page after that to see the upload-file option on the web page.
2. Follow the steps from [https://github.com/tasmota/mgos32-to-tasmota32](https://github.com/tasmota/mgos32-to-tasmota32) and upgrade to the newest Tasmota firmware.
3. Download new RDDL-compatible firmware from [https://testnet-ta.rddl.io/firmware/esp32](https://testnet-ta.rddl.io/firmware/esp32)
4. Upgrade to the previously downloaded firmware.

The LED configuration of the Plug can be configured as described at\
[https://templates.blakadder.com/shelly\_plus\_plug\_S.html](https://templates.blakadder.com/shelly\_plus\_plug\_S.html).

<figure><img src="../../.gitbook/assets/SHELLYPLUS PLUG S.png" alt="" width="375"><figcaption></figcaption></figure>

