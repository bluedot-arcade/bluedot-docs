---
layout: default
title: Installation
grand_parent: Boards
parent: BD845-PWB
nav_order: 1
permalink: /boards/bd845-pwb/installation
---

# BD845-PWB - Installation Guide
{: .no_toc }

How to install the board on diffent setups.
{: .fs-6 .fw-300 }

Installing the board is very easy and does not require any technical expertise. Although being easy, here is a detailed guide on how to do it.

{: .note }
This guide expects you to have original DDR cable wirings. Custom wirings or pads without cabinets are not covered in this guide. Use the [pinout diagram] to figure out how to adapt your setup.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Installation procedure

There are few simple steps to perform in order to install the board correctly.

{: .warning }
Perform the installation with power **OFF**! This will prevent damages to you and to the board.


### 1. Open the installation panel.

The board is installed inside the pad. The board is in a different panel depending on whether it is the left or right platform.
- **Left pad**: the board is located in the **upper-right** panel.
- **Right pad**: the board is located in the **upper-left** panel.

You have to unscrew the panel to access to the board installation slot. There are two units to disassemble: the top stainless-steel panel and a support metal structure underneath. 

After disassembling the panel you will now have access to the board installation slot.

### 2. Remove the original board.

Remove the board that is already present by unscrewing it and disconnecting the cables. There are only 4 screws in the corners keeping the board in place. 

When removing the board handle it from the borders to avoid further damages to it and store it in a ESD bag if you have one.

Also, be sure to clean any dust or other contaminants inside the panel. This will extend the life of the new board.

### 3. Install the BD845-PWB board.

Install the new board by screwing it down. This clone board is of the same size of the original one. Mounting holes should align correctly with the already present spacer screws.

{: .warning }
Do not lay down the board directly onto the metal plate. This will cause electrical shorts! Use spacer screws in each corner or apply an isolant layer between the metal plate and the board.

### 4. Connect the cables.

If you have the original DDR wiring there should be 6 cables:
- 4 cables with 7 wires and a 11 pins connector (Arrow panel cable)
- 1 cable with 12 wires and a 13 pins connector (Comm port cable).
- 1 cable with 4 wires and 4 pins connector (Power cable).

Follow the wiring diagram below, and always double check connectors orientation before powering it up.

![BD845-PWB-Wiring](/assets/images/bd845-pwb/v1.1.0/bd845-pwb-wiring-v1.1.0.jpg)
Cable wiring diagram using original DDR cabinet wirings.
{: .text-center }

### 5. Configure DIP switches.

Configure DIP switches in the bottom of the board according to your preference. 

Check [DIP switches] section for more information.

#### DDR Cabinet with DDR game

| DIP switch option            | Recommended value | 
|:-----------------------------|:------------------|
| Light on press               | OFF               | 
| Boot mode                    | OFF               |
| Debounce                     | ON/OFF            |
| Legacy mode                  | ON                |

This setup requires the legacy mode option to be set to **ON**. The game will not pass the booting phase IO Check otherwise.

#### DDR Cabinet with Stepmania/OpenITG with JPAC + LumenAR/LITBoard or Minimaid

| DIP switch option            | Recommended value | 
|:-----------------------------|:------------------|
| Light on press               | OFF               | 
| Boot mode                    | OFF               |
| Debounce                     | ON/OFF            |
| Legacy mode                  | OFF               |

#### DDR Cabinet with Stepmania/OpenITG with JPAC and no lights control board.

| DIP switch option            | Recommended value | 
|:-----------------------------|:------------------|
| Light on press               | ON                | 
| Boot mode                    | OFF               |
| Debounce                     | ON/OFF            |
| Legacy mode                  | OFF               |


[DIP switches]: /boards/bd845-pwb#dip-switches
[pinout diagram]: /boards/bd845-pwb#pinout-diagram