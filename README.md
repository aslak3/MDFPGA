# MDFPGA: a HUB75 display controller base board using a Pi Pico W and an iCE40UP5K

![MDFPGA PCB](/images/MDFPGA.png)

A [schematic](MDFPGA.pdf) is included here, along with the [KiCAD](https://www.kicad.org)
data files, which are in KiCAD 6 format.

## PCB design

The PCB is a 4 layer board easily built by any random PCB house.

## Project overview

This board is the hardware for my Matrix Display project, which is spread across three repos: this one, [a repo holding the Pico W firmware](https://github.com/aslak3/matrix-display), and [an optional one that holds the HUB75 display controller](https://github.com/aslak3/hub75-controller), which is implemented in Verilog.

Once up and running, you will have a 64 x 32 LED matrix display, presenting information from your Home Assistant system or, in theory, any other system that publish data in a suitable format via MQTT.

## Hardware description

* Power via 5V barrel jack
* A Pi Pico W (obviously)
* A [DS3231](https://www.analog.com/media/en/technical-documentation/data-sheets/DS3231.pdf) (PDF) I2C Real Time Clock
  * CR122t battery backup
* IDC16 HUB75 connector attached to the Pico W
* Buzzer
* iCE40UP FPGA
  * [N25Q32A](https://www.mouser.co.uk/datasheet/2/12/Micron_Datasheet_N25Q032A_RevJ-1880047.pdf) (PDF) 32MBit SPI Flash
  * IDC16 HUB75 connector attached to the FPGA
  * LED

## Possible gotchas

The board revision included here fixes some minor issues I found in the board I use on a daily basis:

* The CR1225 conenctor has been moved a few mm to make it easier to insert and remove the battery.
* The screw terminals, which power the HUB75 panel, have been pointed in the oposite direction, making them easier to access.
* More vias have been added around the 1.2V power pin on the linear regulator.

## References

* [Matrix Display](https://github.com/aslak3/matrix-display) The projects main repository. which holds the firmware source code.
* [HUB75 Controller](https://github.com/aslak3/hub75-controller) A HUB75 LED matrix controller implemented in Verilog.
