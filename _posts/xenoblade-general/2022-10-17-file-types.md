---
title: "File Types in the Xenoblade Series"
categories:
  - xenoblade-general
tags:
  - Resources
---


{: .notice--info}
This page contains all of the proprietary file types found across all of the Xenoblade series.

## ARH

Header: `arh1` (`61 72 68 31`)

Description: Proprietary header file. Contains information for the corresponding [ARD](#ard) file. This includes header files of each object and how they are stored in the ARD file.

Compatible parser: [XenoLib]

## ARD

Header: `xbc1\x03` (`78 62 63 31 03`)

Description: Proprietary archive-like file containing information such as its child file. Requires a corresponding [ARH](#arh) file to decompress.

Compatible parser: [XenoLib]

## PCK

Header: `AKPK` (`41 4B 50 4B`)

Description: Proprietary packed audio format by Wwise. This file format is used across numerous games and contains entries for all of the soundbanks `.bnk` and encoded WEMs `.wem` featured in the game.

Compatible parser: [Custom BMS script]

## BDAT

Header: `BDAT` (`42 44 41 54`)

Description: Proprietary data table format. A BDAT may contain multiple tables. Each table begins with the hex byte `BDAT\x040` (`42 44 41 54 04 30`). An entry requires has a unique 4-byte ID and may contain a wide variety of compatible data formats, ranging from floats to strings.

Compatible parser: [XenoLib]

## ATTRANIM

## SVD

## WILTP

## KZPS

## SEG

## MI

## WILAY

Header: `LAHD\x13'` (`4C 41 48 44 13 27`)

Description: Proprietary layout file. Often used in menus and is likely to contain a common image format within.

Compatible parser: [XbTool]

## CRT

Header: `CRT` (`43 52 54`)

Description: Proprietary file for end-credits. Not to be confused to certificate files typically associated with this file extension.

Compatible parser: N/A

## WISMHD

## WISMDA

Header: `xbc1\01` (`78 62 63 31 01`)

Description: Proprietary overworld map file. Contains information about the map terrain, props, textures, materials, etc.

Compatible parser: N/A

## NVHE

Header: `NVMS` (`4E 56 4D 53`)

Description: Proprietary file format related to maps. Purpose unknown.

Compatible parser: N/A
## NVDA

## IDCM

Header: `IDCM` (`49 44 43 4D`)

Description: Proprietary file format related to maps. Speculated to be collision mesh.

Compatible parser: N/A

## LVB

## ETH

Header: `69 C9 0B 07 69 20 77 78`

Description: Proprietary file format for Event Theater. Purpose unknown.

Compatible parser: N/A

## BEH

Header: `HDEV` (`68 64 65 76`)

Description: Proprietary cutscene header file. Contains references to all data (voice lines, actors, objects, effects, engine commands, etc.) used in the cutscene. Every file references "EventBuilder v0.0.27" tool at the end of it. Based on the file contents EventBuilder seems to be pretty advanced cutscene authoring tool similar to Source Filmmaker and Unreal Sequencer.

Compatible parser: N/A

## BEB

Header: N/A

Description: Proprietary cutscene data file. Purpose unknown.

Compatible parser: N/A

## WIEFXA

## WIPAC

## WISMT

## WIMDO

## CHR

## MOT

## AAB

## PAD

## WITEX

## WISHP

## WILGT

## WITX

## DATA

## PTC

## MSBP

## IDMAP

## WIFNT

## WISTY

## OCPAM

## DAT

## ANM

## EVA

## WEBM

[XenoLib]: https://github.com/PredatorCZ/XenoLib
[XbTool]: https://github.com/Thealexbarney/XbTool
