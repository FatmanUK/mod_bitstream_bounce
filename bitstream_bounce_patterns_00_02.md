# Bitstream Bounce: Patterns `00` through `02`

**Pattern-set version:** `0.6.0-draft2`  
**Target:** 4-channel ProTracker MOD  
**Speed:** `06`  
**Tempo:** `8a` hex / 138 BPM  
**Row numbering:** decimal, as required by the project compiler  
**Status:** revised two-pattern introduction pending audition; Pattern `02` is the accepted former Pattern `01`, with row data unchanged

## Numbering migration

The introduction now occupies two stored patterns. Every previously planned pattern from `01` onward moves up by one slot.

| Former slot | Current slot | Role |
|---:|---:|---|
| `00` | `00` and `01` | Carrier Signal, divided into a slower call and answer |
| `01` | `02` | Hard Synchronisation; accepted row data unchanged |
| `02` | `03` | Main Bounce |
| `03` | `04` | Offset Reply |
| `04` | `05` | Sideband Break |
| `05` | `06` | Party Hook |
| `06` | `07` | Buffer Underrun |
| `07` | `08` | Overclock |
| `08` | `09` | Checksum Coda |

The canonical order list therefore becomes:

```text
00 01 02 03 04 03 05 04 06 03 06 07 02 03 04 06 05 08 06 08 04 03 09
```

This is `17` hex order positions, or 23 decimal positions. At speed `06` and tempo `8a`, the projected runtime is exactly 160 seconds.

## Effect glossary

- `F06`: set speed to 6 ticks per row.
- `F8A`: set tempo to 138 BPM.
- `Cxx`: set the current channel volume to hexadecimal `xx`. In Pattern `01`, several `Cxx` commands taper the looped `Strings7` drone rather than cutting it at full level.
- `304`: tone-portamento toward the written `D-4` target at speed `04`, without retriggering the active `Bratz` sample.

## Pattern `00`: Carrier Signal, Call

`Strings7` establishes the D-centred carrier. The lead density is deliberately sparse: two three-note phrases occupy the full pattern, with a substantial breath between them. There is no cut at the end; the looped drone and its channel volume carry into Pattern `01`.

| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 0 | D-4 01 C18 | --- -- F06 | --- -- F8A | --- -- --- |
| 8 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
| 16 | --- -- C1A | --- -- --- | --- -- --- | C-4 02 C20 |
| 24 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C22 |
| 32 | --- -- C1C | --- -- --- | --- -- --- | --- -- --- |
| 40 | --- -- --- | --- -- --- | --- -- --- | F-4 02 C20 |
| 48 | --- -- C1E | --- -- --- | --- -- --- | E-4 02 C1E |
| 56 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C20 |

## Pattern `01`: Carrier Signal, Answer

The lead answers at the same relaxed pace, then approaches D through the established `C#4` leading tone and restrained portamento. The drone fades over the final twelve rows. Both active channels reach `C00` on row `60`, leaving rows `60-63` as exactly one silent beat before the kick at Pattern `02`, row `0`.

| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 0 | --- -- C20 | --- -- --- | --- -- --- | --- -- --- |
| 8 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
| 16 | --- -- C1E | --- -- --- | --- -- --- | C-4 02 C20 |
| 24 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C22 |
| 32 | --- -- C1C | --- -- --- | --- -- --- | --- -- --- |
| 36 | --- -- --- | --- -- --- | --- -- --- | F-4 02 C20 |
| 44 | --- -- --- | --- -- --- | --- -- --- | E-4 02 C22 |
| 48 | --- -- C18 | --- -- --- | --- -- --- | --- -- --- |
| 50 | --- -- --- | --- -- --- | --- -- --- | C#4 02 C20 |
| 52 | --- -- C10 | --- -- --- | --- -- --- | --- -- --- |
| 54 | --- -- --- | --- -- --- | --- -- --- | D-4 -- 304 |
| 56 | --- -- C08 | --- -- --- | --- -- --- | --- -- --- |
| 58 | --- -- C04 | --- -- --- | --- -- --- | --- -- --- |
| 60 | --- -- C00 | --- -- --- | --- -- --- | --- -- C00 |

