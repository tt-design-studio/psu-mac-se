## Mac SE PSU Project Overview

[Purchase boards link](https://www.tindie.com/products/ttdesign/diy-macintosh-se30-se-ac-dc-power-supply-board/)

![](/images/PSU_SE_3D_Rendering.jpg)

This project is for a design of a modern replacement of the AC/DC power supply board for the Apple Macintosh SE/30 and SE using all new components. It is mainly intended to be a DIY project to build on your own.

What follows are some notes to aid in the build configuration and component selection. 

## Power Supply Specs

Here's a table of the build options for the different Mean Well IRM modules and their voltage rails.

| Voltage Rail | Original Spec | IRM-10  | IRM-15 | IRM-45 | IRM-60 |
| ----- | ------------- | ------- | ------ | ------ | ------ |
| +5 V  | 6 A           | -       | -      | 8 A    | 10 A   |
| +12 V | 3.35 A        | -       | -      | 3.8 A  | 5 A    |
| -12 V | 0.5 A         | 0.850 A | 1.25 A | -      | -      |

Table 1: PSU Module Specs

Note, the power draw on the -12 V rail in a typical SE/30 setup is ~ 0.1 A.

## Supplier Project Links

### Board version 0.4

This version added a pluggable terminal for the ASTEC version of the power supply. The project links do not include the LED (D1) and the resistor (R1).

Phoenix Contact - Qty 1: P/N 1755749 and Qty 1: P/N 1757022

- [Mouser](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=d27a74f39d)
- [Digikey](https://www.digikey.com/en/mylists/list/7I77MKNK71)

### Board versions 0.2 and 0.3

- [Mouser](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=ec51f88d00)

- [Digikey](https://www.digikey.com/en/mylists/list/53G5CF5PMB)

### Cable Assembly

#### Modular cable assembly (connector on both ends)

The modular cable approach tries to balance the ease of assembly with the standard practice of using a crimped wire and connector for wire to board applications. If an issue develops with the cable, it can be more easily replaced. The trade-off is it adds two components for the connectors and some small additional contact resistance.

- [Mouser]()
- [Digikey]()

#### Direct board soldering

Note: Typically PSU wires have a terminal crimped to the wire end ([example](https://www.digikey.com/en/products/detail/te-connectivity-amp-connectors/170338-1/1861092)) and then the terminal is soldered to the board. This prevents solder from wicking into the cable which weakens the cable and the terminal provides strain relief by holding onto the insulator.

Molex 10 pin, 225 mm, 18 AWG, single ended for soldering wires directly to the board

- [Mouser](https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=94fdc6ba0d)

- [Digikey](https://www.digikey.com/en/mylists/list/Y2ULEIMUVL)

## BOM and Assembly Notes

| Note No. | BOM Notes                                                    |
| -------- | ------------------------------------------------------------ |
| 1        | You can probably transfer the working fuse from the old PCBA if you would like (v0.3 note: the ASTEC variant fuse is physically larger and cannot be reused), or use one like the one suggested in the cart link. |
| 2        | The board is designed for all new components, so the old Sony connector does not need to be harvested. There are two AC connector options for the type of PSU chassis. J2 is for the Sony variant, which uses 3 pins directly soldered to the board. J3 is for Apple variant. For the the Apple variant, you may want to buy an extra J3 considering note 3. |
| 3        | One pin (out of the 4) is removed from J3 to create a keyed connector to prevent reversing the connection. Check your original board to see which pin is missing while using the locking tab for the orientation. An easy way to do remove the pin is to hold the connector body in a vise and heat the pin closer to the plastic base with a soldering iron while holding the pin with pliers. Pull the pin out when it starts to give, which will likely happen very quickly. |
| 4        | The Mean Well IRM-45 series power supplies appear to be interchangable with the IRM-60 series to allow for more sourcing options and slightly reduce cost |

## Power Cable Assembly

The PCB legend includes a voltage and color guide per the original PSU designs to help with assembly of the cable and confirming the voltages with a multimeter.

### 1. Connector Info

- **Connector Type:** Molex Mini-Fit Jr 5557 series
- **Part Number:** 0039012105
- **Number of Pins:** 10
- **Gender:** Receptacle (female)
- **Quantity:** 2 or 1 for direct soldering to board

### 2. Wire Specifications

- **Wire Gauge:** 18 AWG
- **Wire Type:** UL 1061
- **Wire Type:** Flexible multi-stranded
- **Length:** 20 cm (with connector on both ends) or 22.5-30 cm for a single connector with direct soldering to the board
- **Quantity:** 10 wires total per the color coding (if desired)

### 4. Terminal Specifications

- **Terminal Type:** Molex Mini-Fit Jr 5556 series
- **Gender:** Female
- **Part Number:** 0039000046
- **Quantity:** 20 (one for each wire end)

### 5. Pin-Out and Color Coding

| Pin Number | Signal Name | Wire Color |
| ---------- | ----------- | ---------- |
| 1          | GND         | Black      |
| 2          | GND         | Black      |
| 3          | GND         | Black      |
| 4          | +5V         | Orange     |
| 5          | +12V        | Yellow     |
| 6          | -12V        | Green      |
| 7          | GND         | Black      |
| 8          | GND         | Black      |
| 9          | +5V         | Orange     |
| 10         | +12V        | Red        |

Table 2: Pin / signal / wire color code listing for both ends of the harnesss.

![](/images/cable_harness_layout.png)

Figure 1: Pin / wire color code layout for both ends of the harnesss (this view is of the **<u>back side</u>** of the connector).

### 6. Cable Protection

Ensure you reuse the grommet/gland/strain relief from the original power supply to protect the wire insulation from abraision from the edges of the sheet metal enclosure. Small vibrations over time can wear away the insulation and cause a short circuit.
