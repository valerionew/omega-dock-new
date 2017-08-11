# Omega dock\new

Project released under CC-BY-SA 4.0 license  
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by-sa/4.0/)

![layout 1](/images/layout.jpg)

1. [Project status](#project-status)  
1. [Project description](#project-description)  
1. [BOM](#bom)  
1. [Photos](#photos)  

## Project status
v0.9 tested, working with some bodges  
v1.0 boards not tested yet

## Project description 
This is my dock\new project: it's a small dock (same size as the mini dock and the omega) for the Onion Omega 2 and 2+.

I needed the smallest dock i could do, that featured:

* Ethernet
* Type A USB host
* Micro USB for power

It has an onboard linear voltage regulation (i didn't bother going with a switching one for such low power), magnetics integrated in the RJ45 connector to save space, USB host ESD protection (diode array), USB host PTC fuse.

On the left side there is the RJ45 connector and nothing on the back side of the board, so that you can easily access the MicroSD card on the Omega 2+.
On the right side (the antenna side of the omega) you have the USB type A connector, facing outwards, and the microusb connector for power, facing inwards.

The first version, v0.9, had some issues with the ethernet. Currently i've released v1.0 that solves all the issues, adds a led to check power and, making a better use of the space, the RJ45 connector doesn't protrude anymore. I haven't ordered the v1.0 PCBs yet, but the circuit is tested.

I've chosen 0805 passives, 1206 ptc fuse, big smd electrolitic caps, a SOT223 (the classic 1117) for power regulation and a SOT23-6 for usb host protection, so it can all be easily handsoldered with just a plain soldering iron. Probably the hardest part to handsolder is the SOT23-6 but it's easily doable by hand.

The components and board cost for the prototype it's arround 10 to 15€ per board.

## BOM
|    Symbol   |                 Package                | Quantity |    Valore   |                          Note                          |
|:-----------:|:--------------------------------------:|:--------:|:-----------:|:------------------------------------------------------:|
| C1          | CP_Elec_4x5.3                          |     1    | 10uF        | 10V or higher                                          |
| C2          | CP_Elec_6.3x5.3                        |     1    | 100uF       | 10V or higher                                          |
| C3, C4      | 0805                                   |     2    | 100nF       |                                                        |
| C5          | 0805                                   |     1    | 1uF         |                                                        |
| D1          | 1206                                   |     1    | PWR         | Amber LED                                              |
| F1          | 1206                                   |     1    | 1.5A        | PTC Fuse                                               |
| J1          | USB_A                                  |     1    | USB_A       | MOLEX 67643-3910                                       |
| J2          | USB_Micro-B                            |     1    | USB_PWR     | ADAM TECH MCR-AB1-S-RA-SMT-CS1-TR                      |
| J3          | RJ45_TRAFO_AMPHENOL                    |     1    | RJ45-TRAFO  | AMPHENOL LMJ1598824110DT39                             |
| R1,R2,R3,R4 | 0805                                   |     4    | 50R         | Ethernet termination resistors: should be 1% or better |
| R5          | 0805                                   |     1    | 150R        |                                                        |
| U1          | SOT23-6                                |     1    | USBLC6-2SC6 |                                                        |
| U2          | SOT223                                 |     1    | AP111733    |                                                        |
| U3          | Socket_Strip_Straight_1x16_Pitch2.00mm |     2    | OMEGA_2_2+  | Two 2mm 1x16 strip connectors                          |

## Photos
![image 1](/images/1.jpg)
![image 2](/images/2.jpg)
![image 3](/images/3.jpg)
![image 4](/images/4.jpg)
