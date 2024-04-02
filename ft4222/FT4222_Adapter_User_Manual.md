# Introduction

This adapter is a USB to SPI/I2C bridge based on FTDI's FT4222 chip.

It can be used with the usbio utility(https://github.com/strongtek/usbio).

# Feature

Features of FT4222 include:

* USB 2.0 high speed.

* Support single, dual and quad lines for SPI master.

* SCLK can support up to 30MHz for SPI master.

* Up to 53.8Mbps data rate for quad lines SPI master.

* Support I2C master interface, conforming to I2C v2.1 and v3.0.

* Support I2C speed modes: SM(100Kbps), FM(400kbps), FM+(1Mbps) and HS(3.4Mbps).

* +5V USB VBUS detection engine.

* Integrated 5V-3.3V-1.8V regulators.

* Configurable IO pin output drive strength.

Features of this FT4222 adapter include:

* USB-B to host.

* 20-pin 2.54mm DIP connector to target board.

* IO voltage can be supplied by internal regulator or external source.
 
* Can provide 3.3V and 5V output voltage to target board.

* I2C pull-up resisters can be enabled or disabled by jumpers.

Features of usbio include:

* Support SPI master and I2C master mode of FT4222.

* Programable with Tcl script.

* Tcl command for LibFT4222 APIs.

* Include work around of FT4222 errata.

* Compatible with PC. OS support Windows, Linux and MacOS

* Compatible with Raspberry Pi.
  
# Deliverables

* FT4222 adapter box.

* USB-A to USB-B cable.

* 20-pin 2.54mm dupont lines.

# Hardware Configuration

## Box outline

![Top](https://raw.githubusercontent.com/strongtek/adapter/main/ft4222/resource/top.png)

![Side](https://raw.githubusercontent.com/strongtek/adapter/main/ft4222/resource/side.png)

## Pin assignment

The pin assignment of the 20-Pin DIP connector:

| Function | Pin | Pin | Function  |
| -------- | --- | --- | --------- |
| VIO_EXT  | 1   | 2   | 5V_EXT    |
| SPI_CSn  | 3   | 4   | SPI_SS    |
| N.C.     | 5   | 6   | SPI_SCLK  |
| SPI_MOSI | 7   | 8   | SPI_MISO  |
| SPI_IO2  | 9   | 10  | SPI_IO3   |
| N.C.     | 11  | 12  | N.C.      |
| I2C_SCL  | 13  | 14  | I2C_SDA   |
| N.C.     | 15  | 16  | N.C.      |
| GPIO_2   | 17  | 18  | GPIO_3    |
| GND      | 19  | 20  | GND       |

## In-box jumpers

There are some jumper on the PCB of the adapter, for tweaking the adapter's behavior.

You need to open the box with a screwdriver or by hands to make adjustment.

| Jumper | Purpose | Description | Default |
| ------ | ------- | ----------- | ------- |
| J3     | VIO select | Connect to "EXT": VIO are supplied by pin-1 of the 20-Pin connector. Connect to "3.3V": VIO are supplied by FT4222's 3.3V regulator. |  3.3V |
| J5     | 5V output enable | Connect to output 5V on pin-2 of the 20-Pin connector. | Connect |
| J6     | 3.3V/External VIO enable | Connect to output 3.3V on pin-1 of the 20-Pin connector, or input external voltage from pin-1 of the 20-Pin connector. Must connect if you want to use external VIO. | Connect |
| J9     | I2C_SCL pullup | Connect to pull-up I2C_SCL with a 10K ohm resistor. | Connect |
| J10    | I2C_SDA pullup | Connect to pull-up I2C_SDA with a 10K ohm resistor. | Connect |

Do NOT change other jumpers unless you know what you are doing.

## Electronic characters

Please refer to the FT4222 datasheet(https://ftdichip.com/wp-content/uploads/2020/08/DS_FT4222H.pdf) for electronic charaters detail.

# Software

Most software utilities designed for FT4222 can be used with this adapter.

Especially, usbio, an open source Tcl wrapper of LibFT4222, can be used.
For details about the usbio utility, please refer to its github(https://github.com/strongtek/usbio).
As an open source utility, it provides no binary executables. You can build it from source code. But If you do need a binary executable, please contact us.

