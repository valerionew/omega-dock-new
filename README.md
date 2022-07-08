# Omega dock\new

Project released under CC-BY-SA 4.0 license  
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by-sa/4.0/)

![layout 1](/images/layout.jpg)

1. [Project status](#project-status)  
1. [Project description](#project-description)  
1. [BOM](#bom)  
1. [Photos](#photos) 

<a href="https://oshpark.com/shared_projects/xYpCcduu"><img src="https://oshpark.com/packs/media/images/badge-5f4e3bf4bf68f72ff88bd92e0089e9cf.png" alt="Order from OSH Park"></img></a>

If you want to discuss the project, join [the thread in the onion community forum](https://community.onion.io/topic/2284/my-omega-2-2-dock-new)

## Project status
Current version is tested and working.  
No new versions are planned at the moment

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

## Build instructions 
The following is my response to [issue #10](https://github.com/valerionew/omega-dock-new/issues/10), where i described the assembly process and tips and tricks that i use. I think it might be helpfull to report it here.

First of all: 
**I strongly encourage anyone who has any basic electronic soldering experience, to get the boards from wherever they want and solder his own. It's much more satisfying and, if you've never done SMD before, you'll have a chance to learn it**. 
Why do i say so? Because this board has a very few parts, big SMD pads and reasonably big components. Once you learn SMD soldering, they are even easier to solder than through hole parts. Don't feel uncomfortable, SMD parts are great.

### Boards
The easiest thing is to just get it from OSHPark. They have good prices, deliver three boards and the shipping is free worldwide. I've already uploaded my v1.0 design on their website, so that you can order it with just a few clicks.
[Here](https://oshpark.com/shared_projects/xYpCcduu) is the link.


### Soldering
So, what you need to get started? 
* **A soldering iron**. I use the *Hakko FX-888D* with the tip that comes with it, but that's upon your preferences and your budget. A cheaper AliExpress iron will also do the job.
* **Solder**. I use *Sn60Pb40 solder*, and i recommend you to do the same. I prefer 0.5 mm, but you can go with whatever you want, i suggest to stay in the 0.4-0.75 range.
* **Some flux**. I use it in a *felt tip dispensing pen*, but again, you can use whatever you prefer.
* **Solder wick**. I use whatever i can find, not really a problem. 
* **Fine tweezers**, if possible ESD safe. I use the *Vetus ESD-11*, but yet again you can use whatever you want.
* **Patience!** A lot of that! After all, you are learning something new

That's all you need. Given that you already have a soldering iron, the other things are cheap. Patience is free.
About the method, these are the steps i do for a 2 pin component:
1. Put some flux on the pads. No skimping with that
1. Heat one pad with your iron and put some solder on it. You'll learn the right amount with the time, but don't worry, you'll have the chance to remove the excess with the wick after (or before, if you prefer) you've soldered the part. 
1. Grab the part with the tweezers, reheat the pad and place the component. Don't be too quick or solder won't stick to the part. Hold the part with the tweezers until the solder becomes solid. Then release.
1. Solder the other pin, adding some solder.
1. Inspect. Check, by eyes or with a magnifying glass, that there is a joint between each pad and the component.

That's it. For ICs and parts with more pins i usually solder one pad first, make sure that the alignment is correct, then solder the diagonally opposite pin, then all the others, but the steps are basically the same.
Same rule as THT soldering applies: lower profile parts first.

### Parts
For the passives you can basically pick whatever you want, as long as they are the same value, same package, and same tolerance. All those specs and quantities are shown in the table up here.

The only two ICs here are U1 and U2. 

U1 is USBLC6-2SC6. This is a TVS and diode protection array, specifically designed for USB ESD protection. It is not *strictly* necessary, but given that it's a very cheap part and provides additional protection, why not use it. Moreover, the docks from omega use a similar protection too. However, if you aren't going to use it short pad 1 with pad 6, and pad 3 with pad 4. **DON'T short pad 2 and pad 5. That would be a short on the power supply**

U2 is just a basic 1117-3.3v. A linear 3.3v regulator. You can pick a 1117 3.3v or even another linear regulator, as long as it has the same package, the same footprint, and it's capable of supplying at least 500mA.

There is a 1206 PTC fuse, anything from 1A to 1.5A should be good. 

Connector choice is critical to this project. I've indicated the exact part that i've used. If you can't find them you have two choices:
1. Pick another part. You can go to whatever supplier, shop or distributor and find a part that would fit mechanically in the pins. Make sure to check the distance between the mechanical mounting pins and the electrical pins. Also  **check the pinout, they are not always the same, especially in RJ45 connectors.**. 
In USB and RJ45 connectors, the distance from the last pin in the back, and the back of the connector **is critical**: it should be **no more** than what is in the parts that i've indicated, or the two polarized capacitors won't fit. If the RJ45 part has LED pins, they can be cut before soldering, so no big deal.
1. Modify the board. You can download the KiCad files and modify the footprints in order to fit your particular connector. Again,  **check the pinout**.

Then, pick two parts of 1x16 2mm female header, and you are done. 


## Photos
![image 1](/images/1.jpg)
![image 2](/images/2.jpg)
![image 3](/images/3.jpg)
![image 4](/images/4.jpg)
