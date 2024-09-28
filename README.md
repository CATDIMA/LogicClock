# Logic Clock [Work in progress]
## Logic clock based on 564-series ICs and VFD lamps 

## Description
This project was inspired by [cmos_clock](https://github.com/Radionews/cmos_clock) from [Radionews](https://github.com/Radionews) user. My clock is essentially a fork of his project, because it almost completely repeats the circuitry with some differences caused by the use of a different series of chips and the used display.

The clock built mostly on CMOS 564 series ICs, it is a military-grade soviet IC series. There are some TTL chips from 514 and 533 series for controlling IV-12 VFD lamps. Of course there are a lot of regular electronic components.

The eight IV-12 (ИВ-12) VFD lamps are placed on a separate PCB for fitting the display in different case designs. Six lamps are used for numbers display, two lamps are displaying a separator represented as a dash between hours and minutes and between minutes and seconds.

To obtain the required frequencies (1 Hz and 500 Hz), a frequency obtained from a quartz generator is used. Quartz generator is built on a separate board which contains a quartz oscillator and CMOS inverter IC. You can use any frequency source in this project. The frequency comes to the P2 connector and is divided by n-times by a divider to obtain 500 Hz, this is the only condition that must be met. You have to set a division factor by setting jampers on P3-P5 PBS connectors (to set division factor see CD4059 datasheet). I use an old quartz oscillator on 100 kHz in a glass case for more aesthetic appearance. So, my division factor is 200.

## Current state
The project is under development and it can contain errors

Steps:
- [X] Decide on the parts to be used: IC series, etc.
- [X] Develop the schematics
- [X] Test developed schematics in simulation
- [X] Test some blocks by building their prototypes
- [X] Trace the PCBs
- [ ] Assemble and test a real device
- [ ] Design and print a case

## Building
The bit L in division factor settings must always be set to logical zero. There are no other special assembly instructions. You can order PCBs from any PCB manufacturer, get somewhere all details from from BOM.xlsx and solder everything together in one device. It would be better if you put all these boards in a nice case. 

## Usage

There are three button and one switch. The switch turns the power on and off. Buttons do this: reset seconds, increment minutes, increment hours. The сlock doesn't store time and doesn't count time without the power. If the power supply is turned off, the time will be reset.

## Known issues

Chip U28 (564ТВ1, two JK triggers - CD4027) used as counting trigger can be removed. It will affect both of clock dividers ICs: U26, U27 (564ИЕ15 - CD4059) - their division factors has to be changed, bit L must always be connected to logical one. The PCB layout will also be affected and must be changed.

## Like this project?
:star2: You can always give a star on the project to say thanks

*OR*

:moneybag: You can donate me:
> BTC: bc1q8rcdhq4pfn45pf647afhjtdn6qhrheu3hngn9m

:heart: I will print on a 3D printer with this money and multiply plastic waste in the ocean and microplastics in the food chain