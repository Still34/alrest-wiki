---
title: "Viewing and Exporting Xenoblade Models"
categories:
  - xenoblade-general
tags:
  - Resources
  - Xenoblade (Series)
  - Models
  - Textures
permalink: /xenoblade-model-viewing
toc: true
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/splash-noesis.png
excerpt: "Viewing and exporting Xenoblade models using Noesis."
---

{: .notice--info}
This page assumes you have already dumped and extracted all of the files from your copy of the supported Xenoblade game(s).

{: .notice--danger}
**This one lookin' at me funny!** Animation for Xenoblade 3 is currently not supported and cannot be re-exported to a different format.

## What You Need

- The latest release of [Noesis]
- The latest release of [Xenoblade-Switch-Model-Importer-Noesis]

## Instructions

[Noesis] is a popular tool used among various game reverse engineering projects for viewing and re-exporting the models and textures to a more accessible format, such as FBX (Filmbox by Autodesk), glTF (Graphics Language Transmission Format), and more. By default, Noesis does not recognize the file formats used by the various Xenoblade engines. However, this can be resolved using a third-party import script to let Noesis know how to properly parse the formats. 

In this case, we will be using Turk645's excellent [Xenoblade-Switch-Model-Importer-Noesis] script to help us with the import.

1. Extract Noesis to its own directory.
2. Navigate to `<noesis_directory>/plugins/python/`.
3. Paste in the `fmt_wismt.py` from the [Xenoblade-Switch-Model-Importer-Noesis] project.
4. Open up Noesis with either `Noesis.exe` or `Noesis64.exe`.
5. Navigate to the desired character model. 
    - The model should have an extension of [WISMT](/files#wismt).
6. Double click on the filename or right-click and click on `Open`.
    - The model should now be properly rendered on the right hand side. If the texture or model appear malformed, the extracted file(s) may be corrupt. This may happen due to bad ARH extraction scripts.
7. To export the model into a wider-known format, go to `File` > `Export`.
8. Select the desired output type and hit `Export`.

[Noesis]: https://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91
[Xenoblade-Switch-Model-Importer-Noesis]: https://github.com/Turk645/Xenoblade-Switch-Model-Importer-Noesis