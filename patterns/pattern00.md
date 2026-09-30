# Bitstream Bounce: Pattern `00`

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
| 00 | D-4 01 C18 | --- -- --- | --- -- --- | --- -- --- |
| 06 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
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

## Intended checks after compilation

1. Confirm `F06` and `F8A` are both honored when placed on the same row in separate channels.
2. Confirm `D-4 -- 304` preserves the active `Bratz` sample and glides from `C#4` rather than retriggering.
3. Confirm both Ch1 and Ch4 become silent exactly at pattern `00`, row `56`.
4. Confirm pattern `01` begins with an abrupt kick at row `0`, bass first appears at row `8`, and clav first appears at row `25`.
5. Confirm the row `61-63` hat/snare fill crosses cleanly into pattern `02` without clipping or an accidental hanging clav note.
