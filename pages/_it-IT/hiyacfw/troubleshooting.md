---
lang: it-IT
layout: wiki
section: hiyacfw
title: Risoluzione dei problemi
category: other
description: Risoluzione dei problemi per hiyaCFW
---

## #-2435-8325
If your Nintendo DSi shows an error in this format when booting, with the # being a number, that means that bootstage 2 thinks something is wrong with your SDNAND. This is usually fixed by [reinstalling hiyaCFW](installing-hiyacfw).

## "An error has occurred"
When the Nintendo DSi Menu detects a problem it will usually show this generic error message, some of the causes are:

#### The free space bug
The Nintendo DSi Menu has a bug when checking the free space on large storage devices. While this can't occur on the actual NAND (since the chip is only 256 MiB), it can happen when using an SD card.

What works and what doesn't goes by every other range of two gibibytes. For example, having 0-2 GiB of free space works, but 2-4 GiB doesn't. The same goes for 4-6 GiB vs 6-8 GiB, up until you get to the size of your SD card.

The latest hiyaCFW version can create dummy files to work around this, so make sure that you download the latest version of [hiyaCFW](https://github.com/RocketRobz/hiyaCFW/releases/latest/download/hiyaCFW.7z) and copy `hiya.dsi` from "for SDNAND SD card" to the root of your SD card.

#### Over 39 titles
The Nintendo DSi Menu has a limit of 39 titles. If you have more than that, delete some from the folders in `sd:/title` or use [TMFH](https://github.com/JeffRuLz/TMFH/releases/latest) to uninstall them.

#### Too much space used by DSiWare
There is also a limit of 200 blocks (25MB) for DSiWare in the `00030004` folder. This can be worked around by installing as system apps using [TMFH](https://github.com/JeffRuLz/TMFH/releases/latest).

#### Invalid title
There are several things you need to take into account when adding titles to hiyaCFW:
- Game card dumps cannot be run without being using a [forwarder](forwarders)
- Homebrew need to be built correctly using modern tools to work from the Nintendo DSi Menu
