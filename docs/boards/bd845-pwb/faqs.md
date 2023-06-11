---
layout: default
title: FAQs
grand_parent: Boards
parent: BD845-PWB
nav_order: 3
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

Yes! This board was designed as a clone of the original GN845-PWB(B) DanceDanceRevolution Stage IO PCB. Just swap this board with the original one and you are ready to play.

## Are lights supported?

Yes! Just like the original board. There is also an additional feature that turn on the panel light it is pressed without the need of an external lights driver. Check [here][light on press mode] for more info.

## Do I need an external lights controller?

Yes if you want the lights to be turned on/off by the game, just like the original board. But if you just want to turn the panel light on when it is pressed you can enable the [LIGHT ON PRESS][light on press mode] mode by simply toggling a switch on the board.

## Can it drive original neon lights?

Yes! Each channel can output a max of 20W (1.66A current max at +12V output).

## Is it protected against ESD (Electric Static Discharge)?

Yes! Each connector has a protection against ESD and overvoltage spikes. But it can fail in extreme situations. Proper handling will prevent these incidents. Try not to touch the electronic components with your bare fingers. Avoid handling the printed circuit board whilst it is powered and only handle by the edges to minimise the risk of electrostatic discharge damage.

## Is there a short-circuit protection?

Partially. The +12V rail is not protected. The +3.3V is. 

That means that if an accidental short of the +12V rail with ground happens a large current will flow if the power supply does not provide short-circuit protection. These can cause big damage. The MCU and other components that use +3.3V rail are be guarded by a resettable fuse. 

If you want to be extra careful you can add an in-line fuse holder to the +12V cable just before the connector.

## Can I use FSR sensors with this board?

No. This board is not designed to support FSRs. 

They will probably work but that is not the ideal way to handle them. FSRs are analog sensors that change their resistance when compressed. They need special circuitry to set thresholds and have their value read and processed and this board does not provide such circuitry.

## Why is there a fifth connector named "Pad Center"?

The original board also has a fifth channel on the top-right corner. When I designed this board I imagined it to be there for an additional panel like the center one. 

It is a fully working IO channel but you will probably never use it. Maybe in the future can be used in combination with an expansion board to do something cool.

## What is the purpose of the "Status" LED indicator?

Just to have a visual feedback on the current state of the program running onto the board. A list of states and corresponding blinking patterns can be found [here]().

{: .note-title }
> TODO
>
> Fix link to status led blinking patterns.

## What is debouncing?

Original sensors act like mechanical switches. When they are pressed/released the connection can be made and broken several times in a very short period before stabilizing on an open/closed state. This can cause it to fire multiple times. You can even get a way-off when playing if this is not handled properly.

The original board does not provide a debouncing mechanism. The BD845-PWB uses a software debouncing mechanism that can be enabled by simply toggling a switch on the board.

When enabled the panel will remain in the pressed state for an additional 4 milliseconds after the pressure on the sensors is released.

## Does it pass the IO Check when KSYS573 is booting?

Yes! By being a clone it will work with original hardware and games. The game will boot correctly.
However there are still some parts of the original communication protocol between the KSYS573 and the
stage IO that are still not well understood but they are not critical like the IO check during boot.

## How did you implement the original DDR communication protocol?

This board emulates the response of the original board to the "Boot IO Check" in the same way that the [MAME] KSYS573 driver do.

This way every DDR game that boots correctly on MAME will also boot with this clone board. 

Reverse engineering the communication protocol is not an easy task since it is a very strange and slow serial communication protocol. That is why we decided to use a proven emulation method.

## Can I upload a custom firmware?

By being an open-source project there is nothing that stops you from uploading a firmware on the MCU.
Check the dedicated [programming guide] on how to upload a firmware.

## Can I use this board on a cabinet with Stepmania/ITG?

Yes! Just like the original board. You can disable the legacy mode option since it is not required on this setup.

## Can I use this board on a Pump It Up cabinet?

No. Currently it is not meant to be used on Pump It Up stages.

## Why should I get this board instead of the original one?

If you need this board it probably means that the original one you have is broken. In most cases it can be fixed by replacing some components but it requires some time and expertise. But if the broken component is the CPLD there is not very much you can do unfortunately. 

It is not very easy to find original working boards these days.

Also, in the datasheet of the XC9536 CPLD Xilinx guarantees a data retention of minimum 20 years. While it does not specify if it is calculated when unpowered or during normal operation, in the worst case that means original boards will probably fail in the following years.

The BD845-PWB board aim to resolve these problems. Also by being open-source it is designed to be repaired and updated, and if we stop producing them nothing prevents someone else to make it instead.

## My board is not working. What can I do?

Oh no! Check the [troubleshooting guide]. If that does not help, you can [contact us].

[light on press mode]: /boards/bd845-pwb#light-on-press
[programming guide]: /boards/bd845-pwb/programming
[troubleshooting guide]: /boards/bd845-pwb/troubleshooting
[contact us]: /contacts
[MAME]: https://www.mamedev.org/
