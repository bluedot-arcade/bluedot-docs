---
layout: default
title: Installation
grand_parent: Boards
parent: BD845-PWB
nav_order: 1
permalink: /boards/bd845-pwb/installation
---

# BD845-PWB - Installation Guide

{: .note-title }
> TODO 
>
> Add installation steps.

## Typical setups

A list of typical setups and the recommended DIP switches configuration.

Check [DIP switches](/boards/bd845-pwb/#dip-switches) section for more information.

### DDR Cabinet with DDR game

| DIP switch option            | Recommended value | 
|:-----------------------------|:------------------|
| Light on press               | OFF               | 
| Boot mode                    | OFF               |
| Debounce                     | ON/OFF            |
| Legacy mode                  | ON                |

### DDR Cabinet with Stepmania/OpenITG with JPAC + LumenAR/LITBoard or Minimaid

| DIP switch option            | Recommended value | 
|:-----------------------------|:------------------|
| Light on press               | OFF               | 
| Boot mode                    | OFF               |
| Debounce                     | ON/OFF            |
| Legacy mode                  | OFF               |

### DDR Cabinet with Stepmania/OpenITG with JPAC

This setup does not have a lights driver board. Setting light on press mode to **ON** is recommended.

| DIP switch option            | Recommended value | 
|:-----------------------------|:------------------|
| Light on press               | ON                | 
| Boot mode                    | OFF               |
| Debounce                     | ON/OFF            |
| Legacy mode                  | OFF               |