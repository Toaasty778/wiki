---
lang: hu-HU
layout: wiki
section: ds-index
category: reference
title: Nintendo DSi / Nintendo 3DS TWL_FIRM
description: Információk a Nintendo DSi és a Nintendo 3DS TWL_FIRM-jéről
---

### CFW telepítése
Habár a legtöbb előny az egyedi firmware a Nintendo DSi és Nintendo 3DS számára nyújtja, lehetővé teszi, hogy felold a konzolod lehetőségeit. Az egyedi firmware telepítése elég könnyű és a legtöbb esetben csak egy (micro)SD kártyára van szükséged hozzá. A legjobb útmutatókkal rendelkezünk, kövesd lépésről lépésre.

- [3DS Hacking Guide](https://3ds.hacks.guide)
   - Lightning parancs: `mod 3ds`
   - Kuriisu parancs: `guide 3ds`
- [DSi Hacking Guide](https://dsi.cfw.guide)
   - Lightning parancs: `mod dsi cfw`
   - Kuriisu parancs: `guide dsi`

### CPU sebességek
A Nintendo DS 67 MHz-es processzorral került szállításra 2004-ben. A Nintendo DSi 133 MHz-es processzorral jött ki 2009-ben. A legtöbb játék a Nintendo DS könyvtárból azelőtt készült, mielőtt a Nintendo DSi kijött, így az elérhető processzor sebesség számukra csak 67 MHz volt. Néhány alkalmazás ehhez az órajelhez kötötte magát, és ennek eredményeként nem működik jól magasabb órajel sebességgel. A legtöbb játék azonban jobban teljesít az eredetinél magasabb órajellel.

Az nds-bootstrap rendelkezik a TWL Clock Speed opcióval, de nem próbálja meg igazítani a ROM-ot, hogy működjön magasabb órajellel. Ez az alkalmazáson múlik, és az alkalmazások amik nem működnek magasabb órajellel, NEM jelentik az nds-bootstrap hibáját.

### Nintendo DSi Menu
Az 1.4.0 verzióban az RSA aláírások a a DS cart fehérlistában nem ellenőrzöttek. Létezik egy exploit a Nintendo DSi flashcard whitelist sérülékenységre, ami lehetővé teszi az ARM9 processzor feletti hozzáférés átvételét. Szüksége van az 1.4.0 verzióra (patchelésre került egy jövőbeni verzióban és nem létezett korábbi verziókban) és egy flashcard-ra módosított ROM-mal.

Továbbá találhatü egy ismert hiba a Nintendo DSi Menu-ben arról, hogyan számolja a szabad területet, ami hibát okozhat, ha a menüt nem az eredeti NAND-ról használják, további információért látogasd meg a [hiyaCFW hibaelhárítás oldalt](/hiyacfw/troubleshooting#the-free-space-bug).

### Nintendo DSi Slot-1 hozzáférés & letiltás
A Slot-1 hozzáférés blokkolt, amikor alkalmazásokat indít a System Menu-ből, kivéve ha az említett alkalmazás a Slot-1 launcher maga vagy a System Settings. Ahhoz, hogy egy normálisan indíthatatlan slot-1 cartridge-t indítsunk, szükség van egy System Settings exploitra vagy egy Unlainch telepítésre. Ezek bármelyike nélkül, nem tud indítani indíthatatlan flashcard-ot és nem tud dump-olni ROM-ot az SD kártyára.

A flashcard white list RSA aláírásokkal kerül ellenőrzésre kivéve az 1.4.0 firmware verziót. Ez azt jelenti, hogy az emberek white list-elhetik saját kártyájukat

Az 1.4.0 előtt a white list két szekciót tartalmazott. Az 1.4.0-nál bevezetésre került a harmadik szekció, amivel a blokkolhatók olyan flash kártyák, amik az első kettőn túljutottak. A harmadik szekció 8 különböző szekciót olvas fel a rom-ról és ellenőrzi egy hash-sel, hogy a rom módosításra került-e. Azon az ellenőrzés hiánya miatt túlcsordultathatjuk a kivétel vektort / megszakítás címet elég nagy értékkel. A legjobb az egészben, hogy ez ARM7-en fut (másik nevén a biztonsági processzor) így ez lehetővé teszik az első exploit-ot az ARM7 processzor-ra. Mivel ez az SCFG regiszterek kizárása előtt történik, fejlett homebrew alkalmazást is futtathatunk (mint például a Slot-1 dumper-ek & külső slot-1 dumper-ek)

Sajnos a követelmények elég szűkek. 1.4.0 verziót és módosított ROM-os flashcard-ot igényel. Továbbá, az exploit nem jött ki sosem hivatalosan, mert az Unlaunch-ot még egyszerűbb telepíteni, és kevesebb követelménnyel rendelkezik (csak egy út a homebrew felé) hasonló előnyökkel.

### Nintendo DSi Camera
A Nintendo DSi Camera alkalmazás képes fényképek készítésére JPEG-ben és azok mentésére a System Memory-ba vagy az SD kártyára. A mód, ahogy betöltésre kerül korlátozza az alkalmazást a DSi által készített képekre, a nem megfelelő HMAC tárolás miatt egy egyedi EXIF tag-ban. Bármilyen egyedi kép nem olvasható a DSi-n, függetlenül attól, hogy PC-n készült vagy szerkesztett.

A `pit.bin` fájl alapján kerül a képek betöltésének sorrendje meghatározásra. Azonban a fejléc méret az offset 0x16-nál nem ellenőrzött, így elég nagy fejléc méret túl tud lépni ezeken a határokon, a buffer felülírását eredményezve aláíratlan kódra ugorva. Ez az ahogy a Memory Pit működik.

### Nintendo DSi 2. Bootstage
A Nintendo DSi második bootstage tölti be a launcher "title.tmd"-jét a memóriába. Azonban ez nem végez fájlméret ellenőrzést, ami azt jelenti, hogy az első 80k bájt betöltésre kerül a RAM-ba, miközben a többi az egyedi payload lehet. Ez az alapja az Unlaunch exploit-nak.

### RTCom
Az RTCom a használata a 3DS RTC-jének, hogy lehetővé tegye, hogy az ARM7 és ARM11 CPU kommunikáljon egymással, még a TWL_FIRM-ben is. Ez engedélyezi a 3DS szolgáltatások használatát a DS(i) módban. Ebbe bele tartozik a Circle Pad analóg bevitel, a széles képernyő engedélyezés és a gyro támogatás. Jelenleg az egyetlen publikus ds homebrew ami használja az RTCom-ot bizonyos GBARunner2 buildek, amik rendelkeznek a 3DS gyro funkció támogatásával. Az RTCom engedélyezéséhez használnod kell a [TWPatch](https://gbatemp.net/threads/542694/)-et.
