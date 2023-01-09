---
layout: default
title: FAQs
grand_parent: Boards
parent: BD845-PWB
nav_order: 2
permalink: /boards/bd845-pwb/faqs
---

# BD845-PWB - FAQs
{: .no_toc }

Frequently asked questions about the board.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Do I just need to swap the boards?

Yes! This board was designed as a clone of the original GN845-PWB DDR Stage IO PCB. Just swap this board with the original one and you are ready to make amazing scores.

## Are lights supported?

Yes! Just like the original board. There is also an additional feature that turn on the light when the panel is pressed without an external lights driver (check [here]() for more info).

## Do I need an external lights controller?

Yes if you want the lights to be turned on/off by the game, just like the original board. But if you just want to turn the light on when the pad is pressed you can enable the [LIGHT ON PRESS]() mode by simply toggling a switch on the board.

## Can it drive original neon lights?

Yes! Each channel can output a max of 36W (3A current max at 12V output).

## Is it protected against ESD (Electric Static Discharge)?

Each connector has a protection against ESD and overvoltage spikes. But it can fail in extreme situations. Proper handling will prevent these incidents. Try not to touch the electronic components with your bare fingers.

## Is there a short-circuit protection?

Partially. The +12V rail is not protected. The +3.3V is. 

That means that if an accidental short of the +12V rail with ground happens a large current will flow if the power supply does not provide short-circuit protection. These can cause big damage especially on the light drivers. Instead, the MCU and other components that use +3.3V rail will be guarded by a resettable fuse. 

If you want to be extra careful you can add an in-line fuse holder to the +12V cable just before the connector.

## Can I use FSR sensors with this board?

This board is not designed to support FSRs. They will probably work but that is not the ideal way to handle them. 

FSRs are analog sensors that change their resistance when compressed. They need special circuitry to set thresholds and have their value read and this board does not provide such circuitry.

## Why is there a fifth connector named "Pad Center"?

The original board also has a fifth channel on the top-right corner. When I designed this board I imagined it to be there for an additional pad like the center one. 

It is a fully working IO channel but you will probably never use it. Maybe in the future can be used in combination with an expansion board to do something cool.

## What is the purpose of the "Status" LED indicator?

Just to have a visual feedback on the current state of the program running onto the board. A list of states and corresponding blinking patterns can be found [here]().

## What is debouncing?

Original sensors act like mechanical switches. When they are pressed/released the connection can be made and broken several times in a very short period before stabilizing on an open/closed state. This can cause it to fire multiple times. You can even get a way-off when playing if this is not handled properly.

The original board provides a very basic debouncing mechanism by using schmitt triggers and filters. The BD845-PWB uses a software debouncing mechanism that can be enabled by simply toggling a switch on the board.

## My board is not working. What can I do?

Oh no! Check the [troubleshoot]() page. If that does not help, you can [contact us]().

