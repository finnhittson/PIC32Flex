# PIC32Flex 

PIC32Flex is a breakout board for the PIC32MX170F256B. This repo holds schematic revision information, how to fabricate this board for yourself, and examples on how to use the board. I designed this board for rapid prototyping, testing, and better wire management for projects and circuits that use the PIC32 as a microcontroller. Specifically, I made PIC32Flex for Stanford's ME218 mechatronics course sequence which exclusively uses the PIC32 as the microcontroller for all student projects. For this reason, it is wired to interface directly with the [MPLAB Snap](https://www.microchip.com/en-us/development-tool/pg164100) and the [CP2102 debugger](https://www.silabs.com/interface/usb-bridges/classic/device.cp2102?tab=specs).

<p align="center">
  <img src="images/rendered_side_view.png" alt="Image 2" height=300px>
  <img src="images/rendered_top_view.png" alt="Image 1" height=300px>
</p>

## Download and Modification

To modify or view a revision of PIC32Flex, download any version of the board from the `hardware/` directory. All revisions were made using [KiCad 8.0](https://www.kicad.org/download/) which is a free PCB design software. Once downloaded, extract the file into the directory of your choice and open the `PIC32Flex.kicad_pro` file. This should open up a the KiCad start page where you can choose to view and then modify the schematic, PCB layout, and most other features related to the board. KiCad files are not backwards compatible so you may need to upgrade to KiCad 8.0 if you are working with an older version. If you download the most recent version and open the schematic editor, you will find the following.

<p align="center">
  <img src="images/schematic.png" alt="Image 2" height=300px>
</p>

Opening the PCB editor of the latest version should present the following PCB layout.

<p align="center">
  <img src="images/pcb_layout.png" alt="Image 2" height=300px>
</p>

## Usage

To build this board for yourself you need to send the gerber files to a PCB manufacturer. Most used are [JLCPCN](https://jlcpcb.com/) and [PCBWay](https://www.pcbway.com/). After unzipping the downloaded board file, upload the `gerber.zip` file to a PCB manufacturer of your choice. It is recommended that the PIC32Flex is reflowed and not hand soldered. For this reason, be sure to include a stencil in your board purchase since they are not included by default. Board lead time is typically longer than a week. With the board ordered you will also need to order components for board population. Components can be ordered from [DigiKey](digikey.com) or [Mouser](mouser.com). With either of these suppliers you can upload the bill of materials file, `bom.csv`, and it will usually parse and place all the items in the cart. Below is a cost breakdown for the devices necessary for board population.

<div align="center">

| Qty | Reference   | Value           | Mfn                     | Mfn PN                         | Cost ($/device) |
|-----|-------------|-----------------|-------------------------|--------------------------------|-----------------|
| 1   | C3          | 10u             | Murata Electronics      | GRM155R60J106ME05D             | $0.10  |
| 3   | C1, C2, C4  | 0.1u            | Murata Electronics      | GRM155R71C104KA88J             | $0.08  |
| 1   | D1          | LED             | Inolux                  | IN-S42BTR                      | $0.28  |
| 1   | R2          | 10k             | YAGEO                   | RC0402JR-0710KL                | $0.10  |
| 2   | R1, R3      | 1k              | YAGEO                   | RC0402JR-071KL                 | $0.10  |
| 1   | SW1         | Reset           | C&K                     | PTS636SM50JSMTR LFS            | $0.25  |
| 1   | U1          | PIC32MX170F256B | Microchip Technology    | PIC32MX170F256B-I/ML           | $4.86  |
|     |             |                 |                         | Total Device Cost              | $6.03  |
|     |             |                 |                         | Total Board Cost w/ stencil    | $9.11  |
|     |             |                 |                         | Total Costs                    | $15.14 |

</div>

This cost analysis does not include sales tax and shipping. These cost usually eclipse the cost of the board and components themselves if you plan to only make a few.

