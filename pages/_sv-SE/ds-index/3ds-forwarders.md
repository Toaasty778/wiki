---
lang: sv-SE
layout: wiki
section: ds-index
category: guides
title: DS Spel Forwarders (3DS)
description: Hur du skapar CIA forwarders att ha dina DS spel på 3DS:ens hemmeny
tabs:
  - 
    tab-sd-card: SD-kort
    tab-flashcard: Minneskort
---

HOME meny forwarders är ikoner i din HOME meny som tar dig till ett annat program som kör ikonen som angets. I detta fall så kan man lägga till DS-spel från SD-kortet (använder nds-bootstrap) eller från ett kompatibelt minneskort (via respektive kärna) till HOME-menyn för enklare åtkomst till spel.

DS spel måste dumpas till en digital `.nds`-format. Du kan dumpa dina DS spelkort med [GodMode9](https://3ds.hacks.guide/dumping-titles-and-game-cartridges#dumping-a-game-cartridge).
{:.alert .alert-info}

Denna sida förutsätter att du kör en modern CFW-miljö från [3ds.hacks.guide](https://3ds.hacks.guide).

Välj ett av följande att lägga till i HOME-menyn:

{% capture tab-sd-card %}

### Del 1: Få de nödvändiga filerna

Om du redan har Universal Updater installerad på din konsol så kan du hoppa över till steg 3.
{:.alert .alert-info}

1. Öppna FBI och välj `Remote Install`, sedan `Scan QR Code`
1. Skanna denna QR-kod för att installera den senaste versionen av [Universal-Updater](https://github.com/Universal-Team/Universal-Updater)<br> ![Universal-Updater QR kod](https://db.universal-team.net/assets/images/qr/universal-updater.cia.png)
1. Öppna Universal Updater från HOME-menyn
1. Installera paketet för NDSForwarder
1. NDSSkotare och dess nödvändiga filer är nu inställda i sina respektive platser

### Del 2: NDSForwarder
1. Starta Homebrew Launcher
1. I Homebrew Launcher, öppna `NDS Forwarder Generator`
1. Navigera till ditt spels plats och tryck press <kbd class="face">A</kbd>
1. Bekräfta att du vill installera genom att välja `Ja`
1. När det är installerat så kommer ditt spel nu att visas som en titel på din HOME-meny
{% endcapture %}
{% assign tab-sd-card = tab-sd-card | split: "////////" %}

{% capture tab-flashcard %}

Om du har några problem, läs FAQ:en på [GBAtemp tråden](https://gbatemp.net/threads/nds-forwarder-cias-for-your-home-menu.426174/).
{:.alert .alert-warning}

### Krav

3DS:

{% capture flashcards %}
De rekommenderade minneskorten är DSTT och Acekard 2i. If you want perfect game compatibility, get the SuperCard DSTWO/DSTWO PLUS. Den enda nackdelen är att det tömmer ditt systembatteri snabbare.

Om du har ett minneskort som fungerar med Apache Thunder's NTR Launcher, tveka inte att begära det [på GBAtemp tråden](https://gbatemp.net/threads/nds-forwarder-cias-for-your-home-menu.426174/). Var noga med att ange vilken bygg du använder (Normal eller Alt), och om `RESETSLOT1` är satt till `0` eller `1` i `sd:/nds/ntr_launcher.ini`.

Kompatibelt:
- [Acekard 2(i)](http://www.nds-card.com/ProShow.asp?ProID=160) (DSi-Enhanced games, inklusive nyare NTR-spel, fungerar inte.)
- [Acekard RPG](http://wiki.gbatemp.net/wiki/Acekard_RPG)
- [DSTT](http://www.nds-card.com/ProShow.asp?ProID=157)
- [DSTT Advance](http://kaze-tado.way-nifty.com/moo/images/2008/11/19/200811202.jpg)
- Galaxy Eagle
- M3 DS Real
- [M3 DS Simply](https://farm2.static.flickr.com/1333/752793411_d91b182eb7.jpg) (använder < 2 GB microSD-kort)
- [R4 DS](http://www.nds-card.com/ProShow.asp?ProID=141) (Original icke-SDHC version, använder < 2 GB microSD-kort)
- [R4 SDHC Snoopy](http://www.nds-card.com/ProShow.asp?ProID=567)
- [R4 SDHC RTS LITE](http://www.nds-card.com/ProShow.asp?ProID=450) ([www.r4isdhc.com](http://www.r4isdhc.com/))
- R4 SDHC Upgrade ([www.r4i-sdhc.com](http://www.r4i-sdhc.com/))
- [R4i3D](http://www.3ds-cart.com/en/other-flashcarts/35-r4i3d-revolution-cart-for-3ds-dsi-dsl-ds.html) ([www.r4i3d.com](http://www.r4i-sdhc.com/))
- [R4iDSN](http://3ds-flashcard.com/home/28-r4idsn-3ds.html)
- [R4i Gold](http://www.nds-card.com/ProShow.asp?ProID=330)
- [R4i Gold RTS](http://www.nds-card.com/ProShow.asp?ProID=149) ([www.r4ids.cn](http://www.r4ids.cn/))
- [R4i-SDHC](http://www.nds-card.com/ProShow.asp?ProID=146) ([www.r4i-sdhc.com](http://www.r4i-sdhc.com)) (Normal- och RTS-versioner)
- R4iTT ([www.r4itt.net](http://www.r4itt.net/)) (Purple card kan vara inkompatibel)
- [SuperCard DSONE](http://wiki.gbatemp.net/wiki/SuperCard_DSONEi)
- [SuperCard DSTWO](http://www.nds-card.com/ProShow.asp?ProID=135) (Normal och Plus versioner)

Otestade:
- R4i3D NEW (Använd R4iDSN mall och paket)

Delvis kompatibel:
- Ace 3DS+ (Spelkompatibilitet är dåligt, så sparning/ladding av sparfiler kraschar.)
- Gateway Blue Card (Spelkompatibilitet är dåligt, så sparning/ladding av sparfiler kraschar.)
- EX4DS (Spelkompatibilitet är dåligt, så sparning/ladding av sparfiler kraschar.)
- R4iLS (Spelkompatibilitet är dåligt, så sparning/ladding av sparfiler kraschar.)
- Kort med [www.r4isdhc.com.cn](http://www.r4isdhc.com.cn/) (Spelkompatibilitet är dåligt, så sparning/ladding av sparfiler kraschar.)

Inkompatibel:
- CykloDS (i)Evolution (Can automatiskt starta ROM:er men fungerar annorlunda från andra minneskort.)
- (i)Edge (Kan inte automatiskt starta en .nds ROM)
- R4 Gold Pro ([www.r4i-gold.com](http://www.r4i-gold.com) / [www.r4i-gold.me](http://www.r4i-gold.me)) (YSMenu (inte forwarder processen) klossar kortet)
- R4i3D (2012)
- R4 Infinity Dual Core
- R4 SDHC
- R4 SDHC Dual-Core ([www.r4isdhc.com / ](http://www.r4isdhc.com/)) (YSMenu (inte forwarder processen) klossar kortet)
{% endcapture %}

<details>
    <summary>Ett minneskort som stöds från denna lista</summary>
    <div class="details-content">
        {{ flashcards | markdownify }}
    </div>
</details>

PC:
- Ett 64-bitars operativsystem
- [Forwarder3-DS](https://www.dropbox.com/s/b9de5ii6vm3dxfn/Forwarder3DS-v2.9.6.zip?dl=0)
- Java 8 Uppdatering 251
- **Linux användare:** JavaFX
   - På Debianbaserade system kör [detta](https://gist.githubusercontent.com/puntillol59/7532b6583380baca236dcaf2d8f75b5c/raw/e8b9d193f8b24de941160c7292ec0bb3b997e98e/main.sh)
   - Arch: `sudo pacman -S java8-openjfx && sudo archlinux-java set java-8-openjdk/jre`

### Del 1: Komma igång
1. Ladda ner ett av dessa paket:
   - [Original R4 / M3 Simply](https://www.dropbox.com/s/juxzri7h8bttunh/DS%20Game%20Forwarder%20pack%20%28Original%20R4%2C%20M3%20Simply%29.7z?dl=0)
   - [Acekard 2(i) / M3DS Real](https://www.dropbox.com/s/5elogf885sd62hu/DS%20Game%20Forwarder%20pack%20%28M3DS%20Real%29.7z?dl=0)
   - [DSTT / R4i Gold / R4i-SDHC / R4 SDHC Upgrade / SC DSONE](https://www.dropbox.com/s/xxfmvikwmnvsu63/DS%20Game%20Forwarder%20pack%20%28DSTT%2C%20R4i%20Gold%2C%20R4i-SDHC%2C%20SC%20DSONE%29.7z?dl=0)
   - [Acekard RPG](https://drive.google.com/file/d/0B2_1xHkEp2_6OHVuZEJwU1BKbEU/view?usp=sharing)
   - [R4iDSN / R4i Gold RTS / R4i Gold 3DS Plus](https://www.dropbox.com/s/j8nquh073k9y0h7/DS%20Game%20Forwarder%20pack%20%28R4iDSN%2C%20R4i%20Gold%20RTS%29.7z?dl=0)
   - [Ace 3DS+ / Gateway Blue Card / R4iLS / R4iTT](https://www.dropbox.com/s/fd7dzhn8burcq02/DS%20Game%20Forwarder%20pack%20%28Ace3DS%2C%20GW%20Blue%20Card%2C%20R4iTT%29.7z?dl=0)
   - [SC DSTWO](https://www.dropbox.com/s/pyyg0vq8b0nmhqd/DS%20Game%20Forwarder%20pack%20%28SC%20DSTWO%29.7z?dl=0)

1. Extrahera innehållet i mappen `for Slot-1 microSD` till roten på ditt minneskorts microSD-kort, och (om mappen finns) innehållet i `for 3DS SD card` mappen till roten på ditt 3DS SD-kort.

När du har packat upp paketet kan du redigera `sd:/_nds/nds-bootstrap.ini` och ändra inställningarna. Detta är inte möjligt för Acekard RPG, R4 DS, och R4i Gold RTS.
- `NTRCLOCK`: Om satt till `0` eller om <kbd class="face">A</kbd> hålls ner, DSi startskärmen kommer att visas i stället för den vanliga DS startskärmen, och TWL klockfrekvens används, så lagg försvinner
- `DISABLEANIMATION`: If set to `1` or <kbd class="face">B</kbd> is held, the DS/DSi boot screen is skipped
- `HEALTHSAFETYMSG`: Om satt till `1`, startskärmens meddelande om hälsa och säkerhet kommer att visas på nedre skärmen, annars förblir skärmen vit utan meddelandet

### Del 2: Få AP:s åtgärdsfiler från TWiLight Menu++
Om du redan har TWiLight Menu++, hoppa till nästa avsnitt.
1. Download the latest [`TWiLightMenu-3DS.7z`](https://github.com/DS-Homebrew/TWiLightMenu/releases/latest/download/TWiLightMenu-3DS.7z)
1. I 7z-filen, gå till `_nds/TWiLightMenu/`
1. Kopiera mappen `apfix` till `sd:/_nds/ntr-forwarder/` på ditt 3DS SD-kort

### Del 3: Forwarder3-DS
1. Öppna `Forwarder3DS.jar`
   - **Windows-användare:** Om den inte öppnas kan du ladda ner [Forwarder3DS.bat](/assets/files/Forwarder3DS.bat), placera den i samma mapp som Forwarder3DS.jar, och köra den
1. Ställ in ditt kort som `Target` till vänster
   - **OBS:** Om du inte ser en lista av kort, ladda ner [denna zip](https://github.com/Olmectron/olmectron.github.io/archive/master.zip), och lägg `forwarders` mappen i samma mapp som Forwarder3DS. ar, sedan byta namn på den till `.forwarders`
1. Aktivera `Automatically set ROM path`
   - **Linux-användare:** Den automatiska sökvägen är felaktig eftersom den innehåller hela sökvägen (e. . `/media/$USER/någonting/`), ta bort den delen
   - **MacOS användare:** Den automatiska sökvägen är felaktig eftersom den innehåller `/Volumes/(kortnamn)/` i början, ta bort den delen
1. Klicka på mappen längst upp till höger och välj de ROM du vill göra forwarders för eller dra och släpp dem i fönstret
   - **OBS:** ROMs måste redan vara på ditt SD-kort när du väljer dem, och kan inte flyttas utan att återskapa forwarderna
   - **SD-kortanvändare:** Om din sparfil finns i samma mapp som ROM:en, flytta den till en mapp som heter `saves`, med `saves` mappen i samma plats som ROM:erna
1. If you're playing a hack/translation of a DSi-Enhanced game that has it's banner/title edited, find the banner for the game from [here](https://www.dropbox.com/sh/igr47pr0q5bh4p5/AAA9Dy8VOGfBLUA6KdLDSDW-a?dl=0), right click on the game in Forwarder3-DS, click `Import banner`, and click on the banner to use
1. Om du använder en homebrew ROM, klicka på den, rensa sedan `Game title` och skriv in spelets titel
1. Klicka på diskettknappen för att generera forwarder CIA(s)
1. Kopiera CIA(erna) till din 3DS SD-kort, sedan installera dem med FBI
   - Om du använder EmuNAND, installera till både SysNAND och EmuNAND
{% endcapture %}
{% assign tab-flashcard = tab-flashcard | split: "////////" %}

{% assign tabs = tab-sd-card | concat: tab-flashcard %}
{% include tabs.html index=0 tabs=tabs %}