## Pattern `02`: Hard Synchronisation

This is the accepted former Pattern `01`. Its row data is unchanged. Only its stored pattern number and transition destination have moved. It reasserts the clock on row `0`; rows `0-7` contain drums only, `SlapBass` enters on row `8`, and `MuteClav` enters on row `25`. The final fill now crosses into Pattern `03`.

| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 0 | C-4 04 --- | --- -- F06 | --- -- F8A | --- -- --- |
| 2 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 3 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 4 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 6 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 7 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 8 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 10 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 11 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- --- |
| 12 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 14 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
| 15 | --- -- --- | --- -- --- | C-4 06 C0E | --- -- --- |
| 16 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- --- |
| 18 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 19 | C-4 04 --- | B-4 03 --- | --- -- --- | --- -- --- |
| 20 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 22 | --- -- --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
| 23 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 24 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 25 | --- -- --- | --- -- --- | --- -- --- | F-4 07 --- |
| 26 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 27 | C-4 04 --- | A-4 03 --- | --- -- --- | A-4 07 --- |
| 28 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 30 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
| 31 | --- -- --- | --- -- --- | C-4 06 C10 | --- -- --- |
| 32 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- --- |
| 33 | --- -- --- | --- -- --- | --- -- --- | G-4 07 --- |
| 34 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 35 | C-4 04 --- | B-4 03 --- | --- -- --- | --- -- --- |
| 36 | C-4 05 --- | --- -- --- | --- -- --- | B-4 07 --- |
| 38 | --- -- --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
| 39 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 40 | C-4 04 --- | G-4 03 --- | --- -- --- | --- -- --- |
| 41 | --- -- --- | --- -- --- | --- -- --- | F-4 07 --- |
| 42 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 43 | C-4 04 --- | B-4 03 --- | --- -- --- | A-4 07 --- |
| 44 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 45 | --- -- --- | --- -- --- | --- -- --- | E-4 07 --- |
| 46 | --- -- --- | D-5 03 --- | C-4 06 C14 | --- -- --- |
| 47 | --- -- --- | --- -- --- | C-4 06 C10 | G-4 07 --- |
| 48 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- --- |
| 49 | --- -- --- | --- -- --- | --- -- --- | E-4 07 --- |
| 50 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 51 | C-4 04 --- | E-4 03 --- | --- -- --- | G-4 07 --- |
| 52 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 54 | --- -- --- | G-4 03 --- | C-4 06 C14 | --- -- --- |
| 55 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 56 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- --- |
| 57 | --- -- --- | --- -- --- | --- -- --- | E-4 07 --- |
| 58 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 59 | C-4 04 --- | C#5 03 --- | --- -- --- | G-4 07 --- |
| 60 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 61 | --- -- --- | --- -- --- | C-4 06 C10 | --- -- --- |
| 62 | C-4 04 --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
| 63 | C-4 05 C24 | --- -- --- | C-4 06 C18 | --- -- --- |

## Intended checks after compilation

1. Confirm Pattern `00` flows into Pattern `01` without retriggering or interrupting the looped `Strings7` drone.
2. Confirm the lead feels roughly half as dense as the earlier one-pattern introduction and that the phrase breaks read as deliberate breaths.
3. Confirm the Pattern `01` drone fade is smooth across `C18`, `C10`, `C08`, `C04`, and `C00`.
4. Confirm rows `60-63` of Pattern `01` are silent and amount to exactly one beat before Pattern `02`, row `0`.
5. Confirm `D-4 -- 304` preserves the active `Bratz` sample and glides from `C#4` rather than retriggering.
6. Confirm Pattern `02` is musically and structurally identical to the accepted former Pattern `01`: kick at row `0`, bass at row `8`, clav at row `25`, and the same closing fill.
7. Confirm the Pattern `02` row `61-63` fill crosses cleanly into the future Pattern `03`.
