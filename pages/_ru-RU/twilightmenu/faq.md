---
lang: ru-RU
layout: faq
section: twilightmenu
category: other
title: FAQ и Устранение неполадок
long_title: TWiLight Menu++ FAQ и устранение неполадок
description: FAQ и устранение неполадок для TWiLight Menu++
---

Больше FAQ вы можете найти в [теме на GBAtemp](https://gbatemp.net/threads/ds-i-3ds-twilight-menu-gui-for-ds-i-games-and-ds-i-menu-replacement.472200/).
{:.alert .alert-info}

#### Почему моя 3DS/2DS зависает с чёрным экраном, вылетает, выключается, и т.д. когда я запускаю TWiLight Menu++?
Возможно TWL_FIRM повреждён. Следуйте этой инструкции чтобы исправить проблему: <https://3ds.hacks.guide/troubleshooting#dsi--ds-functionality-is-broken-after-completing-the-guide>

#### Как мне исправить проблему зависания на белом экране при запуске TWiLight Menu++?
- Для начала, попробуйте ввести консоль в режим сна (т.е. закройте крышку консоли, или нажмите кнопку сна на O2DS), затем выведите из него
- Если это не сработает, отформатируйте вашу SD карту в FAT32 с размером кластера 32 Кб
- Если и это не сработает, попробуйте другую SD карту

#### Где тема Acekard/Wood UI?
Тема acekard (также называемая Wood UI) была удалена из-за ошибок, вызвавших повреждение SD-карты. Ожидайте исправления. Прогресс по возвращению этой темы можно найти в [этом PR](https://github.com/DS-Homebrew/TWiLightMenu/pull/1109).

#### How do I fix TWiLight Menu++ restarting or giving a Guru Meditation Error when launching a game?
Go into TWLMenu++ Settings, and disable `Update recently played list`.

#### Почему приставка зависает на белом экране когда я пытаюсь запустить игру с SD карты?
- Для начала, проверьте [список совместимости nds-bootstrap](https://docs.google.com/spreadsheets/d/1LRTkXOUXraTMjg1eedz_f7b5jiuyMv2x6e_jY_nyHSc/htmlview#gid=0) и убедитесь что ваша игра совместима
- Попробуйте запустить игру с полностью отключёнными читами, т.к. не все читы совместимы с nds-bootstrap на данный момент. Вы можете использовать <kbd class="l">L</kbd> чтобы отключить все читы для игры
- Если игра изначально работала, удалите папки `fatTable` и `patchOffsetCache` в `sd:/_nds/nds-bootstrap/`

#### Как использовать читы?
You need to have a cheat DB in the form of a `usrcheat.dat` file in the `sd:/_nds/TWiLightMenu/extras/` folder. The most updated cheat database is [DeadSkullzJr's](https://gbatemp.net/threads/deadskullzjrs-flashcart-cheat-databases.488711/).
- On the 3DS, this database is available in the Universal-Updater app as "NDS Cheat Databases." This will automatically install it to the required location.

Alternatively, you can use [r4cce](http://hp.vector.co.jp/authors/VA013928/soft_en.html) to create your own cheat DB.

#### How do I show a custom picture on the top screen of the DSi theme?
A random `.png` image in `sd:/_nds/TWiLightMenu/dsimenu/photos/` will be shown each time the menu is loaded.

- The images(s) must be no bigger than 208x156
- If you have errors, it's most likely an error with the image size. Please use [tinypng](https://tinypng.com) to reduce the size

#### How do I get games?
You can download homebrew games from [Universal-DB](https://db.universal-team.net/ds) and [GameBrew](https://www.gamebrew.org/wiki/List_of_all_DS_homebrew#Games). To get dumps of your retail games:
- On DS you can use [GodMode9i](https://github.com/DS-Homebrew/GodMode9i/releases) to dump your GBA games and, if you have a Slot-2 flashcard, DS games
- On DSi you can use [GodMode9i](https://github.com/DS-Homebrew/GodMode9i/releases) to dump your DS games and DSiWare
- On 3DS you can use [GodMode9](https://github.com/d0k3/GodMode9/releases) to dump your DS games, DSiWare, and Virtual Console titles

#### Can I get the save files from my game cards onto my SD card or vice versa?
Yes, you can use [GodMode9i](https://github.com/DS-Homebrew/GodMode9i/releases) on DSi and 3DS or [Checkpoint](https://github.com/FlagBrew/Checkpoint/releases) on 3DS.

#### How do I change TWiLight Menu++'s language?
1. Open TWiLight Menu++ settings, you can do this by holding <kbd>SELECT</kbd> while loading TWiLight Menu++
1. Press <kbd class="l">L</kbd> or <kbd class="face">Y</kbd> once (on flashcard/3DS) or twice (on DSi)
1. Change the first option until you see the language you want, then exit settings
   - You may also want to change the next two options as they control the language of DS games and their titles in TWiLight Menu++

#### Is this a DS(i) emulator?
No, this is not an emulator. The menu and DS games (loaded via nds-bootstrap) are ran natively in the console's DS/DSi mode. The only consoles emulated are the past consoles, but partially for GBA (as some or all parts like graphics are ran natively).

#### What systems does TWiLight Menu++ support?

| Format                  | Loader                                           | Extensions                             | Save file                                      |
| ----------------------- | ------------------------------------------------ | -------------------------------------- | ---------------------------------------------- |
| ARGV[^1]                | Native                                           | `.argv`                                |                                                |
| Atari 2600              | [StellaDS][stellads]                             | `.a26`                                 |                                                |
| Atari 5200              | [A5200DS][a5200ds]                               | `.a52`                                 |                                                |
| Atari 7800              | [A7800DS][a7800ds]                               | `.a78`                                 |                                                |
| Atari XEGS              | [XEGS-DS][xegs-ds]                               | `.xex`, `.atr`                         |                                                |
| DS                      | [nds-bootstrap][ndsbs], flashcard kernel, native | `.nds`, `.dsi`, `.ids`, `.srl`, `.app` | `saves/[rom name].sav`[^2]                     |
| DSiWare                 | [Unlaunch][unlaunch], [nds-bootstrap][ndsbs]     | `.nds`, `.dsi`, `.ids`, `.srl`, `.app` | `saves/[rom name].pub`, `saves/[rom name].prv` |
| DSTWO Plugin            | [DSTWO][dstwo][^3]                               | `.plg`                                 |                                                |
| Game Boy (Color)        | [GameYob][gameyob]                               | `.gb`, `.sgb`, `.gbc`                  | `[rom name].sav`                               |
| Game Boy Advance        | [GBARunner2][gbarunner2][^4], native[^5]         | `.agb`, `.gba`, `.mb`                  | `[rom name].sav`                               |
| Game Gear               | [S8DS][s8ds]                                     | `.gg`                                  | `[rom name].gg.sav`                            |
| Genesis/Mega Drive      | [jEnesisDS][jenesis], [PicoDriveTWL][pdtwl]      | `.gen`                                 | `[rom name].srm`[^6]                           |
| Master System           | [S8DS][s8ds]                                     | `.sms`                                 | `[rom name].sms.sav`                           |
| MPEG4 Video             | [MPEG4 Player][mpeg4player]                      | `.mp4`                                 |                                                |
| NES/Famicom             | [nesDS][nesds]                                   | `.nes`, `.fds`                         | `[rom name].sav`                               |
| PC Engine/TurboGrafx-16 | [NitroGrafx][nitrografx]                         | `.pce`                                 |                                                |
| RVID Video              | [Rocket Video Player][rvidplayer]                | `.rvid`                                |                                                |
| SNES[^7]                | [SNEmulDS][snemulds]                             | `.smc`, `.sfc`                         | `[rom name].srm`[^8]                           |
{:.table}

- Footnotes -
{:footnotes}

#### Why isn't touch input working on sudokuhax?
Depending on the save file of sudokuhax, the touch screen inputs may not work.

#### Can The Biggest Loser boot TWiLight Menu++?
No. As The Biggest Loser is a Slot-1 game, and not a DSiWare game, SD access is disabled when running Slot-1 cards.

[^1]: Text files containing the path to a DS homebrew app and arguments to launch it with, see [nds-hb-menu's README](https://github.com/devkitPro/nds-hb-menu#passing-arguments) for more info
[^2]: Only for retail ROMs, homebrew do not have specific save files
[^3]: Only works from a SuperCard DSTWO flashcard as it has additional processing power and RAM inside the cartridge
[^4]: When running in DSi Mode, it can use the DSP for better sound
[^5]: Requires a Slot-2 flashcard and thus only works on DS Phat and DS Lite
[^6]: jEnesis can only save when running from a flashcard, but PicoDriveTWL can save from SD and flashcard
[^7]: Only shown when using a flashcard, 3DS's internal SD card, or DSi with Unlaunch installed
[^8]: Can only save when running from a flashcard

[a5200ds]: https://github.com/wavemotion-dave/A5200DS
[a7800ds]: https://github.com/wavemotion-dave/A7800DS
[dstwo]: http://eng.supercard.sc
[gameyob]: https://github.com/Drenn1/GameYob
[gbarunner2]: https://github.com/Gericom/GBARunner2
[jenesis]: https://www.gamebrew.org/wiki/JEnesisDS
[mpeg4player]: https://gbatemp.net/threads/544095
[ndsbs]: https://github.com/DS-Homebrew/nds-bootstrap
[nesds]: https://github.com/DS-Homebrew/NesDS
[nitrografx]: https://www.gamebrew.org/wiki/NitroGrafx
[pdtwl]: https://github.com/DS-Homebrew/PicoDriveTWL
[rvidplayer]: https://gbatemp.net/threads/539163
[s8ds]: https://www.gamebrew.org/wiki/S8DS
[snemulds]: https://www.gamebrew.org/wiki/SNEmulDS
[stellads]: https://github.com/wavemotion-dave/StellaDS
[unlaunch]: https://problemkaputt.de/unlaunch.htm
[xegs-ds]: https://github.com/wavemotion-dave/XEGS-DS
