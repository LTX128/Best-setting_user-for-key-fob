# Flipper Zero - SubGHz setting_user

Custom SubGHz settings file for Flipper Zero (compatible Momentum, Unleashed, RogueMaster).

Optimized for 433.92 MHz and 434.42 MHz key fob capture at maximum range with tight noise filtering.

---

## Installation

Drop `setting_user.txt` into:

```
SD Card/subghz/assets/setting_user.txt
```

Restart the Flipper.

---

## Custom presets

### Preset 1 - OOK 433 Long Range

OOK/ASK optimized for 433.92 MHz. Narrow bandwidth (58 kHz), max LNA gain, AGC tuned for weak signals. Good all-around for key fob capture.

### Preset 2 - OOK 433 Ultra (recommended for unknown vehicles)

Same base as preset 1 but with the CC1101 TEST registers (`0x2C`, `0x2D`, `0x2E`) correctly set for narrow bandwidth operation. Without these the chip analog front-end is not fully calibrated regardless of other settings. This is what gives a real sensitivity gain over any standard preset. Best choice for long range capture and noisy environments like parking lots.

### VAG 434 - VW / Audi / Skoda / Seat (recommended for VAG)

Dedicated preset for VAG platform keys operating at **434.42 MHz** (pre-2009 Golf, Polo, Passat, Tiguan, Skoda, Seat).

Built around the same architecture as preset 2 with additional tuning specific to VAG RF characteristics:

- Bandwidth locked at 58 kHz — blocks all wide-band parking noise
- Data rate calibrated at exactly 2.4 kBaud to match VAG transmitters
- OOK deviation set to zero, no spectral widening
- AGC averaging on 64 samples with 8 dB hysteresis — the chip waits to be certain before switching between 0 and 1, short noise bursts have no effect
- LNA at absolute maximum gain
- CC1101 TEST registers active, analog front-end fully calibrated for narrow bandwidth
- Continuous RX, no gaps between frames

Use this preset with frequency **434.420 MHz** in Read Raw.

### Vehicle-specific presets

| Preset | Modulation | Data rate | Notes |
|---|---|---|---|
| BMW - Mini | 2-FSK | 4.8 kBaud | F/G-series, all Mini |
| Mercedes-Benz - new | 2-FSK | 9.6 kBaud | W212/W213/W205 and newer |
| Honda - new | OOK | 1.2 kBaud | Civic, CR-V, Jazz EU |
| AUDI - new | OOK | 2.4 kBaud | Audi EU platform |
| VAG 434 | OOK | 2.4 kBaud | VW/Skoda/Seat at 434.42 MHz |
| Land Rover | OOK | 4.8 kBaud | Defender, Discovery, Range Rover |
| Toyota - Lexus | OOK | 4.8 kBaud | Yaris, RAV4, Prius, Lexus IS/NX |
| Subaru | OOK | 1.2 kBaud | Impreza, Forester, Outback EU |
| Mitsubishi | OOK | 2.4 kBaud | ASX, Outlander, Eclipse EU |
| Cadillac | OOK | 4.8 kBaud | Export EU models |
| Chrysler | OOK | 4.8 kBaud | Jeep, Dodge EU models |

---

## Usage

For a generic or unknown vehicle at 433.92 MHz, use **preset 2**.

For VAG platform vehicles (VW, Audi, Skoda, Seat pre-2009), use **VAG 434** with frequency set to 434.420 MHz in Read Raw.

For a known brand, select the matching preset before capturing.

If you are far from the target or in a noisy environment (parking lots, shopping centers), preset 2 and VAG 434 will outperform any generic preset.

---

## Notes

- Tested on Momentum firmware
- Antenna matters more than any preset. A 17.3 cm quarter-wave whip roughly doubles usable range
- These presets are receive-only optimized, PA table is set accordingly

---

## Credits

By LTX

# Flipper Zero - SubGHz setting_user

Custom SubGHz settings file for Flipper Zero (compatible Momentum, Unleashed, RogueMaster).

Optimized for 433.92 MHz and 434.42 MHz key fob capture at maximum range with tight noise filtering.

---

## Installation

Drop `setting_user.txt` into:

```
SD Card/subghz/assets/setting_user.txt
```

Restart the Flipper or reload SubGHz.

---

## Custom presets

### 🟠 Preset 1 - OOK 433 Long Range

OOK/ASK optimized for 433.92 MHz. Narrow bandwidth (58 kHz), max LNA gain, AGC tuned for weak signals. Good all-around for key fob capture.

### 🟢 Preset 2 - OOK 433 Ultra (recommended for unknown vehicles)

Same base as preset 1 but with the CC1101 TEST registers (`0x2C`, `0x2D`, `0x2E`) correctly set for narrow bandwidth operation. Without these the chip analog front-end is not fully calibrated regardless of other settings. This is what gives a real sensitivity gain over any standard preset. Best choice for long range capture and noisy environments like parking lots.

### 🟢 VAG 434 - VW / Audi / Skoda / Seat (recommended for VAG)

Dedicated preset for VAG platform keys operating at **434.42 MHz**

Built around the same architecture as preset 2 with additional tuning specific to VAG RF characteristics:

- Bandwidth locked at 58 kHz — blocks all wide-band parking noise
- Data rate calibrated at exactly 2.4 kBaud to match VAG transmitters
- LNA at absolute maximum gain
- Continuous RX, no gaps between frames

Use this preset with frequency **434.420 MHz**

### Vehicle-specific presets

| Preset | Modulation | Data rate | Notes |
|---|---|---|---|
| VAG 434 | OOK | 2.4 kBaud | VW/Skoda/Seat at 434.42 MHz |
| BMW - Mini | 2-FSK | 4.8 kBaud | F/G-series, all Mini |
| Mercedes-Benz - new | 2-FSK | 9.6 kBaud | W212/W213/W205 and newer |
| Honda - new | OOK | 1.2 kBaud | Civic, CR-V, Jazz EU |
| AUDI - new | OOK | 2.4 kBaud | Audi EU platform |
| Land Rover | OOK | 4.8 kBaud | Defender, Discovery, Range Rover |
| Toyota - Lexus | OOK | 4.8 kBaud | Yaris, RAV4, Prius, Lexus IS/NX |
| Subaru | OOK | 1.2 kBaud | Impreza, Forester, Outback EU |
| Mitsubishi | OOK | 2.4 kBaud | ASX, Outlander, Eclipse EU |
| Cadillac | OOK | 4.8 kBaud | Export EU models |
| Chrysler | OOK | 4.8 kBaud | Jeep, Dodge EU models |

---

## Usage

For a generic or unknown vehicle at 433.92 MHz, use **preset 2**.

For VAG platform vehicles (VW, Audi, Skoda, Seat pre-2009), use **VAG 434** with frequency set to 434.420 MHz.

If you are far from the target or in a noisy environment (parking lots, shopping centers), preset 2 and VAG 434 will outperform any generic preset.

---

## Notes

- Tested on Momentum firmware
- Antenna matters more than any preset. A 17.3 cm quarter-wave whip roughly doubles usable range
- These presets are receive-only optimized, PA table is set accordingly

---

## Credits

BY LTX

---

<p align="center">
  <img src="flipper.png" alt="Flipper Zero" width="700">
</p>

---
