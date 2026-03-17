---

https://chatgpt.com/backend-api/estuary/content?id=file_00000000ec40720a87d772e89f95577b&ts=492719&p=fs&cid=1&sig=ffd6e876605e57250072e2ce5592d41f7301fb90dc0e8a868492c67b40ad5844&v=0

---

# Flipper Zero - SubGHz setting_user

Custom SubGHz settings file for Flipper Zero (compatible Momentum, ARF Firmware, Unleashed, RogueMaster).

Optimized for 433.92 MHz key fob capture at maximum range with tight noise filtering.

---

## Installation

Drop `setting_user` into:

```
SD Card/subghz/assets/setting_user
```

Restart the Flipper or reload SubGHz.

---

## Custom presets

### 🟢 Preset 1 - OOK 433 Long Range

OOK/ASK optimized for 433.92 MHz. Narrow bandwidth (58 kHz), max LNA gain, AGC tuned for weak signals. Good all-around for key fob capture.

### 🟢 Preset 2 - OOK 433 Ultra ( Recommended )

Same base as preset 1 but with the CC1101 TEST registers (`0x2C`, `0x2D`, `0x2E`) correctly set for narrow bandwidth operation. Without these the chip analog front-end is not fully calibrated regardless of other settings. This is what gives a real sensitivity gain over any standard preset. Best choice for long range capture and noisy environments like parking lots.

### Vehicle-specific presets ( Not really stable )

Each brand preset is tuned to the actual modulation, data rate and deviation used by that manufacturer:

| Preset | Modulation | Data rate | Notes |
|---|---|---|---|
| BMW - Mini | 2-FSK | 4.8 kBaud | F/G-series, all Mini |
| Mercedes-Benz | 2-FSK | 9.6 kBaud | W212/W213/W205 and newer |
| Honda | OOK | 1.2 kBaud | Civic, CR-V, Jazz EU |
| AUDI - new | OOK | 2.4 kBaud | All VAG platform EU |
| VAG - new | OOK | 2.4 kBaud | VW, Skoda, Seat |
| Land Rover | OOK | 4.8 kBaud | Defender, Discovery, Range Rover |
| Toyota - Lexus | OOK | 4.8 kBaud | Yaris, RAV4, Prius, Lexus IS/NX |
| Subaru | OOK | 1.2 kBaud | Impreza, Forester, Outback EU |
| Mitsubishi | OOK | 2.4 kBaud | ASX, Outlander, Eclipse EU |
| Cadillac | OOK | 4.8 kBaud | Export EU models |
| Chrysler | OOK | 4.8 kBaud | Jeep, Dodge EU models |

All presets include the CC1101 TEST registers and max LNA gain configuration.

---

## Usage

For generic capture on an unknown vehicle, use **preset 2**.

If you are far from the target or in a noisy environment, preset 2 will outperform any brand-specific preset.

---

## Notes

- Tested on Momentum firmware & ARF firmware
- Antenna matters more than any preset.
- These presets are receive-only optimized.

---

## Credits

By LTX
