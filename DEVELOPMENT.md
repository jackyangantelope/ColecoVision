# Change record

## 2026-10-23

- Created an independent source candidate without changing the accepted
  development firmware or frozen test packages.
- Retained the chips CPU adapter and HALT batching optimization.
- Replaced the unresolved-license PSG with MIT emu76489, pinned to
  c0fa097060e022db237163d79704025435042997; adapted the Coleco noise polynomial.
- Added a public Fruit Jam target and removed external application-source
  paths. SDK and PIO USB remain explicit external build dependencies.
- Initial full firmware build passed: flash 550,208 bytes, static RAM
  467,828 bytes. These figures predate subsequent PSG initialization fixes.
- Host regression passed nine runs of 1,800 frames with ASan/UBSan,
  including a repeat after PSG initialization/reset fixes.
- PSG-specific sanitizer test passed: reset silence, tone transition rate,
  audible noise output and preservation of the configured feedback mask
  when writing the noise register. This does not establish listening quality.
- Completed public-baseline source/license selection audit and recorded
  retained-source differences. Excluded old implementation bodies even from
  provenance diffs; retained historical author credits separately.
- Locked official Pico SDK 2.3.0 at 98a542c1a62fb549ffb5d66a3e5892b06276b670,
  its TinyUSB gitlink and PIO USB. Public build script verifies dependency
  revisions and rejects tracked modifications.
- Fixed public target UART defaults and enabled Fruit Jam USB VBUS GPIO11.
- A source-only clean export completed a full rebuild: flash 547,184 bytes,
  static RAM 467,712 bytes. Its bundled host test passed all nine 1,800-frame
  runs, plus PSG tests, after fixing non-tone data-register writes.
- All 162 frame checkpoints match the frozen CPU baseline in PC, rendered
  pixels and sample counts. PCM changes are expected and require listening.
- Built separate RP2350B bench H test firmware using exactly the public
  emulator/PSG sources, official pinned SDK, frozen G frontend and board pins.
  G remains a separate rollback artifact. No board write was performed.
- Local Git repository initialized on GitHubRelease. The initial independent
  build check used a source export, not a Git clone.
- Fruit Jam physical acceptance is separate and remains unverified.

## 2026-10-26

- Archived the user-supplied H hardware capture without changing firmware.
- Recorded scoped brinquitos steady performance/audio acceptance: 10,325
  frames / 172.307550 s = 59.921924 FPS; user confirmed normal sound.
- All 87 queue windows satisfy both conservation equations. Final 30 windows
  have no dropped/zero samples; cumulative under9/over413 and replaced27 remain
  explicit. Full input/multigame/extended/Fruit Jam acceptance is not inferred.
- Updated the source validation status for the public-source release.
