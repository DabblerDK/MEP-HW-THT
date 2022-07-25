# MEP-HW-THT
Multipurpose Expansion Port (MEP) Through-Hole Technology (THT) Hardware for OSGP Smart Meters in Denmark

This is the repository holding the Thrugh-Hole Technology (THT) Hardware for OSGP Smart Meters (i.e. Echelon or NES) in Denmark.
The scematics can be use in other countries too if you gain access to the Multipurpose Expansion Port (MEP) terminals.
Please:
- see https://github.com/OSGP-Alliance-MEP-and-Optical for further hardware specifiactions of these meters.
- see https://www.dabbler.dk for further information about this hardware project


Notes:
- The Gerber files has been generated acording to [JLCPCBs](https://jlcpcb.com/) specifications.
- We have not been able to source the correct MEP connector, so please note that the pin-numbers does NOT corespond to the pin numbers in the official documentation. Also you should NOT insert the 2x3 pin headers all the way into the PCB (the pins should be aligned with the PCB back side).
- The ESP32 can be programmed "on board" using the J5 connector. We usually don't put headers on that one, but simply insert the pins of a FTDI232 directly into the holes. WARNING: Some FTDI232's supply 5v EVEN when they are jumped to 3.3v. Don't use those - they'll fry your ESP32!
- The Schematic for the THT and the SMD versions are currently the same, but they might branch in the future
- J7 have two functions: before "on board" programming of the ESP32 a jumper must be set between ESP_PROGRAM and GND (pin 1 and 2) and the power jumper between pin 3 and 4 must be removed
- WARNING: Remove all jumpers from J7 before adjusting the buck converter voltage to 3.6v. When done set a jumper between pin 3 and 4 for nomal operation.


Bill of Materials:
| Component | Value | Type | Note |
| ------------- | ------------- | ------------- | ------------- |
| R1-R2 | 10K ohm | | |
| R3-R7 | 0 ohm | | Mount either R3 or R4 |
| D1 | 1N4007 | | |
| C1-C5 | 100nF | Non-polarized | |
| U1 | MAX3232 | DIP-16 | 3.3v version (warning: lots of fake chips out there) |
| U2 | ESP32-wroom-32e | 16MB recommended but currently NOT required |
| J1-J4 | DC-DC Buck converter | | i.e. https://www.ebay.com/itm/264731212329 |
| J6 | 2x3 Horizontal pin header | 2.54mm | i.e. https://www.ebay.com/itm/253023279430 |
| J7 | 2x2 Vertical pin header | 2.54mm | |
