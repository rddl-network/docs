# ⏱ POWR316D Elite

The [POWR316D Elite](https://www.amazon.de/Energiemessung-%C3%9Cberlastschutz-Energieeinsparung-Reichweite-Sprachsteuerung/dp/B09XB3RZB9/ref=sr\_1\_2?\_\_mk\_de\_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91\&keywords=Sonoff%2BPOWR3\&sr=8-2\&th=1) is a Smart ESP32 based Power Monitoring and Power Relais device.\
In order to flash this device there is some soldering required as the flashing method is USB to Serial. The exact same process applies for the POWR320D Elite.

The configuration file for Buttons and other features can be added by following the instructions here: [https://templates.blakadder.com/sonoff\_POWR316D.html](https://templates.blakadder.com/sonoff\_POWR316D.html)

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

## Flashing Sonoff - Tasmota

💡 I**MPORTANT & WARNING:**

**NEVER TRY TO FLASH WHILE YOUR DEVICE IS CONNECTED TO MAINS POWER!!!**

**YOU CAN BE ELECTROCUTED IF YOU DO NOT KNOW WHAT YOU ARE DOING!**



**💡 During the complete, succeeding process the Sonoff POW Elite has to stay unplugged from the main power! The Serial-to-USB adapter is sourcing enough power from your host computer to run the MCU inside the Sonoff power-meter/switch**



#### Prerequisites:

1. Soldering Iron and solder paste
2. 2 Pin headers\
   ![](<../../.gitbook/assets/image (27).png>)
3. Jumper Wires
4. Screw-driver toolset
5. [**ESP-Flasher**](https://github.com/Jason2866/ESP\_Flasher)\
   **-** GUI flasher for Tasmota based on [esptool.py](http://esptool.py) for ESP32. (Windows, Linux or Mac)
6. Serial-to-USB connector
   1. if possible based on FTDI chipset
   2. [FTDI FT232](https://www.ftdichip.com/Products/ICs/FT232R.htm)\
      \- these adapters have a lot of fakes in the market so buy only from reliable sources ([example](https://www.sparkfun.com/products/13746)). Buy only the variant with a separate 3.3V regulator on PCB! I’ve used the one from Sparkfun.
7. Prepare the firmware we intend to flash onto the MCU
   1.  the Sonoff POW Elite is powered by an ESP32. Therefore,\
       we need exactly this firmware aka tasmota.bin. In our case this is tasmota32.bin

       One finds them at this resource locator:\
       [Tasmota ESP32 Binary Release List](http://ota.tasmota.com/tasmota32/release/)\
       Or just download here directly:\
       [Tasmota32.bin download](https://ota.tasmota.com/tasmota32/release/tasmota32.bin)

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption></figcaption></figure>

Arrange the POW Elite on your desk, together with all the tools needed. Use precision screw-drivers to not mess up the screws and to not break the casing. Take care that the power meter was disconnected from the mains power long enough ( 5 to 10 mins).

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

Flip the device to its backside and unscrew the four visible screws to take off the back cover of the device casing. Keep wires, jumpers, adapters, soldering tools at hand.

<figure><img src="../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

Once the device is open you will recognize the 4 pin holes at the top of the PCB. There we will have to solder the connectors for 3.3V power, ground, data receive and transmit jump wires.

Unscrew the additional 4 screws to take the PCB completely out of the casing. Keep the two sets of screws at a safe place, split from each other. Also take care for the mains power connectors, which will fall off once you unmount the PCB from the casing.

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

Turn the PCB around and you will see the markings for the PIN outs it requires to solder. When you solder the PIN headers take care of the length of the headers. They will remain on the PCB when you reassemble board and casing. Also, take care that the headers on both sides reach out of the holes far enough to get well soldered. Bad soldering creates lose connections and creates noise. This noise might result in errors while flashing the firmware.

<figure><img src="../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>



<figure><img src="../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (36).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (38).png" alt=""><figcaption></figcaption></figure>

After successful soldering put the PCB back into its case and screw it in, again. But keep the backside open, still. As a next step connect the Serial-to-USB connector with the right four jumper wires (female ends on both sides) to the PCB.

1. Connect ground to ground (GND to GND)
2. Connect power to power (3.3V to 3.3V)
3. Connect TX to RX ( Attention !)
4. Connect RX to TX

Another important issue. The adapter has to support and operate for 3.3V and not for 5V. Otherwise, you will destroy the MCU.

Then connect the Serial-to-USB adapter to your host computer via the right USB cable. On the host the ESP-flasher has to be installed and started and the tasmota32.bin has to be downloaded and to available to be loaded by the ESP-flasher.

The ESP-flasher will recognize automatically the serial port the Serial-to-USB adapter is connected to. Then load the tasmota32.bin firmware from the right directory of the host computer.

Now, before you can flash the firmware onto the Sonoff you have to put the Sonoff’s ESP32 MCU into boot mode. To achieve this you have to disconnect the power jumper wire from the Sonoff PIN header. Then you have to print the start button on the Sonoff device and keep it pressed for 10 seconds while you connect the power PIN header again.

Then you can press the “Flash ESP” button inside the ESP-flasher user interface. This will start the flashing of the firmware to Sonoff’s ESP32 MCU.

Now completely close the casing again. Reconnect the main power cord and connect main power, cable and Sonoff again to your validator node. Restart the validator node.

<figure><img src="../../.gitbook/assets/image (39).png" alt=""><figcaption></figcaption></figure>

## Using the flashed Sonoff/Tasmota

Don’t be distracted the LCD screen of the Sonoff is not going to show any information on the screen. This part of the Tasmota firmware for the POW Elite is not fully activated.

Once the POW Elite with the Tasmota firmware is connected again check your Wifi network for a new Wifi device. You will see that the Sonoff will appear as its own Wifi router. Connect to it.

Then open your browser. better keep it open before you connect to the Sonoff via Wifi.

Inside your browser, a configuration window will appear. Select the right Module parameters and save them. Then the Sonoff device will ask you for the access credentials to your Wifi mainnet. Give the right credentials and save everything. The Sonoff will keep you informed when it has successfully established the bridge to your WIFI mainnet and it will also inform you about its very own IP address on your mainnet. The Sonoff will restart. Change your Wifi network back to your main network and connect to Sonoff’s IP address. Then you are done.

**💡 The Sonoff devices need a configuration template to operate properly**

Press on “Configuration” and then “Configure other”. Copy the configuration template from below and paste it instead of the one in your Tasmota interface under **Other Parameters** → **Template** as on the screenshot below.

<figure><img src="../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

[**Configuration template**](https://templates.blakadder.com/sonoff\_POWR316D.html) for Sonoff POWR316D **Elite:**

```jsx
{"NAME":"Sonoff POWR316D","GPIO":[32,0,0,0,0,576,0,0,0,224,9280,0,3104,0,320,0,0,0,0,0,0,9184,9248,9216,0,0,0,0,0,0,0,0,0,0,0,0],"FLAG":0,"BASE":1}
```

After copying this template to the Tasmota Web-interface:

```jsx
Check the “Activate” Box and proceed by clicking on Save.
```



You will notice that the LCD screen shows values and the relay works properly after the reboot.

With these 2 calls one gets the power consumption data and some additional meta information:

`curl <http://sonoff/cm?cmnd=EnergyTotal`> (sonoff) is my nameresolution of the local IP) returns the following:

```
{"EnergyTotal":{"Total":0.392,"Yesterday":0.179,"Today":0.213}}
```

whereas`curl <http://sonoff/cm?cmnd=Status%208`>

```
{"StatusSNS":{"Time":"2022-10-18T12:08:14","ENERGY":{"TotalStartTime":"2022-10-13T10:12:20","Total":0.392,"Yesterday":0.179,"Today":0.213,"Power":17,"ApparentPower":36,"ReactivePower":32,"Factor":0.47,"Voltage":230,"Current":0.156},"ESP32":{"Temperature":26.7},"TempUnit":"C"}}
```

returns a bit more complex but also more contextual information.

## Reset Sonoff/Tasmota (zurücksetzen)

If you're having problems with your Sonoff device not starting up. You can also completely "reset" the Tasmota device. To do this, press the power button for at least 40 seconds. This will reset the device to its factory settings, and you can start anew.
