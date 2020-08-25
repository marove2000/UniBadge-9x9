# UniBadge 9x9
A simple badge PCP with 9x9 LEDs. Create symbols, figures, pixel art by just soldering LEDs to the spots you want. No programming needed.

<img src="images/unibadge_front.png" width=400px alt="UniBadge 9x9 front"> <img src="images/unibadge_back.png" width=400px alt="UniBadge 9x9 front">

## Bill of Material
| Designator | Package            | Quantity | Designation                    |
| ---------- | ------------------ | -------- | ------------------------------ |
| BT1        | 2-Pin connector    | 1        | Battery-Holder (2xAAA)         |
| C1, C2     | 100nF              | 2        |                                |
| C3         | 0805 SMD capacitor | 1        | variable (see capaictor table) |
| D1-D81     | 0805 SMD LED       | 1-81     | LED Red                        |
| Q1-Q9      | Mosfet             | 9        | 2N7002                         |
| R1, R2     | 0805 SMD resistor  | 2        | 100k                           |
| R3-R11     | 0805 SMD resistor  | 9        | variable (see resistor table)  |
| SW1        | SMD switch         | 1        |                                |
| U1         | SOIC-8 NE555       | 1        |                                |
| U2         | SOP-16 CD4017      | 1        |                                |

### Capacitor-Table for C3
The frequency is determined by the value of C3. Always on: The frequency is so fast, it looks like all (soldered) LEDs are always on.

| Frequency          | Capacitor Value (C3)       |
| ------------------ | -------------------------- |
| slow (~5Hz)        | 1µF                        |
| faster (~50Hz)     | 10nF                       |
| always on (~110Hz) | 4700pF                     |

### Resistor-Table for R3-R11
Resistor values depend on the number of soldered LEDs per row (refer to the table below). Note that you can only choose one LED color per row.

| Number of LEDs | Resistor value for red LEDs | Resistor value for green LEDs (bright!) |
| -------------- | --------------------------- | --------------------------------------- |
| 1              | 56 Ohm                      | 110 Ohm                                 |
| 2              | 27 Ohm                      | 56 Ohm                                  |
| 3              | 18 Ohm                      | 36 Ohm                                  |
| 4              | 15 Ohm                      | 30 Ohm                                  |
| 5              | 11 Ohm                      | 22 Ohm                                  |
| 6              | 9,1 Ohm                     | 18 Ohm                                  |
| 7              | 8,2 Ohm                     | 16 Ohm                                  |
| 8              | 6,8 Ohm                     | 13 Ohm                                  |
| 9              | 6,2 Ohm                     | 12 Ohm                                  |

## Manual
TBD

## Copyright and Authorship
- PCB layout: [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) - [Thomas Schmid and Timo Schindler](https://www.binary-kitchen.de)
- Manual (TeX): [LPPL](https://www.latex-project.org/lppl.txt) - [Marei Peischl](https://peitex.de)
- Manual (pdf): [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) - [Binary Kitchen e.V.](https://www.binary-kitchen.de)

## Acknowledgments
A big thank you goes to Thomas Schmid, Clemens Grünewald and Sandra Schweighart for all the help!

The calculation of the frequency done with https://ohmslawcalculator.com/555-astable-calculator

## Misc: Logo to PCB
The Logos to the PCB are created with an Inkscape plugin

- download and install https://github.com/badgeek/svg2shenzhen
- Inkscape: Extensions -> svg2shenzhen -> Prepare Document
- Choose Layer where to place the logo
- Rename: remove "disabled" from layer-name
- Place logo
- Extensions -> svg2shenshen -> Export Kicad (Kicad-module)
- Copy .kicad_mod in .pretty-folder
- Place as part