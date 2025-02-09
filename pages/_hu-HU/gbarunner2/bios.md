---
lang: hu-HU
layout: wiki
section: gBARunner2
title: GBA BIOS infó
description: Információk a GBA BIOS-ról és a dumpolás módjáról
---

A GBARunner2-nek, hogy betöltse a címeket szüksége van egy GBA BIOS dumpra. A GBARunner2 frissebb build-jei (amik együtt érkeznek a TWiLight Menu++-szal) rendelkeznek [Normatt Open Source BIOS-ával](https://github.com/Normmatt/gba_bios) előre beépítve. Mivel nem egy egzakt másolat, egy hivatalos BIOS dumpja növeli a kompatibilitást. A következő metódusokkal dumpolhatsz egy hivatalos GBA BIOS-t.

### Dumpolási útmutatók

- [Wii (nem családi verzió)/GameCube + link cable dumper](https://github.com/FIX94/gba-link-cable-dumper)
- [3DS-sel, a legtöbb Virtual Console címmel](https://glazedbelmont.github.io/gbabiosdump/#virtual-console-title-from-a-3ds) (nem lehet GBA vagy nem-Nintendo (Game Gear) Virtual Console cím)
- [GBA vagy DS Phat/Lite egy GBA Flashcard-dal](https://glazedbelmont.github.io/gbabiosdump/#gameboy-advance-sp-micro-ds-ds-lite)

A BIOS dumpolása után át kell azt nevezni `bios.bin`-nek, majd az `sd:/`, `sd:/gba/`, vagy az `sd:/_gba/` könyvtárba kell rakni, hogy a GBARunner2 tudja olvasni.

Ellenőrizheted, hogy a BIOS-od megfelelő dump összehasonlítva a következő ellenőrző összegekkel:

**CRC32:** `81977335`

**MD5:** `a860e8c0b6d573d191e4ec7db1b1e4f6`

**SHA1:** `300c20df6731a33952ded8c436f7f186d25d3492`

**SHA256:** `fd2547724b505f487e6dcb29ec2ecff3af35a841a77ab2e85fd87350abd36570`
