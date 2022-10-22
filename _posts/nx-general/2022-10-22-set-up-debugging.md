---
title: "Setting up Nintendo Switch for Remote Debugging (IDA Pro)"
categories:
  - nx-general
tags:
  - Resources
  - Nintendo Switch
  - Debugging
  - Reverse engineering
permalink: /nx-debug-setup-ida-pro
toc: true
---

{: .notice--warning}
**Think you can take me!?** This guide assumes the reader has decent knowledge of reverse engineering and low-level debugging and requires the use of a modded Nintendo Switch.


## What You Need

- The latest version of IDA Pro
- The latest version of Atmosphere

## Instructions

### Section I - Enable Switch GDB Stub via Atmosphere

1. Navigate to `atmosphere/config/` under the console's SD card. If the directory does not exist, create one if necessary.
2. Create or modify the file `system_settings.ini` and insert the following,

```ini
[atmosphere]
enable_htc = u8!0x0
enable_standalone_gdbstub = u8!0x1
```

3. Reboot the system.

### Section II - Connecting to the Switch via IDA's Debugger

{: .notice--info}
If you plan on using the debugging feature more in the future, consider registering a static IP for your console via your DHCP server.

1. Connect the Nintendo Switch under the same network as your computer.
1. Make note of the console's IP address via `System Settings` -> `Internet` -> `IP address`.
1. Launch the game you wish to debug.
1. Open up IDA Pro (64-bit).
1. Select `Debugger` -> `Attach` -> `Remote GDB Debugger`
1. Enter your console's IP address in the `Hostname` field with the port `22225`.
1. Open `Debug Settings`
1. (Optional) Check all relevant boxes under the Logging section for more information during the debugging session.
1. (Optional) Check `Suspend on debugging start` so that the game freezes when the debugger has successfully attached.
1. Select `Set Specific Options`
1. Change the dropdown menu option `Configuration` from the default to `ARM64 (AArch64)` (if appliciable).
1. Press `OK` all the way through.
1. A new menu should now appear, asking you which system process on the Switch to debug. Scroll down and select `Application`; this will be the game the Switch is currently running.
1. Press `OK`.
1. IDA should now be attached to the remote process.