# Bitstream Bounce: Patterns `06` and `07`

**Target:** 4-channel ProTracker MOD  
**Row numbering:** decimal  
**Clock effects:** omitted; speed and tempo are inserted programmatically  
**Instrument `08`:** `ST-01/Stabs`, accepted replacement  

## Transition assumptions

- Pattern `06` is the reusable Party Hook and must terminate cleanly into several different successors.
- Pattern `07` is unique and is written to transition directly into Pattern `02`, the established Hard Synchronisation/reboot pattern.
- No order-list or structural-arc document is changed here; the user is maintaining those separately.

## Pattern `06`: Party Hook

The full groove supports the principal sax refrain. The lead states the complete Copper Query in the first half, gives a short MuteClav answer, then climbs through the Overclock Ladder contour in the second half. `EC4` creates brief articulated gaps before each fresh sax attack and before the closing stab. The final `D-4` hit uses instrument `08` (`ST-01/Stabs`) as a recurring refrain marker.

| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 00 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 02 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 03 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- EC4 |
| 04 | C-4 05 --- | --- -- --- | --- -- --- | A-3 02 C20 |
| 06 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
| 07 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 08 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- --- |
| 10 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 11 | C-4 04 --- | B-4 03 --- | --- -- --- | --- -- C22 |
| 12 | C-4 05 --- | --- -- --- | --- -- --- | C-4 -- 305 |
| 13 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 14 | --- -- --- | A-4 03 --- | C-4 06 C14 | --- -- 300 |
| 15 | C-4 04 --- | --- -- --- | C-4 06 C0E | --- -- 300 |
| 16 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 18 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 19 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- C24 |
| 20 | C-4 05 --- | --- -- --- | --- -- --- | D-4 -- 305 |
| 21 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 22 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
| 23 | C-4 04 --- | --- -- --- | --- -- --- | --- -- C22 |
| 24 | C-4 04 --- | D-5 03 --- | --- -- --- | F-4 -- 305 |
| 25 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 26 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- 300 |
| 27 | C-4 04 --- | F-5 03 --- | --- -- --- | --- -- 300 |
| 28 | C-4 05 --- | --- -- --- | --- -- --- | E-4 -- 305 |
| 29 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 30 | --- -- --- | A-4 03 --- | C-4 06 C14 | --- -- EC4 |
| 31 | C-4 04 --- | --- -- --- | C-4 06 C0E | C-5 07 C1C |
| 32 | C-4 04 --- | G-4 03 --- | --- -- --- | --- -- --- |
| 34 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 35 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- EC4 |
| 36 | C-4 05 --- | --- -- --- | --- -- --- | D-4 02 C20 |
| 38 | --- -- --- | F-5 03 --- | C-4 06 C14 | --- -- --- |
| 39 | C-4 04 --- | --- -- --- | --- -- --- | --- -- C22 |
| 40 | C-4 04 --- | G-5 03 --- | --- -- --- | F-4 -- 305 |
| 41 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 42 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- 300 |
| 43 | C-4 04 --- | E-5 03 --- | --- -- --- | --- -- 300 |
| 44 | C-4 05 --- | --- -- --- | --- -- --- | G-4 -- 305 |
| 45 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 46 | --- -- --- | D-5 03 --- | C-4 06 C14 | --- -- --- |
| 47 | C-4 04 --- | --- -- --- | C-4 06 C0E | --- -- C24 |
| 48 | C-4 04 --- | A-4 03 --- | --- -- --- | A-4 -- 305 |
| 49 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 50 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 51 | C-4 04 --- | E-5 03 --- | --- -- --- | --- -- C24 |
| 52 | C-4 05 --- | --- -- --- | --- -- --- | B-4 -- 305 |
| 53 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 54 | --- -- --- | G-5 03 --- | C-4 06 C14 | --- -- --- |
| 55 | C-4 04 --- | --- -- --- | --- -- --- | --- -- C22 |
| 56 | C-4 04 --- | A-5 03 --- | --- -- --- | A-4 -- 305 |
| 57 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 58 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 59 | C-4 04 --- | C#5 03 --- | --- -- --- | --- -- EC4 |
| 60 | C-4 05 C24 | --- -- --- | --- -- --- | --- -- --- |
| 61 | --- -- --- | --- -- --- | C-4 06 C0E | D-4 08 C24 |
| 62 | C-4 04 --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
| 63 | C-4 05 C28 | --- -- --- | C-4 06 C18 | --- -- --- |


