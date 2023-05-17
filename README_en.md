
# USB CABLE CHECKER2 Manual

## Features

This product has the following features.

------

- Check the wire connection status of USB cables

- Check the built-in resistance value that a type C plug has (check for the presence of E-Marker for PD)

- Check the resistance of the power supply line

- Check for ground fault in a plug shell

------

## Explanation of each part

【JP】  
<img src="https://github.com/bit-trade-one/USBCableChecker2/blob/image/WP-%E8%A3%BD%E5%93%81%E3%83%88%E3%83%83%E3%83%97-SUB1.png" width="480px">
<!--  
![info](https://github.com/bit-trade-one/USBCableChecker2/blob/image/WP-%E8%A3%BD%E5%93%81%E3%83%88%E3%83%83%E3%83%97-SUB1.png)
-->
【EN】  
<img src="https://cdn.shopify.com/s/files/1/0512/2264/2842/files/UCC2Eng2.jpg?v=1671508735" width="480px">
<!-- 
![info](https://cdn.shopify.com/s/files/1/0512/2264/2842/files/UCC2Eng2.jpg?v=1671508735)
-->


## Before Use / Precautions

At the time of purchase, the USBCableChecker2 has a battery installed for operational check.

An insulating sticker is placed between the battery and the main unit. Please remove the sticker before use.

The board is protected by acrylic, but connectors and other parts are exposed, so please handle it with care.

**This product is a dedicated device for cable testing. Do not connect other USB devices. There is a risk of damage.**

## How to use

- **Check plug conversion adapters**

After turning ON the product's power, connect the conversion adapter to either the A-side connector or the B-side connector.

In the case of a Type-C plug conversion adapter, the resistance value is shown on the OLED display when a built-in resistor is connected to the CC.

If the adapter has an OTG function, "OTG ENABLE" will be displayed.

- **Check cables**

After turning ON the product's power, connect the A-side port to the B-side port with a USB cable.

If the wires are electrically connected, the corresponding LED will light up at "CONNECTION".

- **OLED display unit**

If **both** VBUS and GND of the cable connected to the A and B sides are wired together, the display will show the **total** resistance value of the VBUS and GND line resistance values.
  
If a Type-C plug with a built-in resistor in the plug is connected, the value of the pull-up/pull-down resistor connected to CC and the corresponding maximum allowable current value to be notified to the connected device are displayed.
  
If a 10k pull-down resistor is detected, it is determined to be a MARKED cable.

## Explanation of OLED display screen

### [Resistance]

The total resistance of the GND and VBUS lines.

This includes the contact resistance between the USB plug and connector. The units are in milliohms and the accuracy is ±15%.

The measurement limit is 1100 mΩ, above which "HIGH" is displayed.  

### [UP10K/SOURCE 3.0A]

A 10 kΩ resistor is connected between VBUS and CC in the C plug.

Let the connected USB device recognize the host as capable of supplying 3A of current.

Cables with resistors of this resistance value in the plug are not compliant with the USB specification.

### [UP22K/SOURCE 1.5A]

A 22 kΩ resistor is connected between VBUS and CC in the C plug.

Let the connected USB device recognize the host as capable of supplying 1.5A of current.

Cables with resistors of this resistance value in the plug are not compliant with the USB specification.  

### [UP56K/SOURCE 0.5A] 

A 56 kΩ resistor is connected between VBUS and CC in the C plug.

Let the connected USB device recognize the host as capable of supplying 0.5A of current.

Only this value is allowed for the built-in pull-up resistor in connectors according to the USB specification.

### [DOWN1K/E-MARKED]

A 1 kΩ resistor is connected between GND and VCONN in the C plug.

This notifies the connected USB device that it is an E-Marked cable with an integrated E-Marker IC.

### [DOWN5.1K/SINK 0.5A]

A 5.1 kΩ resistor is connected between GND and CC in the C plug.

This allows the connected USB device to operate as a host if possible.  

### [OTG　ENABLE]

Although not a resistor, it lights up when the GND-ID terminals of the Mini-B and Micro-B connectors are shorted.

This allows the connected USB device to operate as a host if possible.

### [SHELL-GND SHORT(SIDE)]

Displayed when the plug shell is conducive with GND. The parentheses indicate which connector, A or B, is conductive.

If both connectors are conductive, it will display "A&B".

Note that the Type-C-Type-C cable is specified to have the shell connected to GND. 

### [SHIELD CONNECT]

Displayed as "SHIELD CONNECT" when the shells at both ends are connected by an independent wire from GND.

Note that the shield wire of a regular legacy USB cable is usually connected to only one plug and there is no conduction between plugs.

## Weird cable mode

<img src="https://github.com/bit-trade-one/USBCableChecker2/blob/image/weird_cable_mode_example.png" width="680px">
<!-- 
![img](https://github.com/bit-trade-one/USBCableChecker2/blob/image/weird_cable_mode_example.png)
-->

When multiple CC pull-up or pull-down resistors are found in the cable or plug, the display enters a different mode than usual.

In this mode, the resistance values are displayed smaller, the shell and shield status is not shown, and the states of all CC terminals on both the A and B sides are listed. This feature helps to detect non-standard Type-C cables with unrecognizable front and back sides.

## Explanation of wire connection confirmation LEDs

【JP】  
<img src="https://github.com/bit-trade-one/USBCableChecker2/blob/image/ADUSBCIM_LED.png" width="680px">
<!-- 
![img](https://github.com/bit-trade-one/USBCableChecker2/blob/image/ADUSBCIM_LED.png)  
-->
【EN】  
<img src="https://cdn.shopify.com/s/files/1/0512/2264/2842/files/UCC2Eng.jpg?v=1671508738" width="600px">
<!-- 
![img](https://cdn.shopify.com/s/files/1/0512/2264/2842/files/UCC2Eng.jpg?v=1671508738)
-->

### [3.2]　

Wires used for USB 3.2 connections. The differential line names are based on the terminal names on the A-side connector.  

### CC

A wire is mainly used for identifying hosts and devices and USB PD communication in Type-C cables.

Various functions are exchanged between devices through this wire to determine if they "can be used."  

### SBU

A wire used for exchanging data other than USB data (such as audio and video) in Side Band Use.

It is mainly used in Alternate Mode.  

### TX1/2 and RX1/2

Wires are used for communication in USB 3.0 and later.

USB 3.0 uses two pairs of wires for data communication (SuperSpeed / SS), and USB 3.2 and later uses four pairs of wires for data communication (SuperSpeed+ / SS+).  

### [2.0]

Wires used for USB 1.0 to USB 2.0 connections.  

### D

Wires used for data communication up to USB 2.0 (LowSpeed / Full Speed and High Speed).  

### VBUS and GND

Wires used for power management.

## How to replace the battery

<img src="https://github.com/bit-trade-one/USBCableChecker2/blob/image/image4.jpg" width="480px">
<!-- 
![swap](https://github.com/bit-trade-one/USBCableChecker2/blob/image/image4.jpg)
-->

When "LOW BATTERY" is displayed on the OLED display at startup, it is time to replace the battery.

As shown in the image above, use the principle of leverage by sliding the tip of a flathead screwdriver into the gap between the negative terminal and the battery.

Then, install a new CR2032 battery with the positive side facing up.

Official page: http://bit-trade-one.co.jp/adusbcim
