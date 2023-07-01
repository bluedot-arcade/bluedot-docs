---
layout: default
title: BD845-PWB
parent: Boards
has_children: true
nav_order: 1
permalink: /boards/bd845-pwb
has_toc: false
---

# BD845-PWB
{: .no_toc }

A clone of the original DanceDanceRevolution GN845-PWB(B) Stage I/O board.
{: .fs-6 .fw-300 }

[Github project]{: .btn .mr-2 .mb-4 }
[Latest firmware]{: .btn .mr-2 .mb-4 }
[Schematic diagrams]{: .btn .mr-2 .mb-4 }
[Mechanical drawings]{: .btn .mr-2 .mb-4 }

![BD845-PWB-Front](/assets/images/bd845-pwb/v1.1.0/bd845-pwb-front-v1.1.0.png)
PCB Front layer
{: .text-center }

- [Overview]
- [Tech specs]
- [Pinout diagram]
- [DIP switches]
- [Installation]
- [Programming]
- [FAQs]
- [Troubleshooting]
- [Konami GN845-PWB(B)]

## Overview

This board was designed as a drop in replacement clone board for the Konami [GN845-PWB(B)](/boards/bd845-pwb/gn845-pwb) Stage I/O board. 

It emulates the original DDR Stage I/O communication protocol boot sequence allowing to run the game without an IO Check Bypass. Sensor masking is also supported. Other protocol features are currently unknown.

It also provides additional features such as debouncing and a Light-On-Press mode that lights up the arrow light when pressed without the need of an external lights driver board.

The board can also be re-programmed with a custom/updated firmware. 

### If you have this board
* Identify your version by looking at the version written under the logo. If you don't have the latest version you can still get schematic diagrams from the [changelog page].
* Read the [installation guide][Installation] if you want to know how to install it correctly.
* Read the [FAQs] which will answer to a lot of your questions.

![BD845-PWB-Back](/assets/images/bd845-pwb/v1.1.0/bd845-pwb-back-v1.1.0.png)
PCB Back layer
{: .text-center }

## Tech specs

|:---------------------------------|:------------------|
| Input voltage (recommended)      | 12V               | 
| Input voltage (limit)            | 9-15V             |
| Power consumption (idle) [^1]    | 0.22W             |
| Light power (max) @ +12V         | 15W               |
| Light driver current (max)       | 1.25A             |
| Output response time (max) [^2]  | 50uS              |
| Width                            | 110mm             |
| Length                           | 185mm             |
| Height                           | 15mm              |
| Weight                           | 90gr              |
| Mounting hole diameter           | 4mm               |
| Product code                     | 001               |

## Pinout diagram

![BD845-PWB-Pinout](/assets/images/bd845-pwb/v1.1.0/bd845-pwb-pinout-v1.1.0.jpg)

## DIP switches

On the bottom side of the board there are four DIP switches that allows you to configure some of the board parameters.

To turn **ON** an option put the corresponding toggle in the up position corresponding to the ON text. The lower position
corresponds to **OFF**.

Check the [installation guide][Installation] to know the proper configuration based on your cabinet setup.

![BD845-PWB-DIP-SW](/assets/images/bd845-pwb/v1.1.0/bd845-pwb-dip-sw-v1.1.0.png)

### Light on press
{: .no_toc }

When **ON** the panel light will light up when the panel is pressed. This way you don't need an external lights driver.

When **OFF** the lights will be controlled by the external lights driver which can be, for example, the KSYS573 for original DDR games or a LumenAR for Stepmania setups.

### Boot mode
{: .no_toc }

When **ON** the BOOT0 pin of the STM32 MCU will be tied to +3V3. This puts the board into a forced program mode.

When **OFF** the BOOT0 pin of the STM32 MCU will be tied to GND. This puts the board into run mode.

In almost any case this must be set to **OFF**. Refer to the official STM32 documentation for more information about the BOOT0 pin.

{: .warning }
If this option is set to **ON** the board will not work! For normal operation it must be set to **OFF**.

### Debounce
{: .no_toc }

When **ON** the sensor debouncing will be enabled. When sensors are released they will still be considered pressed for an additional 4 milliseconds.

When **OFF** the sensor debouncing will be disabled.

[What is debouncing?](/boards/bd845-pwb/faqs#what-is-debouncing)

{: .note }
Some games like Stepmania supports software debouncing. If software debouncing is performed by the game already it is recommended to set this option **OFF**.

### Legacy mode
{: .no_toc }

When **ON** the board will listen for original DDR boot command and reply to it. This is required to pass the IO Check on original DDR games.

When **OFF** the board will ignore the DDR boot command.

----

[^1]: Calculated when the board is idle with all lights and sensors off.

[^2]: This is the time required for the output to react to a change of a sensor input.

[Overview]: /boards/bd845-pwb#overview
[Tech specs]: /boards/bd845-pwb#tech-specs
[Pinout diagram]: /boards/bd845-pwb#pinout-diagram
[DIP switches]: /boards/bd845-pwb#dip-switches
[Installation]: /boards/bd845-pwb/installation
[Programming]: /boards/bd845-pwb/programming
[FAQs]: /boards/bd845-pwb/faqs
[Troubleshooting]: /boards/bd845-pwb/troubleshooting
[Konami GN845-PWB(B)]: /boards/bd845-pwb/gn845-pwb
[What is debouncing?]: /boards/bd845-pwb/faqs#what-is-debouncing
[Github project]: https://github.com/bluedot-arcade/bd845-pwb-board
[Schematic diagrams]: https://github.com/bluedot-arcade/bd845-pwb-board/blob/master/sch_bd845-pwb.pdf
[Latest firmware]: https://github.com/bluedot-arcade/bd845-pwb-firmware/releases
[Mechanical drawings]: https://github.com/bluedot-arcade/bd845-pwb-board/blob/master/draw_bd845-pwb.pdf
[changelog page]: /boards/bd845-pwb/changelog
