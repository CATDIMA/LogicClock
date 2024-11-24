# Logic Clock
## Logic clock based on 564-series ICs and VFD tubes 

![img](https://github.com/CATDIMA/LogicClock/blob/main/images/device.jpg?raw=true)
*The finished device*

## Description
This project was inspired by [cmos_clock](https://github.com/Radionews/cmos_clock) from [Radionews](https://github.com/Radionews) user. My clock is essentially a fork of his project, because it almost completely repeats the circuitry with some differences caused by the use of a different series of chips and the used display.

The clock built mostly on CMOS 564 series ICs, it is a military-grade soviet IC series. There are some TTL chips from 514 and 533 series for controlling IV-12 VFD tubes. Of course there are a lot of regular electronic components.

The eight IV-12 (ИВ-12) VFD tubes are placed on a separate PCB for fitting the display in different case designs. Six tubes are used for numbers display, two tubes are displaying a separator represented as a dash between hours and minutes and between minutes and seconds.

To obtain the required frequencies (1 Hz and 500 Hz), a frequency obtained from a quartz generator is used. Quartz generator is built on a separate board which contains a quartz oscillator and CMOS inverter IC. You can use any frequency source in this project instead of the one I suggested in this repo. The frequency comes to the P2 connector and is divided by n-times by a divider to obtain 500 Hz, this is the only condition that must be met. You have to set a division factor by setting jampers on P3-P5 PBS connectors (to set division factor see CD4059 datasheet). I use an old quartz oscillator on 100 kHz in a glass case for more aesthetic appearance. So, my division factor is 200.

## Building
The bit L in division factor settings must always be set to logical zero. There are no other special assembly instructions. You can order PCBs from any PCB manufacturer, get somewhere all details from from components.xlsx and solder everything together in one device. It would be better if you put all these boards in a nice case.

I made my case out of acrylic and PETG plastic. I've posted DXF and STL files for case parts, so you can repeat it. For connection the display to the main board you have to use IDC-20 flat cable. For case assembly you need some fasteners:

* M3x6 screw, 4 pcs
* M3x10 screw, 2 pcs
* M3x16 screw, 2 pcs
* M3 nut, 22 pcs
* M3 nut with nylon ring, 4 pcs
* M3 washer, 2 pcs
* M3 reinforced washer, 10 pcs
* M3x70 threaded stud, 4 pcs
* M3 hex standoff 7.5mm, 4pcs

## Usage

There are three button and one switch. The switch turns the power on and off. Buttons do this: reset seconds, increment minutes, increment hours. The сlock doesn't store time and doesn't count time without the power. If the power supply is turned off, the time will be reset.

## Like this project?
:star2: You can always give a star on the project to say thanks

*OR*

:moneybag: You can donate me:
> BTC: bc1q8rcdhq4pfn45pf647afhjtdn6qhrheu3hngn9m

:heart: I will print on a 3D printer with this money and multiply plastic waste in the ocean and microplastics in the food chain
