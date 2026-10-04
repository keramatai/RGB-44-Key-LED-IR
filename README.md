# 44-Key RGB LED Controller IR Protocol Database

This repository provides standardized IR signal configuration files (`.ir`) for generic 44-key RGB LED strip controllers operating on the NEC protocol.

Designed for import into universal Android IR apps (such as IRPLUS, Smart IR Remote, or custom IR blaster applications) and hardware devices like Flipper Zero or microcontrollers (ESP32/Arduino).

## Protocol Overview

- **Protocol:** NEC
- **Carrier Frequency:** 38 kHz (Wavelength: 940nm)
- **Code Length:** 32-bit
- **Address Byte:** `00 FF 00 00` (`0x00` address, `0xFF` inverted complement)

## Button Layout & Command Reference

| Button # | Name | Command Hex | Complement Hex | Full Payload |
| :---: | :--- | :---: | :---: | :---: |
| 01 | Brightness Up | `3A` | `C5` | `3A C5 00 00` |
| 02 | Brightness Down | `BA` | `45` | `BA 45 00 00` |
| 03 | Play / Pause | `82` | `7D` | `82 7D 00 00` |
| 04 | Power | `02` | `FD` | `02 FD 00 00` |
| 05 | Red Color 1 | `1A` | `E5` | `1A E5 00 00` |
| 06 | Green Color 1 | `9A` | `65` | `9A 65 00 00` |
| 07 | Blue Color 1 | `A2` | `5D` | `A2 5D 00 00` |
| 08 | White Color 1 | `22` | `DD` | `22 DD 00 00` |
| 09–12 | Color Tier 2 (R, G, B, W) | `2A`, `AA`, `92`, `12` | Inverted | Standard |
| 13–16 | Color Tier 3 (R, G, B, W) | `0A`, `8A`, `B2`, `32` | Inverted | Standard |
| 17–20 | Color Tier 4 (R, G, B, W) | `38`, `B8`, `78`, `F8` | Inverted | Standard |
| 21–24 | Color Tier 5 (R, G, B, W) | `18`, `98`, `58`, `D8` | Inverted | Standard |
| 25–27 | Red, Green, Blue Up | `28`, `A8`, `68` | Inverted | Standard |
| 28 | Quick | `E8` | `17` | `E8 17 00 00` |
| 29–31 | Red, Green, Blue Down | `08`, `88`, `48` | Inverted | Standard |
| 32 | Slow | `C8` | `37` | `C8 37 00 00` |
| 33–35 | DIY 1–3 | `30`, `B0`, `70` | Inverted | Standard |
| 36 | Auto | `F0` | `0F` | `F0 0F 00 00` |
| 37–39 | DIY 4–6 | `10`, `90`, `50` | Inverted | Standard |
| 40 | Flash | `D0` | `2F` | `D0 2F 00 00` |
| 41–42 | Jump 3 / Jump 7 | `20`, `A0` | Inverted | Standard |
| 43–44 | Fade 3 / Fade 7 | `60`, `E0` | Inverted | Standard |

## Setup Instructions

### Android IR Applications
1. Download `remotes/RGB_44_Key_LED.ir` to your mobile device storage.
2. Launch your preferred IR app (e.g., IRPLUS or Smart IR Remote).
3. Select **Import** or **Load Remote File** and select the `.ir` file.

### Flipper Zero
1. Connect your device via USB or mobile app.
2. Copy `RGB_44_Key_LED.ir` into the SD card directory: `/SD Card/infrared/`.
3. Open **Infrared** -> **Saved Remotes** on the device to select and transmit commands.

## License
Distributed under the MIT License. See `LICENSE` for details.