# Omega dock\new

Project released under CC-BY-SA 4.0 license  
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](http://creativecommons.org/licenses/by-sa/4.0/)

![layout 1](/images/layout.jpg)


### Project status
v0.9 tested, working with some bodges  
v1.0 boards not tested yet

### Project description 
This project is a dock, compabile with Onion Omega 2 and Omega 2+. 
It features:  
* Microusb connector for power supply with onboard linear regulation  
* USB host connector  
* Ethernet connector

I've tried to add all the features that i needed for a project, in the smallest form factor possible: the Onion Omega 2/2+ size.

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


![image 1](/images/1.jpg)
![image 2](/images/2.jpg)
![image 3](/images/3.jpg)
![image 4](/images/4.jpg)
