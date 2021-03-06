# TF530 Revision 3

WARNING: I have just committed revision 3 of the board. I havent verified this yet.

This repository contains all the files needed to produce a copy of my accelerator board.

The CPLD Required is a XC9572XL-10VQ64

Everything in this repository is released under the GNU GPLv2. You may create or base commercial PCBs from the work in this repository but you must make the sources for all derivative work available. I have noticed some forks have removed copyright notices. This is a breach of the GPL. 

## Firmware / Requirements

  * Xilinx ISE, 14.7 (the final version - other versions may work but this is the one I support)
  * JTAG Adaptor

[For more information visit my channel](https://www.youtube.com/c/TerribleFire)

##License

This project and all the files contained are released under the GNU GPLv2. If you build a modified version of the board you must supply the end user with all the sources (this can be a web link).

## The TerribleFore 530 board (Revision 3)

Completely untested board link.... use with caution!!!! Do not come crying to me if it didnt work!!

http://dirtypcbs.com/store/designer/details/12476/2654/tf530-rev3-zip

##The TerribleFire 530 board (Revision 2)

This board is now in Beta. It may not work in all circumstances but it has been verified to boot AmigaOS 1.3, 2.05 and 3.1 and run various games and desktop apps at 25Mhz. Operation is not guarunteed to be crash free but will work in most "happy path" situations.

I have only verified the HD interface with Compact Flash cards.
I have verified this board boots on Amiga 500 Rev 5, 6a, 8.1a

I accept no responsibiltiy for any damage to any equipment that results from the use of this board. IT IS ENTIRELY AT YOUR OWN RISK!

## Installation

As of Revision 3 installation no longer needs the OVR and INT2 signals connected to the Amiga motherboard. The headers remain on the TF530 for testing but do not need to be connected although it should make little difference if they are connected. Well behaved Autoconfig devices will work alongside the TF530. The autoconfig space asserts the internal OVR signal when there are PICs remaining to be configured. After which the autoconfig will probe the standard bus. This revision should work on the A2000 (untested). 

IPL0 has not been routed because we only ever need to assert INT2 and/or INT6. 

## What does the board look like

The TF530 Rev 3 looks like...

![Image of Top of PCB](gerbers/tf530_rev3_top.png)

![Image of Bottom of PCB](gerbers/tf530_rev3_bottom.png)

## The BOM (WARNING! This is out of date)

| Qty | Value           | Device             | Package              | Parts                                                  | Description                   | 
|-----|-----------------|--------------------|----------------------|--------------------------------------------------------|-------------------------------|
| 1   |                 | MC68030RC          | MPGA128              | IC1                                                    | 68xxx PROCESSOR               | 
| 1   |                 | MC68881FN-SOC      | PLCC68-S             | IC2                                                    | 68xxx PROCESSOR               |
| 1   | 10K             | RESISTOR1206       | 1206                 | R3                                                     | Resistors                     |
| 13  | 10uF            | CAP_CERAMIC1206    | 1206                 | C1, C2, C3, C4, C5, C6, C7, C8, C9, C10, C11, C12, C13 | Ceramic Capacitors            | 
| 2   | 47K             | RESISTOR1206       | 1206                 | R1, R2                                                 | Resistors                     | 
| 2   | 74LVC1G17DBV    | 74LVC1G17DBV       | SOT23-5              | IC4, IC5                                               | Single Schmitt-Trigger Buffer | 
| 1   | A500            | JUMPER-2PTH        | 1X02                 | A500                                                   | Jumper                        | 
| 4   | AS7C4096A-12TIN | AS7C4096A-12TCN    | TSOP44-II            | U$1, U$2, U$3, U$4                                     |                               |  
| 1   | AUXPINS         | JUMPER-2PTH        | 1X02                 | AUXPINS                                                | Jumper                        | 
| 1   | BYPASS          | JUMPER-2PTH        | 1X02                 | BYPASS                                                 | Jumper (optional)           | 
| 3   | CAY16-103J4LF   | CAY16-103J4LF      | RESCAXE80P320X160-8N | RN1, RN2, RN3                                          | Res Thick Film Array 10K Ohm  | 
| 1   | CDIS            | JUMPER-2PTH        | 1X02                 | JP5                                                    | Jumper                        |
| 1   | CLOCKSEL        | JUMPER-3PTH        | 1X03                 | JP1                                                    |                               | 
| 1   | EXT5V           | JUMPER-2PTH        | 1X02                 | JP7                                                    | Jumper                        |
| 1   | IDE CONNECTOR   | PINHD-2X20         | 2X20                 | IDE                                                    | PIN HEADER                    |
| 1   | JTAG            | HEADER-1X6ROUND    | 1X06_ROUND           | JTAG                                                   | PIN HEADER                    |
| 1   | LM1117          | V_REG_LM1117SOT223 | SOT223               | U1                                                     | 3.3V Voltage  Regulator LM1117 |
| 1   | MC68000         | MC68000P           | DIL64                | X1                                                     | 68xxx PROCESSOR SOCKET        | 
| 1   | MMUDIS          | JUMPER-2PTH        | 1X02                 | JP3                                                    | Jumper                        | 
| 1   | SPI PORT        | PINHD-2X6          | 2X06                 | SPIPORT                                                | PIN HEADER                    | 
| 1   | X24MHZ          | OSCILLATOR         | OSC_7X5MM            | OSC1                                                   | 24 Mhz llators                   |
| 2   | XC9572XL-10VQ64   | XC9572XL-VQ64      | VQ64                 | XC9572XL(BUS), XC9572XL(RAM)                           |                               | 
