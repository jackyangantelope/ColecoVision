# Validation, 2026-10-23

| Evidence | Result | Boundary |
|---|---|---|
| Source selection and notices | Passed | No old restricted CPU/PSG bodies, BIOS/ROM, bench hardware definitions or hardcoded local application paths in export |
| Public dependency pins | Verified and built | Official SDK 2.3.0 with its TinyUSB gitlink; PIO USB commit in lock file |
| Independent clean source export | Full rebuild passed | Source export; not yet a Git clone |
| Export build footprint | Flash 547,184 B; static RAM 467,712 B | Does not measure physical heap/stack high water |
| ASan/UBSan game runs | 3 games x 3 input modes x 1,800 frames passed | Original gameplay execution, samples, reload and invalid-length gate |
| CPU/video/timing regression | 162 checkpoints identical | PC, pixel hashes and sample totals vs frozen CPU baseline; no claim of identical PCM |
| PSG-specific tests | Passed | Silence/reset, tone transition rate, noise activity/feedback retention, all latched data-write register classes |
| H RP2350B bench firmware | Scoped physical pass, 2026-10-26 | brinquitos steady 59.921924 FPS over 172.307550 s; user confirmed normal sound. Last 60.091173 s: no dropped/zero samples. Cumulative under9/over413, replaced27 remain recorded. Full controls, other games and extended stability unverified. |
| Public Fruit Jam firmware | Built, physical operation unverified | Different hardware from prior scoped G acceptance |
| Previous G hardware result | Scoped acceptance retained | Does not validate the replacement PSG or Fruit Jam configuration |

No SD card, board flash or serial port was changed during source preparation.
The public Fruit Jam target still needs physical validation.

The user supplied the H board capture on 2026-10-26. No agent board operation
was performed. The physical result covers the new MIT PSG on the RP2350B
bench setup; Fruit Jam remains physically unverified. The capture
SHA256 is `c7369304b0e742500bc0a9451d56c8e352f331858614bf4c376119d290e25325`.
