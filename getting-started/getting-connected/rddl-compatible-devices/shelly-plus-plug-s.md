# 🔌 Shelly Plus Plug S

The [**Shelly Plus Plug S**](https://www.amazon.de/Shelly-Plus-Plug-programmierbare-Sprachsteuerung/dp/B0BTJ1DTBX/ref=sr\_1\_2?keywords=shelly%2Bplug%2Bs\&sr=8-2\&th=1) does not have an **RDDL Network**-compatible Tasmota firmware. Instead, it comes with a Mongoose OS.

It is possible to install a RDDL Network Tasmota version with the help of a [Mongoose OS to Tasmota converter.](https://github.com/tasmota/mgos32-to-tasmota32)

Follow the steps to get your Shelly Plus Plug S RDDL ready.

**Video guide:**

{% embed url="https://www.youtube.com/watch?v=_Xv1U5Fz2Y4" %}

1st Link: [MgOs to Tasmota Github](https://github.com/tasmota/mgos32-to-tasmota32)

2nd Link: [RDDL Firmware](https://testnet-ta.rddl.io/firmware/esp32)

3rd Link: [LED Configuration](https://templates.blakadder.com/shelly\_plus\_plug\_S.html)

**Written guide**:

1. Setup your Shelly Plus Plug S and connect it to your network (see the manual)
   1. Connect to the ShellyPlusPlugS-Wifi of the device
   2. Browse to 192.168.33.1 to configure your device
   3.  Configure the Shelly Plus Plug S WiFi by providing the SSID and password to your local WiFi.&#x20;

       Once the Shelly Plus Plug S connects to your local WiFi, you can see the device's IP address on the dashboard, and from now on, you can connect to Shelly Plus Plug S by entering this IP address on your browser.

       If you were unable to see the IP address,&#x20;

       1. the IP address can be looked up on your router
       2.  or via a network sniffing app for your OS.

           <figure><img src="../../../.gitbook/assets/Screenshot 2023-11-20 at 14.47.07.png" alt=""><figcaption></figcaption></figure>
       3.
   4. Upgrade the device firmware by selecting _**Settings**_ and then _**Firmware**_.
   5. Be sure to refresh the shelly page after that to see the upload-file option on the web page.
2. Follow the steps from [https://github.com/tasmota/mgos32-to-tasmota32](https://github.com/tasmota/mgos32-to-tasmota32) and upgrade to the newest Tasmota firmware.\
   **IMPORTANT NOTE ⚠️** Make sure to follow the steps **“⚠️ NEEDED ⚠️ Convert to Tasmota Safeboot and update to the latest Tasmota release”** on [https://github.com/tasmota/mgos32-to-tasmota32](https://github.com/tasmota/mgos32-to-tasmota32) otherwise, you won’t be able to upgrade to RDDL-compatible firmware and even might brick your device!
3. Enter the _**Consoles -> Partition Wizard**_ page and resize the file system.&#x20;
4. Download new RDDL-compatible firmware from [https://testnet-ta.rddl.io/firmware/esp32](https://testnet-ta.rddl.io/firmware/esp32)
5. Upgrade to the previously downloaded firmware by selecting _**Firmware Upgrade**_, dragging and dropping the _**tasmota32-rddl.bin**_ file onto the _**Upgrade by file upload**_ section and finally, by clicking _**Start Upgrade**_.

{% hint style="info" %}
**Resizing (Step 3)** is important in order to have fresh working filesystem. Issues got experiencd otherwise.
{% endhint %}

The LED configuration of the Plug can be configured as described at\
[https://templates.blakadder.com/shelly\_plus\_plug\_S.html](https://templates.blakadder.com/shelly\_plus\_plug\_S.html).

<figure><img src="../../../.gitbook/assets/SHELLYPLUS PLUG S.png" alt="" width="375"><figcaption></figcaption></figure>

