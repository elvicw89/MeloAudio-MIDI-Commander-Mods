# MeloAudio MIDI Commander (TSMIDI2.0) — Mods Hub

Community hub for **experimental modifications** to the MeloAudio MIDI Commander (USB ID `2EEE:0301`, product string `TSMIDI2.0`, STM32F1-class MCU).

> Unofficial, use at your own risk. Not affiliated with MeloAudio.
> **This repo is a showcase only.** No vendor firmware and no patch tools are distributed here.

Research behind these mods (reverse engineering of the original firmware) lives in the private/ongoing project repo; findings relevant to a mod are summarised in each mod's notes.

> ⚠️ **Warning:** this mod works perfectly, but there is **one aesthetic flaw**: the OLED shows a block of noisy pixels in the CC# field. It is cosmetic only; MIDI output is correct. See the photo below.

## Available mods

| Mod | Target | What it does | Status |
|---|---|---|---|
| [JAMP for Ampero II Stomp](docs/release-notes-v0.1.0-jamp-mod.md) (`v0.1.0-jamp-mod`) | built-in **JAMP** profile | Footswitch CC map for the Ampero II Stomp, EXP1/EXP2 = CC11, 5/E = patch up/down CCs | Showcase; hardware-tested by the author (keys, pedals); one cosmetic OLED flaw |

### JAMP → Ampero II Stomp: CC map
| Footswitch | CC | Value | Mode | Ampero II Stomp function |
|---|---|---|---|---|
| 1 / 2 / 3 | CC25 | 1 / 2 / 3 | Momentary | SCENE 1 / 2 / 3 |
| 4 | CC28 | 127/0 | Toggle | n/a |
| A | CC79 | 127/0 | Toggle | FS1 |
| B | CC80 | 127/0 | Toggle | FS2 |
| C | CC81 | 127/0 | Toggle | FS3 |
| D | CC60 | 127/0 | Toggle | TUNER |
| 5 | CC27 | 0 | Momentary | PATCH UP |
| E | CC26 | 0 | Momentary | PATCH DOWN |
| EXP1 / EXP2 | CC11 | pedal | continuous | expression |

Side effects: JAMP loses bank / program-change navigation; the "10x" bank-step menu option becomes stride 1 (labelled "01x"). Other presets are byte-identical to the original. Known flaw: noisy pixel block in the OLED CC# field (cosmetic; MIDI is correct) — see `docs/v0.1.0-jamp-mod-oled-flaw.jpg`.

## Patch tools
Not published yet. Tooling and flashing instructions will be released once the underlying reverse-engineering project is complete. No firmware images are distributed here.

## Verification
The patch was verified by running the original code under an ARM emulator (22 checks) and on hardware against an Ampero II Stomp.

## Contributing
Ideas and mod requests welcome via issues. Tooling will be shared after project completion.
