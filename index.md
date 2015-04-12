---
layout: project
title: pm-board-zoo
subtitle: Various Texas Instruments EVM adapter boards for monitoring device power consumption.
---

<img src="http://niftyhedgehog.com/pm-board-zoo/images/line_display.jpg">

## Overview
The PM Board Zoo is a collection of animal-inspired PCBs designed as adapter boards for simplifying power measurements with various TI Sitara ARM microprocessor evaluation modules (EVMs). Each EVM has current shunt resistors and 2-pin headers to output the bus and shunt voltages of a given supply. However, due to routing constaints, these 2-pin headers are sporadically placed on the EVM boards. Each adapter board in the PM Board Zoo consolidates these 2-pin headers into a simplified, standardized connector for interfacing with an automated digital multimeter setup or other power monitoring equipment such as the [AfternoonCape](http://niftyhedgehog.com/afternoon-cape).

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

*Supply detail table

## Dog
<img src="http://niftyhedgehog.com/pm-board-zoo/images/dog_mount.jpg">
The "dog" adapter board was designed for the AM437x GP (general purpose) EVM.

*Supply detail table

## Duck
<img src="http://niftyhedgehog.com/pm-board-zoo/images/duck_mount.jpg">
The "duck" adapter board was designed for the AM335x GP (general purpose) EVM. The VDD_CORE and VDD_MPU supplies do not have 2-pin headers on this EVM, so they must be connected externally via the right-angle 2-pin header inputs.

*Supply detail table

## Turtle
<img src="http://niftyhedgehog.com/pm-board-zoo/images/turtle_mount.jpg">
The "turtle" adapter board was designed for a beta revision of the AM43xx ePOS (electronic point of sale) EVM. The tail was purposely designed to avoid mechanical collision with a standoff leg for the EVM's display.

*Supply detail table
