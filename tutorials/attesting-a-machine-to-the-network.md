# Attesting a Machine to the Network

### Requirements

* Installed 0x21e8 on the Node
* Installed rddl-client (for convenience)
* LBTC
* RDDL (later this year)
* [RDDL Explorer](https://explorer.rddl.io) (optional)
* [Liquid Testnet Explorer](https://blockstream.info/liquidtestnet/) (optional)
* [Liquid Testnet Faucet](https://liquidtestnet.com/faucet) (optional)

### Step by Step

1. Attach the Node to the internet (& the machine if this is not a Tasmota node)
2.  Get your machine specification \


    ```json
    {
        'DMIType': 1, 
        'DMISize': 27,
        'DMIName': 'System Information', 
        'Manufacturer': 'Intel(R) Client Systems', 
        'Product Name': 'NUC9VXQNX',
        'Version': 'K47173-402',
        'Serial Number': 'JRQN027302GK',
        'UUID': 'ddadbe4e-ba9d-11ea-9e72-9e7acb4ae300',
        'Wake-up Type': 'Power Switch',
        'SKU Number': 'BKNUC9VXQNX', 
        'Family': 'QN'
    }

    ```
3. Get your machine location.
4. <pre><code><strong>     "geo": {     
   </strong><strong>            "host": "node1-rddl-testnet.twilightparadox.com",
   </strong>            "ip": "84.112.103.218",
               "rdns": "84-112-103-218.cable.dynamic.surfer.at",
               "asn": 8412,
               "isp": "T-Mobile Austria GmbH",
               "country_name": "Austria",
               "country_code": "AT",
               "region_name": "Vienna",
               "region_code": "9",
               "city": "Vienna",
               "postal_code": "1150",
               "continent_name": "Europe",
               "continent_code": "EU",
               "latitude": 48.1968,
               "longitude": 16.3191,
               "metro_code": null,
               "timezone": "Europe\/Vienna",
               "datetime": "2023-01-19 11:20:22"
           }
   }
   </code></pre>
5. Provision the machine with public-private keys by running a Key Ceremony&#x20;
6. Get the machine's public keys to fund your machine
7. Attest the device to the RDDL Network
8. Start notarizing data by defining the machine logic&#x20;
9. Distribute your shares
