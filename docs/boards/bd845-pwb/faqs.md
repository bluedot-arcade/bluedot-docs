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

Yes! This board was designed as a clone of the original GN845-PWB(B) DanceDanceRevolution Stage IO PCB. Just swap this board with the original one and you are ready to make amazing scores.

## Are lights supported?

Yes! Just like the original board. There is also an additional feature that turn on the light when the panel is pressed without the need of an external lights driver (check [here]() for more info).

{: .note-title }
> TODO
>
> Fix link to light-on-press mode documentation.

## Do I need an external lights controller?

Yes if you want the lights to be turned on/off by the game, just like the original board. But if you just want to turn the light on when the pad is pressed you can enable the [LIGHT ON PRESS]() mode by simply toggling a switch on the board.

{: .note-title }
> TODO
>
> Fix link to light-on-press mode documentation.

## Can it drive original neon lights?

Yes! Each channel can output a max of 36W (3A current max at 12V output).

## Is it protected against ESD (Electric Static Discharge)?

Each connector has a protection against ESD and overvoltage spikes. But it can fail in extreme situations. Proper handling will prevent these incidents. Try not to touch the electronic components with your bare fingers. Avoid handling the printed circuit board whilst it is powered and only handle by the edges to minimise the risk of electrostatic discharge damage.

## Is there a short-circuit protection?

Partially. The +12V rail is not protected. The +3.3V is. 

That means that if an accidental short of the +12V rail with ground happens a large current will flow if the power supply does not provide short-circuit protection. These can cause big damage especially to the light drivers. The MCU and other components that use +3.3V rail will be guarded by a resettable fuse. 

If you want to be extra careful you can add an in-line fuse holder to the +12V cable just before the connector.

## Can I use FSR sensors with this board?

This board is not designed to support FSRs. They will probably work but that is not the ideal way to handle them. 

FSRs are analog sensors that change their resistance when compressed. They need special circuitry to set thresholds and have their value read and processed and this board does not provide such circuitry.

## Why is there a fifth connector named "Pad Center"?

The original board also has a fifth channel on the top-right corner. When I designed this board I imagined it to be there for an additional pad like the center one. 

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

## My board is not working. What can I do?

Oh no! Check the [troubleshooting guide]. If that does not help, you can [contact us].

## Does it pass the IO Check when KSYS573 is booting?

Yes! By being a clone it will work with original hardware and games. The game will boot correctly.
However there are still some parts of the original communication protocol between the KSYS573 and the
stage IO that are still not well understood but they are not critical like the IO check during boot.

## Can I upload a custom firmware?

By being an open-source project there is nothing that stops you from uploading a firmware on the MCU.
Check the dedicated [programming guide] on how to upload a firmware.



[programming guide]: /boards/bd845-pwb/programming
[troubleshooting guide]: /boards/bd845-pwb/troubleshooting
[contact us]: /contacts