## Pattern `07`: Buffer Underrun

The groove begins recognisably, then loses expected events in stages. A sax glide is cut before it settles; the second fragment lands on the chromatic `D#4`; bass packets introduce `D#5` and `G#4`; and a forceful `G#4` Stabs hit marks the failure. Hats and bass then fall away, leaving a short near-silence before a compressed drum-only restart fill throws the order list into Pattern `02`.

| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 00 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 02 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 03 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- EC4 |
| 04 | C-4 05 --- | --- -- --- | --- -- --- | A-3 02 C1C |
| 06 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
| 08 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- --- |
| 10 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 11 | C-4 04 --- | --- -- --- | --- -- --- | --- -- C20 |
| 12 | C-4 05 --- | --- -- --- | --- -- --- | C-4 -- 305 |
| 13 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 14 | --- -- --- | A-4 03 --- | C-4 06 C0E | --- -- 300 |
| 15 | --- -- --- | --- -- --- | --- -- --- | --- -- C00 |
| 16 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 18 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
| 19 | --- -- --- | A-4 03 --- | --- -- --- | --- -- EC4 |
| 20 | C-4 05 --- | --- -- --- | --- -- --- | D#4 02 C20 |
| 22 | --- -- --- | D#5 03 --- | C-4 06 C10 | --- -- --- |
| 23 | C-4 04 --- | --- -- --- | --- -- --- | --- -- C1E |
| 24 | --- -- --- | D-5 03 --- | --- -- --- | D-4 -- 305 |
| 25 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 27 | --- -- --- | G#4 03 --- | --- -- --- | --- -- C00 |
| 28 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 31 | --- -- --- | --- -- --- | --- -- --- | G#4 08 C28 |
| 32 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
| 34 | --- -- --- | --- -- --- | C-4 06 C0E | --- -- --- |
| 35 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 36 | C-4 05 --- | A-4 03 --- | --- -- --- | --- -- --- |
| 39 | --- -- --- | --- -- --- | --- -- --- | --- -- C00 |
| 40 | C-4 04 C18 | --- -- --- | --- -- --- | --- -- --- |
| 43 | --- -- --- | D-4 03 --- | --- -- --- | --- -- --- |
| 46 | --- -- --- | --- -- --- | C-4 06 C08 | --- -- --- |
| 52 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 54 | --- -- --- | --- -- --- | C-4 06 C10 | --- -- --- |
| 55 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 56 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
| 57 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 58 | --- -- --- | --- -- --- | C-4 06 C12 | --- -- --- |
| 59 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
| 60 | C-4 05 C24 | --- -- --- | --- -- --- | --- -- --- |
| 61 | C-4 04 C20 | --- -- --- | C-4 06 C0E | --- -- --- |
| 62 | C-4 04 C24 | --- -- --- | C-4 06 C14 | --- -- --- |
| 63 | C-4 05 C28 | --- -- --- | C-4 06 C18 | --- -- --- |


## Audition checkpoints

1. Pattern `06`: confirm the first sax phrase reads as one connected statement rather than five separate notes.
2. Pattern `06`: confirm the row-31 MuteClav answer is audible but does not interrupt the refrain.
3. Pattern `06`: confirm the row-61 `D-4` Stabs hit remains consequential without masking the closing fill.
4. Pattern `07`: confirm the interrupted first glide sounds intentionally dropped rather than malformed.
5. Pattern `07`: confirm the chromatic `D#`/`G#` material signals failure without sounding like a key change.
6. Pattern `07`: confirm rows `47-51` register as a short loss of signal.
7. Pattern `07`: confirm the rows `52-63` drum fill crosses cleanly into Pattern `02`, row `00`.
