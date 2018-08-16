# IMPORTANT STUDIO NOTE
> ServiceNow Studio does not play nice with remote updates to Repos. Updating this readme.md for example, corrupts the repo.  To import this application to studio, I would reccomend that you download the [ZIP File realease](https://github.com/coryforsythe/sn-vmware-day2/archive/2018-08-16-TESTED.zip) and upload it to a new GitHub Repository. You may then connect your ServiceNow Studio to this application and begin working with it locally.  


# ServiceNow VMware Day 2 Operations

This repository contains a VERY unofficial extension to the VSphereComputeProvider resource block and a new REST API Implementation that provides additional Day2 operations for VMWare virtual machines built from the Virtual Server Resource Block.

**Applicable to:** ServiceNow Instances running Jakarta, Kingston, or London and have the Cloud Management Platform application installed (requested via HI and licensed per node. Contact your account manager for complete information regarding financial impact of enabling paid plugins).

**The Additional Operations Are:**
- Stop (not previously functional in the baseline)
- Suspend (not new but now using REST)
- Start (not new but now using REST)
- Reboot (not previously functional in the baseline)
- AdjustCPU
- AdjustMemory

# Installation
Clone this repo down to the Studio application and apply it to your instance

Note that you will now have new catalog items published for the Virtual Machine Resource Block for AdjustCPU and AdjustMemory.  Though operations exist for the others, no catalog items are published. You may choose to do so later.

# Usage

## Create a Blueprunt
Construct a new BluePrint utilizing the VSphere and Virtual Machine resource blocks
![Image of Blueprint](https://raw.githubusercontent.com/coryforsythe/sn-vmware-day2/master/imgs/bp.png)

## Request a VM
Complete a request to provision a new VM from your newly created blueprint and navigate to the completed stakc
![Image of Stack](https://raw.githubusercontent.com/coryforsythe/sn-vmware-day2/master/imgs/stack.png)

## Note new Operations for the VM
Note that the activities combo-box control now contains activities for AdjustCPU and AdjustMemory (note: you may need to click on the VM resouce if the Stack is selected)
![Image of Activities](https://raw.githubusercontent.com/coryforsythe/sn-vmware-day2/master/imgs/activities.png)

## Request the Operation
Ensure the VM is stopped, then try adjusting the memory and note the two API Operations invoked. The first Adjusts the Memory for the VM and the second describes the VM so that the CMDB can be updated
![Image of Operations](https://raw.githubusercontent.com/coryforsythe/sn-vmware-day2/master/imgs/ops.png)

Note the operation is also reflected in VMware. The inventory data should match the CMDB. In this example, the memory was adjusted to  1024MiB

![Image of Proof](https://raw.githubusercontent.com/coryforsythe/sn-vmware-day2/master/imgs/proof.png)







