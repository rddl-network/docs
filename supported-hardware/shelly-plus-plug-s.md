# Shelly Plus Plug S

The **Shelly Plus Plug S** does not have an **RDDL Network**-compatible Tasmota firmware. Instead, it comes with a Mongoose OS.

It is possible to install an RDDL Network Tasmota version with the help of a [Mongoose OS to Tasmota converter.](https://github.com/tasmota/mgos32-to-tasmota32)

The following steps need to be executed:

1. Follow the steps from [https://github.com/phiten/mgos32-to-tasmota32](https://github.com/phiten/mgos32-to-tasmota32) and upgrade to the native Tasmota.
2. Download the [Tasmota Partition Wizard](https://raw.githubusercontent.com/arendst/Tasmota/development/tasmota/berry/modules/Partition\_Wizard.tapp) (it's one of the supported [Tasmota Applications)](https://tasmota.github.io/docs/Tasmota-Application/)
3. Upload the Partition Wizard file to the Tasmota device by uploading it onto your filesystem (Main Menu -> Consoles ->  Manage File System)
4. Restart the Tasmota device
5. Enter the Partition Wizard in  Main Menu -> Consoles
6. Follow the instructions at [https://github.com/tasmota/mgos32-to-tasmota32](https://github.com/tasmota/mgos32-to-tasmota32) to install the safeboot (pick the correct one from [https://ota.tasmota.com/tasmota32/](https://ota.tasmota.com/tasmota32/))
7. Restart and upgrade to your firmware of choice from\
   [https://github.com/rddl-network/flash\_utils](https://github.com/rddl-network/flash\_utils) or [https://github.com/rddl-network/Tasmota/releases/](https://github.com/rddl-network/Tasmota/releases/tag/rddl-v0.35.0).

The LED configuration of the Plug can be configured as described at\
[https://templates.blakadder.com/shelly\_plus\_plug\_S.html](https://templates.blakadder.com/shelly\_plus\_plug\_S.html).
