---
title: "File Types in the Xenoblade Series"
categories:
  - xenoblade-general
tags:
  - Resources
  - Xenoblade (Series)
permalink: /files
header:
  overlay_color: '#000'
  overlay_filter: '0.75'
  overlay_image: /assets/images/splash-filetypes.jpg
excerpt: File types found within the Xenoblade (Series) files.
toc: true
---


{: .notice--info}
This page contains all of the proprietary file types found across all of the Xenoblade series.

## All-purpose

### ARH

Header: `arh1` (`61 72 68 31`)

Description: Proprietary header file. Contains information for the corresponding [ARD](#ard) file. This includes header files of each object and how they are stored in the ARD file.

Compatible parser: [XenoLib]

### ARD

Header: `xbc1\x03` (`78 62 63 31 03`)

Description: Proprietary archive-like file containing information such as its child file. Requires a corresponding [ARH](#arh) file to decompress.

Compatible parser: [XenoLib]

### PCK

Header: `AKPK` (`41 4B 50 4B`)

Description: Proprietary packed audio format by Wwise. This file format is used across numerous games and contains entries for all of the soundbanks `.bnk` and encoded WEMs `.wem` featured in the game.

Compatible parser: [Custom BMS script]

### BDAT

Header: `BDAT` (`42 44 41 54`)

Description: Proprietary data table format. A BDAT may contain multiple tables. Each table begins with the hex byte `BDAT\x040` (`42 44 41 54 04 30`). An entry requires has a unique 4-byte ID and may contain a wide variety of compatible data formats, ranging from floats to strings.

Compatible parser: [XenoLib]

### CRT

Header: `CRT` (`43 52 54`)

Description: Proprietary file for end-credits. Not to be confused to certificate files typically associated with this file extension.

Compatible parser: N/A

### ETH

Header: `69 C9 0B 07 69 20 77 78`

Description: Proprietary file format for Event Theater. Purpose unknown.

Compatible parser: N/A

### PKB

Header: `N/A`

Description: Primary archive format for XC1(Wii). Requires PKH file as key to decompress.

Compatible parser: [Custom BMS script]

### CPK

Header: `43 50 4B 20`

Description: Primary archive for Xenoblade X.

Compatible parser: [Custom BMS script]

### XBC1

Header: `xbc1` (`78 62 63 31`)

Description: An all-purpose compression format that several other Xenoblade formats depend on. In most cases, the underlying compression format is zlib, though this may occasionally differ in rare instances, such as zstandard in some ARD files.

Structure:

| Offset | Size    | Description       |
|--------|---------|-------------------|
| 0x00   | 0x04    | XBC1 magic        |
| 0x04   | 0x04    | Compression type  |
| 0x08   | 0x04    | Uncompressed size |
| 0x0C   | 0x04    | Compressed size   |
| 0x10   | 0x04    | Unknown           |
| 0x14   | 0x1C    | Filename          |
| 0x30   | Dynamic | Compressed data   |

Compatible parser: N/A

## Models/Animations/Textures

### BEH

Header: `HDEV` (`68 64 65 76`)

Description: Proprietary cutscene header file. Contains references to all data (voice lines, actors, objects, effects, engine commands, etc.) used in the cutscene. Every file references "EventBuilder v0.0.27" tool at the end of it. Based on the file contents EventBuilder seems to be pretty advanced cutscene authoring tool similar to Source Filmmaker and Unreal Sequencer.

Compatible parser: N/A

### BEB

Header: N/A

Description: Proprietary cutscene data file. Purpose unknown.

Compatible parser: N/A

### WISMT

Header: N/A (see [XBC1](#xbc1))

Description: Proprietary model format. This file format may contain raw mesh data, textures, and shader code. Typically associated with [WIMDO](#wimdo).

Compatible parser: N/A

### WIMDO

Header: `DM<XX>` (`44 4D XX XX`)

Description: Proprietary model format. This file format may contain mesh, materials, state flags, bones used for mesh weights, etc. A corresponding [WISMT](#wismt) file may not exist, depending on whether a raw mesh data is embedded within the [WIMDO](#wimdo).

Compatible parser: [XenoLib]

### WILAY

Header: `LAHD\x13'` (`4C 41 48 44 13 27`)

Description: Proprietary layout file. Often used in menus and is likely to contain a common image format within.

Compatible parser: [XbTool]

### BRRES

Header: `62 72 65 73`

Description: Primary model container for characters, NPCs, and enemeis in XC1(Wii).

Compatible parser: [BrawlCrate]/[BRRESViewer]

### MCA

Header: `6D 63 61 00`

Description: Contains animations for characters, NPCs, and enemeis in XC1(Wii).

Compatible parser: [BRRESViewer]

### KYP

Header: `4B 59 50 00`

Description: Contains both models and animations for characters, NPCs, and enemeis in XC1(Wii).

Compatible parser: [BRRESViewer]

### CAMDO

Header: `4D 58 4D 44`

Description: Primary model format for Xenoblade X. Related to CASMT.

Compatible parser: [XenoMax]

### CASMT

Header: `N/A`

Description: Primary model format for Xenoblade X. Related to CAMDO.

Compatible parser: [XenoMax]

### ATTRANIM

## Maps

### WISMDA

Header: N/A

Description: Proprietary overworld map file format. Contains information about the map terrain, props, textures, materials, etc.

Compatible parser: N/A

### WISMHD

{: .notice--warning}
**Another vision...** This file format is still being studied.

Header: `DMSM\x80'` (`44 4D 53 4D 80 27`)

Description: Proprietary map-related file format. Contains table maps of related [WISMDA](#wismda) files and other map-related information, such as volumetric cloud information and more.

Compatible parser: N/A

### NVHE

Header: `NVMS` (`4E 56 4D 53`)

Description: Proprietary file format related to maps. Purpose unknown.

Compatible parser: N/A

### IDCM

Header: `IDCM` (`49 44 43 4D`)

Description: Proprietary file format related to maps. Speculated to be collision mesh.

Compatible parser: N/A

### DAP

Header: `44 41 50 31`

Description: Primary file archive for maps in XC1(Wii). Related to LOD.

Compatible parser: [Custom BMS script]

### LOD

Header: `4C 4F 44 49`

Description: Speculated to contain LOD data for maps in XC1(Wii). Related to DAP.

Compatible parser: N/A

### MAP

Header: `62 72 65 73`

Description: Contains base map objects for XC1(Wii). Resides inside DAP archives.
Other related files(albeit unexplored) include ID, LGT, MPF, OCC, and KP. Extracted from DAP.

Compatible parser: [BRRESViewer]

### CASMDA

Header: `57 E0 E0 57`

Description: Archive for Xenoblade X map data. Related files include CANVDA, CANVHE, and CASMHD, although minimal research has been done on them.

Compatible parser: [XenoMax]

### HKX

Header: `57 E0 E0 57`

Description: Collision data for Xenoblade X maps. Little research has been done.

Compatible parser: N/A

## Video/Audio

### WEBM

Header: `1A 45 DF A3`

Description: Open-source WebM audiovisual container file format. In Xenoblade's case, these typically hold pre-rendered cutscenes in a VP9 video stream and may also contain an optional Vorbis audio stream that does not hold any data (as the audio is played separately from Wwise).

Compatible parser: [ffmpeg]

### ADX

Header: `80 00 00 24`

Description: Primary audio format for XC1(Wii) and XCX.

Compatible parser: [vgmstream]

### ACB

Header: `40 55 54 46`

Description: Primary audio archive for XCX. Similar to BNK.

Compatible parser: [vgmstream]

### WEM

### BNK

## Others

### SVD

### WILTP

### KZPS

### SEG

### MI

### NVDA

### LVB

### WIEFXA

### WIPAC

### CHR

### MOT

### AAB

### PAD

### WITEX

### WISHP

### WILGT

### WITX

### DATA

### PTC

### MSBP

### IDMAP

### WIFNT

### WISTY

### OCPAM

### DAT

### ANM

### EVA

[XenoLib]: https://github.com/PredatorCZ/XenoLib
[XbTool]: https://github.com/Thealexbarney/XbTool
[BRRESViewer]: https://gamebanana.com/tools/6293
[BrawlCrate]: https://github.com/soopercool101/BrawlCrate
[XenoMax]: https://github.com/PredatorCZ/XenoMax
[vgmstream]: https://vgmstream.org/
[ffmpeg]: https://ffmpeg.org/