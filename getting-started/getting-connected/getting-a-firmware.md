# ⚡ Getting a Firmware

A RDDL-compatible firmware has to meet the [Compatibility Requirements](../rddl-compatibility-requirements.md).

Reference firmwares - so called [RDDL-Tasmota](https://github.com/rddl-network/Tasmota) firmwares - based on [Tasmota](https://github.com/arendst/Tasmota) including [librddl](https://github.com/rddl-network/librddl/) can be retreived from the following URLs for the following MCUs

Testnet:

* ESP32: [https://testnet-ta.rddl.io/firmware/esp32](https://testnet-ta.rddl.io/firmware/esp32)
* ESP32C3 [https://testnet-ta.rddl.io/firmware/esp32c3](https://testnet-ta.rddl.io/firmware/esp32c3)

Mainnet:

* ESP32: [https://ta.rddl.io/firmware/esp32](https://ta.rddl.io/firmware/esp32)
* ESP32C3: [https://ta.rddl.io/firmware/esp32c3](https://ta.rddl.io/firmware/esp32c3)

**Note:** It is important to use the correct firmware depending on the net you want to use. Your firmware will be registered so it can interact with the corresponding network.

It is also possible to extend or develop your own firmware as long as the result meets the requirements of [Compatibility Requirements](../rddl-compatibility-requirements.md). This process can be simplified by not starting from scratch but to use and utilize the libraries that the RDDL Network developed in order to make Tasmota compatible.&#x20;

That are librddl and the rddl-sdk (deprecated).&#x20;

[**librddl**](https://github.com/rddl-network/librddl/) contains the communciation primitives and workflows to enable the communication with RDDL Network.&#x20;

[**rddl-sdk**](https://github.com/rddl-network/rddl-sdk/) utilizes librddl and creates the workflows and business logic needed to become an active RDDL Network participant.&#x20;

{% hint style="info" %}
librddl and rddl-sdk will be merged into one library in the near future.
{% endhint %}

A sample utilization and implmentation of librddl and rddl-sdk can be found at the RDDL-Tasmota repository [https://github.com/rddl-network/Tasmota](https://github.com/rddl-network/Tasmota).
