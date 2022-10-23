---
title: "Viewing and Exporting Xenoblade Models (Switch)"
categories:
  - xenoblade-general
tags:
  - Resources
  - Xenoblade (Series)
  - Models
  - Textures
  - Nintendo Switch
permalink: /xenoblade-model-viewing-switch
toc: true
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/splash-noesis.png
excerpt: "Viewing and exporting models from Xenoblade DE/2/3 using Noesis."
published: false
---

{: .notice--info}
This page assumes you have already dumped and extracted all of the files from your copy of the supported Xenoblade game(s).

{: .notice--warning}
This guide is for Xenoblade title(s) released on the Nintendo Switch, which means this guide only applies to Xenoblade Definitive Edition, Xenoblade 2, and Xenoblade 3.

{: .notice--danger}
**This one lookin' at me funny!** Animation for Xenoblade 3 is currently not supported and cannot be re-exported to a different format.

## What You Need

- The latest release of [Noesis]
- The latest release of [Xenoblade-Switch-Model-Importer-Noesis]

## Instructions

[Noesis] is a popular tool used among various game reverse engineering projects for viewing and re-exporting the models and textures to a more accessible format, such as FBX (Filmbox by Autodesk), glTF (Graphics Language Transmission Format), and more. By default, Noesis does not recognize the file formats used by the various Xenoblade engines. However, this can be resolved using a third-party import script to let Noesis know how to properly parse the formats. 

In this case, we will be using Turk645's excellent [Xenoblade-Switch-Model-Importer-Noesis] script to help us with the import.

### Section I - Setting up Noesis

1. Extract Noesis to its own directory.
1. Navigate to `<noesis_directory>/plugins/python/`.
1. Paste in the `fmt_wismt.py` from the [Xenoblade-Switch-Model-Importer-Noesis] project.
1. Open up Noesis with either `Noesis.exe` or `Noesis64.exe`.
1. Go to `Tools` and check `Display Plugin Tools`.
  - The `Tools` menu should now have an additional submenu called `Xenoblade Switch`. This allows you to adjust the import/export behavior of the plugin.

Your Noesis is now ready for importing/exporting Xenoblade models. Each of the option under the `Xenoblade Switch` submenu does the following,
- **Skeleton Override** Overrides the skeleton the model should use for the exported model. 
  - This is required for models from Xenoblade Definitive Edition and Xenoblade 3.
  - Exepected value is the target chr filename without the extension, e.g., `ch21011010`.
  - This value persists across the session; therefore, you may want to clear or modify the value when exporting other models.
- **Try Highest Level of Detail** On by default. 
  - This option attempts to export only the highest LOD as opposed to every available LOD for the model.
  - If you wish to mess with other LODs, feel free to turn this off.
- **Skip Morph Data** Off by default. 
  - Discards shapekey data.

### Section II-1 - Importing/Exporting Models for Xenoblade DE/3

1. Navigate to the desired character model within Noesis.
    - The model should have an extension of [WISMT](/files#wismt).
1. Select `Tool` > `Xenoblade Switch` > `Skeleton Override` and enter the corresponding chr name for the model.
    - For Xenoblade 3, this should be the closest matching chr filename ending with `0`, e.g., `ch01011183` > `ch01011180`. Check your `chr` folder to make sure the corresponding file exists.
    - For Xenoblade DE, this should be the closest matching chr filename ending with `0000`, e.g., `pc010109` -> `pc010000`. Check your `chr` folder to make sure the corresponding file exists.
1. Double click on the filename or right-click and click on `Open`.
    - The model should now be properly rendered on the right hand side. If the texture or model appear malformed, the extracted file(s) may be corrupt. This may happen due to bad ARH extraction scripts.
1. To export the model into a wider-known format, go to `File` > `Export`.
1. Select the desired output type and hit `Export`.

### Section II-2 - Importing/Exporting Models for Xenoblade 2

1. Navigate to the desired character model within Noesis.
    - The model should have an extension of [WISMT](/files#wismt).
1. Double click on the filename or right-click and click on `Open`.
    - The model should now be properly rendered on the right hand side. If the texture or model appear malformed, the extracted file(s) may be corrupt. This may happen due to bad ARH extraction scripts.
1. To export the model into a wider-known format, go to `File` > `Export`.
1. Select the desired output type and hit `Export`.

[Noesis]: https://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91
[Xenoblade-Switch-Model-Importer-Noesis]: https://github.com/Turk645/Xenoblade-Switch-Model-Importer-Noesis