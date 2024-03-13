# USB CABLE CHECKER2 Manual

## Features

This product has the following features :

------

- Check the wire connection status of USB cables

- Check the built-in resistance of a Type C plug (check for the presence
 of PD E-Marker)

- Check the resistance of the power line

- Check for ground fault in a plug shell

------

## Explanation of each part

![info](https://cdn.shopify.com/s/files/1/0512/2264/2842/files/UCC2Eng2.jpg?v=1671508735)

## Before Use / Precautions

When purchased, the USBCableChecker2 comes with a battery installed for
 operational verification.

There is an insulating seal placed between the battery and the device; please
 remove it before use.

The circuit board is protected by acrylic, but as connectors and other
 components are exposed, please handle with care.

**This product is a cable testing device only. Do not connect other USB devices
 to it as this may cause damage.**

## How to use

- **Determining Plug Adapter Compatibility**

After powering on the device, connect a conversion adapter to either the A-side
 or B-side connector.

If there is a built-in resistance connected to CC in the Type C plug adapter,
 the resistance value will be displayed on the OLED screen.

If the adapter has OTG (On-The-Go) functionality, "OTG ENABLE" will be displayed.

- **Cable Determination**

After turning on the device, connect the A-side and B-side connectors with a
 USB cable.

If the wires are properly connected, the corresponding LED will light up under "CONNECTION".

- **OLED Display Section**

If **both** VBUS and GND of the cable connected to the A and B sides are wired, the
 display will show the **total** resistance value of the VBUS and GND lines.
  
Connecting a Type C plug with an internal resistance will display the value of
 the pull-up/pull-down resistance connected to CC, as well as the maximum
 allowable current value notified to the connected device according to the resistance.
  
If a 10k pull-down resistance is detected, the cable is identified as MARKED.

## Explanation of OLED Display Indications

### \[Resistance\]

This is the total resistance of the GND and VBUS lines.

It includes the contact resistance between the USB plug and connector. The unit
 is milliohms (mΩ) with an accuracy of ±15%.

The measurement limit is 1100mΩ, and values above this are displayed as "HIGH".

### \[UP10K/SOURCE 3.0A\]

This indicates a 10kΩ resistor connected between VBUS and CC within the Type C plug.

It signals to the USB device that the host can supply a current of up to 3A.

**Cables with this resistance value built into the plug are non-standard
 according to USB specifications.**

### \[UP22K/SOURCE 1.5A\]

Indicates a 22kΩ resistor connected between VBUS and CC within the Type C plug.

It signals to the USB device that the host is capable of supplying a current of 1.5A.

**Cables with this resistor value built into the plug are non-standard
 according to USB specifications.**

### \[UP56K/SOURCE 0.5A\]

Indicates a 56kΩ resistor connected between VBUS and CC within the Type C plug.

It signals to the USB device that the host is capable of supplying a current of 0.5A.

This is the only connector-built-in pull-up resistor value permitted by USB specifications.

### \[DOWN1K/E-MARKED\]

Indicates a 1kΩ resistor connected between GND and VCONN within the Type C plug.

This notifies the connected USB device that the cable contains an E-marker IC.

### \[DOWN5.1K/SINK 0.5A\]

Indicates a 5.1kΩ resistor connected between GND and CC within the Type C plug.

This allows the connected USB device to act as a host if possible.

### \[OTG ENABLE\]

Although not a resistor, it lights up when the GND-ID terminal between Mini-B,
 Micro-B connectors is short-circuited.

This allows the connected USB device to act as a host if possible.

### \[SHELL-GND SHORT(SIDE)\]

Displayed when the plug shell is conductive with GND. The parentheses indicate
 which side's connector, A or B, is conductive.

If both connectors are conductive, it displays as A&B.

Note that for Type C-C cables, the standard specifies that the shell is
 connected to GND.

### \[SHIELD CONNECT\]

Displayed when both ends' shells are connected with a wire independent of GND
 as "SHIELD CONNECT".

Typically, the shield wire of legacy USB cables is connected only to one plug,
 and there is no continuity between plugs.

## Weird cable mode

![img](https://github.com/bit-trade-one/USBCableChecker2/blob/image/weird_cable_mode_example.png?raw=true)

When multiple CC pull-up or pull-down resistors are detected in the cable or
 plug, the display will switch to a mode that differs from the usual display
 mode.

In this display mode, resistance values are shown smaller, and the status of
 the shell or shield is not displayed. Instead, it lists the status of all CC
 terminals on both the A and B sides. This feature is useful for identifying
 non-standard Type-C cables, such as those that cannot differentiate between orientations.

## Explanation of Wire Connection Confirmation LEDs

![img](https://cdn.shopify.com/s/files/1/0512/2264/2842/files/UCC2Eng.jpg?v=1671508738)

### \[3.2\]

These wires are used for USB 3.2 connections. The names of the differential
 pairs correspond to the terminal names on the A-side connector.

### CC

In Type C cables, this wire is primarily used for identifying hosts and devices
 and for USB PD (Power Delivery) communication.

Various functionalities are communicated between devices via this wire to
 determine their availability.

### SBU

Stands for Side Band Use. These wires are used for transferring data other
 than USB data communication, such as audio or video.

They are mainly used in alternate mode.

### TX1/2 and RX1/2

These wires are used for communication in USB 3.0 and later versions.

USB 3.0 uses two pairs of wires for data communication (SuperSpeed /SS), while
 USB 3.2 uses four pairs of wires for data communication (SuperSpeed+ / SS+).

### \[2.0\]

These wires are used for USB 1.0 to USB 2.0 connections.

### D

These wires are used for data communication up to USB 2.0 (LowSpeed / Full
 Speed and High Speed).

### VBUS and GND

These wires are used for power management.

## Battery Replacement Method

![swap](https://github.com/bit-trade-one/USBCableChecker2/blob/image/image4.jpg?raw=true)

When "LOW BATTERY" is displayed on the OLED screen at startup, it is time to
 replace the battery.

As shown in the image above, insert the tip of a flathead screwdriver into the
 gap between the negative terminal and the battery, then leverage it out using
 the principle of a lever.

Afterward, install a new CR2032 battery with the positive side facing up.

Official page: <http://bit-trade-one.co.jp/en/adusbcim>
