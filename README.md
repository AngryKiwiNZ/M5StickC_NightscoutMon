# M5StickC Plus Nightscout Bedside Monitor

A compact Nightscout display for the **M5StickC Plus v1.1**. This fork is
configured as a passive bedside display: it shows glucose and time clearly
without duplicating the phone's missing-data alerts.

**Project status — 27 August 2026:** fully operational; no further changes are
planned.

## Display behaviour

- Alternates between the CGM screen and a large clock every 3 seconds.
- **Day mode:** 08:00–21:00 New Zealand local time; normal display colours and
  maximum brightness.
- **Night mode:** 21:00–08:00; dim red on black.
- New Zealand daylight saving is applied automatically.
- The blue Wi-Fi update animation is hidden; Nightscout updates continue in
  the background.

## Alerts and data availability

Missing, stale, unreachable, or temporarily unavailable CGM data remains
visible on the LCD as `NO DATA` or `STALE`. It does **not** use the buzzer or
flash the red LED. Existing low/high glucose alarm behaviour remains separate.

## Hardware and Arduino setup

- Device: M5StickC Plus v1.1
- Arduino IDE: 2.3.10 tested
- M5Stack board package: 2.1.4 tested
- Install the **M5StickC Plus** library, then compile with
  `#include <M5StickCPlus.h>` enabled in `M5StickC_NightscoutMon.ino`.

The main button cycles the three brightness levels. A manual choice remains in
effect until the next day/night transition.

## Private configuration

Never commit Nightscout credentials or Wi-Fi passwords. Copy
`M5StickC_NSconfig.local.h.example` to `M5StickC_NSconfig.local.h`, then enter
your Nightscout URL/token and Wi-Fi networks in that local file. It is ignored
by Git.

## License

This project is licensed under GPL-3.0-or-later. See [LICENSE](LICENSE).
