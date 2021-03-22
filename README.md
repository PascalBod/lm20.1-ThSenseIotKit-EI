# Overview

This short tutorial describes a way to make a virtual machine configured for creating and running machine learning models created using [Edge Impulse plaform](https://www.edgeimpulse.com/), for a [Silicon Labs Thunderbird Sense 2 Iot Kit](https://www.silabs.com/development-tools/thunderboard/thunderboard-sense-two-kit).

The virtualization environment is VirtualBox, and the guest machine runs Linux Mint 20.1.

# Prerequisites

* Hardware: a 64-bit computer with enough memory so that the VM can be granted 16 GB, with a few tens of GB available on the disk, and one free USB A port
* Hardware (bis): a [Silicon Labs Thunderboard Sense 2 board](https://www.silabs.com/development-tools/thunderboard/thunderboard-sense-two-kit) with an USB A / micro USB B cable
* Developer:
    * basic knowledge of Linux (knowing the most common commands...)
    * basic knowledge of VirtualBox (knowing how to create a virtual machine...)

# Creation of the VM

Check [this guide](https://github.com/PascalBod/lm20.1-vm). Don't forget to add the user to *dialout* group, as stated.

# VM configuration

## Reference documents

* [SiLabs Thunderboard Sense 2 - Edge Impulse](https://docs.edgeimpulse.com/docs/silabs-thunderboard-sense-2)

## Installing dependencies

Install *g++*:

```shell
$ sudo apt install g++
```

Install *nvm* as described [here](https://github.com/nvm-sh/nvm).

Then install *npm*:

```shell
$ nvm install v14.16.0  # The current LTS version.
```

Install *screen*:

```shell
$ sudo apt install screen
```

Install Edge Impulse CLI:

```shell
$ npm install -g edge-impulse-cli
```

Several warnings and notes are displayed. Let's suppose we can ignore them...

# Connecting to Edge Impulse

Signup on [Edge Impulse website](https://studio.edgeimpulse.com/signup).

Connect the Thunderboard Sense 2 board to a USB port of the host machine. Ask VirtualBox to capture it for the virtual machine: in VirtualBox menu for the VM, select **Devices > USB** and tick **Silicon Labs J-Link OB [0100]**. To make the capture permanent, select **Devices > USB > USB Settings...** and add a USB device filter for the board.

Then follow [Edge Impulse instructions](https://docs.edgeimpulse.com/docs/silabs-thunderboard-sense-2#connecting-to-edge-impulse).


If you face the *Error while connecting to CPU* problem when flashing the board with the Edge Impulse binary file, push the board *RESET* button, keep it pushed until you start copying the binary file to the TB004 drive, and release it.

# Start playing with ML

Follow the [*continuous motion recognition*](https://docs.edgeimpulse.com/docs/continuous-motion-recognition) tutorial, for instance.