---
lang: hu-HU
layout: faq
section: nds-bootstrap
title: GYIK & hibaelhárítás
long_title: nds-bootstrap GYIK & helyreállítás
description: GYIK & hibaelhárítás az nds-bootstrap-hez
---

#### Miért kapok fehér képernyőt, ha megpróbálok betölteni egy játékot az SD kártyáról?
- Először ellenőrizd [az nds-bootstrap kompatibilitás listát ](https://docs.google.com/spreadsheets/d/1LRTkXOUXraTMjg1eedz_f7b5jiuyMv2x6e_jY_nyHSc/htmlview#gid=0) legyél biztos benne, hogy a játékod kompatiblis
- Próbáld meg az összes csalás kikapcsolásával annál a játéknál, mert néhány csalás nem kompatibilis az nds-bootstrap-pel jelenleg; az <kbd class="l">L</kbd> gombot tudod használni egy játék összes csalásának kikapcsolásához
- Ha korábban működött, töröld a `fatTable` és a `patchOffsetCache` mappát az `sd:/_nds/nds-bootstrap/` könyvtárból

#### nds-bootstrap hibaelhárítás
Ha problémát tapasztalsz az nds-bootstrap használatakor, itt vannak a lépések, hogyan oldhatod meg azt.

1. Futtasd a játékokat más beállításokkal beleértve az ARM9 CPU sebességet, DS/DSi módot, hang minőséget, Card Read DMA-t, stb.
2. Töröld a `fatTable` és a `patchOffsetCache` mappákat az `sd:/_nds/nds-bootstrap/` mappában
3. Valószínűleg nem olyan nagy kérdés; kérdezz a [Discord szerveren](https://discord.gg/yD3spjv)

Ha a szerver azt mondja, hogy ez egy nds-bootstrap hiba, ellenőrizd, hogy a játék jelentésre került-e már a GitHub-ra. Ellenőrizd a lezárt jegyeket is, arra az esetre, ha valamelyik hibát lezártuk egy másik preferálása miatt. Ha nem tartozik hozzá GitHub hiba, akkor csinálj neki egy újat.

Továbbá ne felejtsd el hozzáadni a [kompatibilitási listához](https://wiki.ds-homebrew.com/nds-bootstrap/testing) a Google Sheets-en.

#### Miért vannak problémák a ROM betöltéssel, ha natívan futnak?
Az nds-bootstrap a ROM funkciókat patcheli, hogy fussanak SD kártyáról, és a ROM hardkódolt a Slot-1 olvasásra. Van néhány időzítési és AP intézkedés (amik nagy része már eltávolított), mind a kettő okozhatja, hogy a ROM-ok nem megfelelően működnek.

#### Miért használjak nds-bootstrap-et a hagyományos flashcard helyett?
- Bizonyos kompatibilis ROM-ok betöltésre kerülnek a RAM-ba, gyorsabb betöltési időket lehetővé téve mint a normál cartridge-eké
- Kibővítheted a VRAM memória buszt 32 bitesre
- Használd a DSi további CPU sebességét, lehetővé téve a jobb teljesítményt néhány játéknál
- Az audiód minőségét javíthatod 48 kHz-re
- Használható a DSi mód, amivel elérhetők a DSi funkciók
- Bizonyos cartridge-ek használatakor lehetőséged van az IR használatára az alkalmazásodból
- Az nds-bootstrap nyílt forrású, így a fejlesztől mindig tudják frissíteni a hibák és egyéb dolgok javítása érdekében, még akkor is, ha a cég megszűnik
- A DS Memory Expansion Pak emulált, így azok a játékok amiknek szüksége van rá működni fognak
- Az alsó és felső képernyő cserélhető a kompatibilis játékoknál a még kényelmesebb játékmenetért, vagy olyan rendszerekhez, ahol törött vagy eltávolított a képernyő

#### Donor ROM-ok
A legtöbb SDK5 játék kiválasztható Donor ROM-nak (ami a TWiLight Menu++-on keresztül tehető meg). A Donor ROM ARM7 binárisa másolásra kerül az nds-bootstrap által és kicseréli az ARM7 binárist a játékban, amit indítani próbálsz. Ez lehetővé teszi bizonyos SDK5 játékoknak a betöltését és mentését.

#### Mi az esti fordítás (nightly) és hol szerezhetem be?
Az esti fordítás egy fordítás a legutolsó változtatásokkal. Az esti fordítások instabilak lehetnek, de tartalmazzák a legutolsó hibajavításokat. Az nds-bootstrap esti fordításokat beszerezheted [innen](https://github.com/TWLBot/Builds/raw/master/nds-bootstrap.7z).

#### Miért nem működnek a csalásaim?
A mód, ahogy az E csalás típusok implementálva vannak az nds-bootstrap-ben hibás, ami azt jelenti, hogy az esetek felében működnek. A csalás, amit használsz valószínűleg ilyen típusú. Ez nem a csalás adatbázis hibája, hanem inkább az nds-bootstrap-pé. Kérjük ne kérd ezen csalások törlését az adatbázisból.

További információkért a csalásokról látogass el [ide](https://wiki.ds-homebrew.com/ds-index/retail-roms#action-replay-cheats).

