# 🎭 Actors

* Pro/consumer machines by Tasmota Nodes
  * Data notarization
  * Data trading
  * PoP participation
* Machine operators&#x20;
  * Offering micro-investments
  * distributing production rewards/participation
* Parties interested in data
  * &#x20;pay for data with incentive tokens



The following [types of machines](https://github.com/rddl-network/librddl/blob/main/inc/rddl\_types.h) are currently supported.

```cpp
#ifndef __RDDL_MACHINE_TYPES__
#define __RDDL_MACHINE_TYPES__

#define RDDL_MACHINE_UNDEFINED          0
#define RDDL_MACHINE_POWER_SWITCH       1
#define RDDL_MACHINE_ENERGY_TRACKER     2
#define RDDL_MACHINE_ENERGY_METER       3
#define RDDL_MACHINE_LOGGER             4
#define RDDL_MACHINE_BATTERY            5
#define RDDL_MACHINE_INVERTER           6
#define RDDL_MACHINE_CONTROLLER         7
#define RDDL_MACHINE_CHARGER            8
#define RDDL_MACHINE_BMS                9 
#define RDDL_MACHINE_ESS               10 

#endif
```
