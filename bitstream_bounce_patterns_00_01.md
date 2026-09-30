# Bitstream Bounce: Patterns `00` and `01`

**Pattern-set version:** `0.5.0-draft1`  
**Target:** 4-channel ProTracker MOD  
**Speed:** `06`  
**Tempo:** `8a` hex / 138 BPM  
**Row numbering:** decimal, as required by the project compiler  
**Status:** syntax-validated; compiler and MilkyTracker audition pending

## Effect glossary

- `F06`: set speed to 6 ticks per row.
- `F8A`: set tempo to 138 BPM. Patterns `00` and `01` both assert the clock so pattern `01` also behaves as a literal reboot later in the order list.
- `Cxx`: set the current channel volume to hexadecimal `xx`. `C00` performs the hard cut at the end of pattern `00`.
- `304`: tone-portamento toward the written `D-4` target at speed `04`, without retriggering the current `Bratz` sample.

## Pattern `00`: Carrier Signal

Four exposed bars. `Strings7` holds the D-centered carrier on Ch1 while `Bratz` asks a tentative version of Copper Query on Ch4. Rows `56-63` are intentionally silent after the hard cut.

| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 0 | D-4 01 C18 | --- -- F06 | --- -- F8A | --- -- --- |
| 6 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
| 10 | --- -- --- | --- -- --- | --- -- --- | C-4 02 C20 |
| 14 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C22 |
| 16 | --- -- C1C | --- -- --- | --- -- --- | --- -- --- |
| 18 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1E |
| 22 | --- -- --- | --- -- --- | --- -- --- | C-4 02 C20 |
| 26 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C24 |
| 30 | --- -- --- | --- -- --- | --- -- --- | F-4 02 C20 |
| 32 | --- -- C20 | --- -- --- | --- -- --- | --- -- --- |
| 34 | --- -- --- | --- -- --- | --- -- --- | E-4 02 C22 |
| 38 | --- -- --- | --- -- --- | --- -- --- | C#4 02 C20 |
| 41 | --- -- --- | --- -- --- | --- -- --- | D-4 -- 304 |
| 46 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
| 48 | --- -- C18 | --- -- --- | --- -- --- | --- -- --- |
| 50 | --- -- --- | --- -- --- | --- -- --- | C-4 02 C20 |
| 53 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C24 |
| 56 | --- -- C00 | --- -- --- | --- -- --- | --- -- C00 |

## Pattern `01`: Hard Synchronisation

The clock is asserted again on row `0`. Rows `0-7` contain drums only, `SlapBass` enters on row `8`, and `MuteClav` enters on row `25`. The last three rows form a compact fill into pattern `02`.

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

1. Confirm `F06` and `F8A` are both honored when placed on the same row in separate channels.
2. Confirm `D-4 -- 304` preserves the active `Bratz` sample and glides from `C#4` rather than retriggering.
3. Confirm both Ch1 and Ch4 become silent exactly at pattern `00`, row `56`.
4. Confirm pattern `01` begins with an abrupt kick at row `0`, bass first appears at row `8`, and clav first appears at row `25`.
5. Confirm the row `61-63` hat/snare fill crosses cleanly into pattern `02` without clipping or an accidental hanging clav note.
