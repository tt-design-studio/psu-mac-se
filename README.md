## Project Overview

This project is for a design of a more powerful replacement of the AC/DC power supply board for the Apple Macintosh SE/30 and SE using all new components. It is mainly intended to be a DIY project to build on your own.

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

### Versions 0.2 and v0.3 boards

#### Mouser
https://www.mouser.com/ProjectManager/ProjectDetail.aspx?AccessID=ec51f88d00

#### Digikey
https://www.digikey.com/en/mylists/list/53G5CF5PMB

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
- **Quantity:** 2 (one on each end of the cable assembly)

### 2. Wire Specifications

- **Wire Gauge:** 18 AWG
- **Wire Type:** UL 1061
- **Wire Type:** Flexible multi-stranded
- **Length:** 20 cm (with connector on both ends) or 27-30 cm for a single connector with direct soldering to the board
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
