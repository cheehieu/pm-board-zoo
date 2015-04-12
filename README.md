pm-board-zoo
============

<img src="http://niftyhedgehog.com/pm-board-zoo/images/line_display.jpg">

## Overview
The PM Board Zoo is a collection of animal-inspired PCBs designed as adapter boards for simplifying power measurements with various TI Sitara ARM microprocessor evaluation modules (EVMs). Each EVM has current shunt resistors and 2-pin headers to output the bus and shunt voltages of a given supply. However, due to routing constaints, these 2-pin headers are sporadically (dis)organized on the EVM boards. This makes it difficult and tedious to measure the power consumption on different EVMs using the same automated setup. Each adapter board in the PM Board Zoo was created to organize the header pins into a more manageable interface, consolidating the 2-pin headers into a simplified, standardized connector for interfacing with an automated digital multimeter setup or other power monitoring equipment such as the [AfternoonCape](http://niftyhedgehog.com/afternoon-cape).

This repository includes:
* Altium library, schematic, and board files
* PCB gerbers and drill files
* Bill of materials
* AfternoonCape config file

PM Board Zoo Animals:
* Duck (AM335x GP EVM)
* Dog (AM437x GP EVM Alpha)
* Cat (AM43xx ePOS EVM Alpha)
* Turtle (AM43xx ePOS EVM Beta)
* IDK, X15, TBD


## Cat
<img src="http://niftyhedgehog.com/pm-board-zoo/images/cat_mount.jpg">
The "cat" adapter board was designed for an alpha revision of the AM43xx ePOS (electronic point of sale) EVM. This revision had 26 supplies to be monitored. It features two rows of 16x2 headers for interfacing with a Keithley DMM with 2 switching multiplexer modules. 

*Note: On this alpha revision of the AM43xx ePOS EVM, the VDDS_CTM supply incorrectly powers some other 1.8V supplies including VDDS_SRAM_CORE_BG, VDDS_SRAM_MPU_BB, VDDS_PLL_DDR, PLL_CORE_LCD, VDDS_PLL_MPU, and VDDS_OSC. This double counts the current consumption, so a post-measurement workaround must be implemented to subtract the extra current.*

| Power Supply | Jumper            | Shunt | Shunt (Ohm) |      |
|--------------|-------------------|-------|-------------|------|
| 1            | VDD_CORE          | J59   | R543        | 0.05 |
| 2            | VDD_MPU           | J60   | R544        | 0.05 |
| 3            | VDDS_DDR          | J40   | R36         | 0.05 |
| 4            | VDDS_SRAM_CORE_BG | J53   | R617        | 1.00 |
| 5            | VDDS_SRAM_MPU_BB  | J54   | R618        | 1.00 |
| 6            | VDDS_PLL_DDR      | J56   | R620        | 2.00 |
| 7            | VDDS_PLL_CORE_LCD | J55   | R619        | 1.00 |
| 8            | VDDS_PLL_MPU      | J57   | R621        | 2.00 |
| 9            | VDDS_OSC          | J87   | R203        | 2.00 |
| 10           | VDDS_CTM*         | J82   | R540        | 2.00 |
| 11           | VDDA_MC_ADC       | J85   | R541        | 2.00 |
| 12           | VDDA_TS_ADC       | J86   | R542        | 2.00 |
| 13           | VDDS              | J81   | R21         | 1.00 |
| 14           | VDDA1P8V_USB0/1   | J83   | R539        | 1.00 |
| 15           | VDDA3P3V_USB0/1   | J84   | R34         | 1.00 |
| 16           | VDDSHV1           | J41   | R10         | 1.00 |
| 17           | VDDSHV2           | J42   | R11         | 1.00 |
| 18           | VDDSHV3           | J43   | R12         | 1.00 |
| 19           | VDDSHV5           | J46   | R14         | 1.00 |
| 20           | VDDSHV6           | J47   | R15         | 1.00 |
| 21           | VDDSHV7           | J48   | R16         | 1.00 |
| 22           | VDDSHV8           | J49   | R17         | 1.00 |
| 23           | VDDSHV9           | J50   | R19         | 1.00 |
| 24           | VDDSHV10          | J51   | R20         | 1.00 |
| 25           | VDDSHV11          | J52   | R22         | 1.00 |
| 26           | VDD_TPM           | J92   | R588        | 2.00 |
| 27           | VDDS_TPM          | J91   | R546        | 2.00 |


## Dog
<img src="http://niftyhedgehog.com/pm-board-zoo/images/dog_mount.jpg">

The "dog" adapter board was designed for the AM437x GP (general purpose) EVM. The red solder mask color was selected in honor of Clifford the Big Red Dog.

| Power Supply | Jumper       | Shunt | Shunt (Ohm) |      |
|--------------|--------------|-------|-------------|------|
| 1            | VDD_CORE     | J93   | R526        | 0.05 |
| 2            | VDD_MPU      | J94   | R527        | 0.05 |
| 3            | VDDS_DDR     | J41   | R38         | 0.05 |
| 4            | V1_8D_AM437X | J81   | R23         | 0.10 |
| 5            | V3_3D_AM437X | J92   | R24         | 0.10 |
| 6            | VDDS_DDR_MEM | J40   | R87         | 0.05 |
| 7            | VDDS_RTC     | J91   | R695        | 0.00 |


## Duck
<img src="http://niftyhedgehog.com/pm-board-zoo/images/duck_mount.jpg">

The "duck" adapter board was designed for the AM335x GP (general purpose) EVM, which has current shunt resistors on 20 different processor supply rails. Unfortunately, the VDD_CORE and VDD_MPU supplies do not have power measurement headers. In order to measure these bus and shunt voltages, wires were soldered directly to the 4-terminal shunt resistors, and then connected to the power measurement adapter board via right-angle 2-pin male/female headers.

|    | Power Supply      | Jumper | Shunt | Shunt (Ohm) |
|----|-------------------|--------|-------|-------------|
| 1  | VDD_CORE          | XX     | R32   | 0.05        |
| 2  | VDD_MPU           | XX     | R46   | 0.05        |
| 3  | VDDS_RTC          | J35    | R505  | 2.00        |
| 4  | VDDS_DDR          | J20    | R508  | 0.24        |
| 5  | VDDS              | J21    | R498  | 0.24        |
| 6  | VDDS_SRAM_CORE_BG | J23    | R500  | 2.00        |
| 7  | VDDS_SRAM_MPU_BB  | J25    | R499  | 2.00        |
| 8  | VDDS_PLL_DDR      | J33    | R507  | 2.00        |
| 9  | VDDS_PLL_CORE_LCD | J24    | R503  | 2.00        |
| 10 | VDDS_PLL_MPU      | J22    | R497  | 2.00        |
| 11 | VDDS_OSC          | J29    | R506  | 2.00        |
| 12 | VDDA1P8V_USB0/1   | J28    | R502  | 1.00        |
| 13 | VDDA3P3V_USB0/1   | J31    | R504  | 2.00        |
| 14 | VDDA_ADC          | J27    | R501  | 1.00        |
| 15 | VDDSHV1           | J26    | R493  | 0.24        |
| 16 | VDDSHV2           | J38    | R545  | 0.24        |
| 17 | VDDSHV3           | J39    | R546  | 0.24        |
| 18 | VDDSHV4           | J30    | R494  | 0.24        |
| 19 | VDDSHV5           | J32    | R495  | 0.24        |
| 20 | VDDSHV6           | J34    | R496  | 0.24        |
| 21 | VDDSDDRMEM        | J41    | R513  | 0.24        |


## Turtle
<img src="http://niftyhedgehog.com/pm-board-zoo/images/turtle_mount.jpg">

The "turtle" adapter board was designed for a beta revision of the AM43xx ePOS (electronic point of sale) EVM. The turtle's tail was purposely designed to avoid mechanical collision with a standoff leg for the EVM's display.

| Power Supply | Jumper       | Shunt | Shunt (Ohm) |      |
|--------------|--------------|-------|-------------|------|
| 1            | VDD_CORE     | J59   | R543        | 0.05 |
| 2            | VDD_MPU      | J60   | R544        | 0.05 |
| 3            | VDDS_DDR     | J40   | R36         | 0.05 |
| 4            | V1_8D_AM437X | J83   | R23         | 0.10 |
| 5            | V3_3D_AM437X | J84   | R25         | 0.10 |
