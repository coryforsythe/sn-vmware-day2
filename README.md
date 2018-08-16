# ServiceNow VMware Day 2 Operations

This repository contains a VERY unofficial extension to the VSphereComputeProvider resource block and a new REST API Implementation that provides additional Day2 operations for VMWare virtual machines built from the Virtual Server Resource Block.

**The Additional Operations Are:**
- Stop (not previsouly functional in the baseline)
- Suspend (not new but now using REST)
- Start (not new but now using REST)
- Reboot (not previsouly functional in the baseline)
- AdjustCPU
- AdjustMemory

# Installation
Clone this repo down to the Studio application and apply it to your instance

Note that you will now have new catalog items published for the Virtual Machine Resource Block for AdjustCPU and AdjustMemory.  Though operations exist for the others, no catalog items are published. You may choose to do so later.

# Usage
Construct a new BluePrint utilizing the VSphere and Virtual Machine resource blocks
![Image of Blueprint](https://raw.githubusercontent.com/coryforsythe/sn-vmware-day2/master/imgs/bp.png)
