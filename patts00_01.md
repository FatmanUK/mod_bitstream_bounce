Ok, sample audition complete. Let's write the first two patterns.

---

Patterns `00` and `01` are written as compiler-ready Markdown tables. They retain the MilkyTracker/PikaOS four-channel ProTracker target,  use only PT2-compatible effects and permitted note ranges,  and follow the compiler’s peculiar but binding rule that row numbers are decimal and entirely empty rows are omitted. 

[Download the compiler-ready Patterns 00 and 01](sandbox:/mnt/data/bitstream_bounce_patterns_00_01.md)

## Effects introduced

* `F06`: set speed to six ticks per row.
* `F8A`: set tempo to `8a` hex, or 138 BPM.
* `Cxx`: set channel volume to hexadecimal `xx`. `C00` gives the introduction its hard cut.
* `304`: tone-portamento toward the written note at speed `04`, without retriggering the active sample.

Both patterns assert `F06` and `F8A` on row `0`. Repeating them in Pattern `01` is intentional: when that pattern returns after the buffer-underrun section, it literally resets the clock. Sometimes symbolism and defensive programming manage to occupy the same three bytes.

## Pattern `00`: Carrier Signal

Four exposed bars. `Strings7` holds the D-centred carrier on Ch1 while `Bratz` gives a tentative version of Copper Query on Ch4. Both channels are cut at row `56`, leaving rows `56–63` as an approximately 0.87-second silent handoff into the drums.

| Row | Ch1        | Ch2        | Ch3        | Ch4        |
| --: | ---------- | ---------- | ---------- | ---------- |
|   0 | D-4 01 C18 | --- -- F06 | --- -- F8A | --- -- --- |
|   6 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
|  10 | --- -- --- | --- -- --- | --- -- --- | C-4 02 C20 |
|  14 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C22 |
|  16 | --- -- C1C | --- -- --- | --- -- --- | --- -- --- |
|  18 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1E |
|  22 | --- -- --- | --- -- --- | --- -- --- | C-4 02 C20 |
|  26 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C24 |
|  30 | --- -- --- | --- -- --- | --- -- --- | F-4 02 C20 |
|  32 | --- -- C20 | --- -- --- | --- -- --- | --- -- --- |
|  34 | --- -- --- | --- -- --- | --- -- --- | E-4 02 C22 |
|  38 | --- -- --- | --- -- --- | --- -- --- | C#4 02 C20 |
|  41 | --- -- --- | --- -- --- | --- -- --- | D-4 -- 304 |
|  46 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
|  48 | --- -- C18 | --- -- --- | --- -- --- | --- -- --- |
|  50 | --- -- --- | --- -- --- | --- -- --- | C-4 02 C20 |
|  53 | --- -- --- | --- -- --- | --- -- --- | D-4 02 C24 |
|  56 | --- -- C00 | --- -- --- | --- -- --- | --- -- C00 |

The drone rises from `18` to `20`, then drops back before the cut. The brass phrase similarly grows from tentative entries to a stronger final D. The `C#4 → D-4` portamento is the first hint of the A-dominant turnaround colour without making the introduction sound like it has already reached the chorus.

## Pattern `01`: Hard Synchronisation

Rows `0–7` are drums only. `SlapBass` enters at row `8`, and `MuteClav` enters at row `25`. The bass establishes Packet Bounce, moves through a brief G-coloured variation, then outlines A dominant before Pattern `02` returns to D.

| Row | Ch1        | Ch2        | Ch3        | Ch4        |
| --: | ---------- | ---------- | ---------- | ---------- |
|   0 | C-4 04 --- | --- -- F06 | --- -- F8A | --- -- --- |
|   2 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|   3 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
|   4 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|   6 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|   7 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
|   8 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
|  10 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  11 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- --- |
|  12 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|  14 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
|  15 | --- -- --- | --- -- --- | C-4 06 C0E | --- -- --- |
|  16 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- --- |
|  18 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  19 | C-4 04 --- | B-4 03 --- | --- -- --- | --- -- --- |
|  20 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|  22 | --- -- --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
|  23 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
|  24 | C-4 04 --- | D-4 03 --- | --- -- --- | --- -- --- |
|  25 | --- -- --- | --- -- --- | --- -- --- | F-4 07 --- |
|  26 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  27 | C-4 04 --- | A-4 03 --- | --- -- --- | A-4 07 --- |
|  28 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|  30 | --- -- --- | C-5 03 --- | C-4 06 C14 | --- -- --- |
|  31 | --- -- --- | --- -- --- | C-4 06 C10 | --- -- --- |
|  32 | C-4 04 --- | D-5 03 --- | --- -- --- | --- -- --- |
|  33 | --- -- --- | --- -- --- | --- -- --- | G-4 07 --- |
|  34 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  35 | C-4 04 --- | B-4 03 --- | --- -- --- | --- -- --- |
|  36 | C-4 05 --- | --- -- --- | --- -- --- | B-4 07 --- |
|  38 | --- -- --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
|  39 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
|  40 | C-4 04 --- | G-4 03 --- | --- -- --- | --- -- --- |
|  41 | --- -- --- | --- -- --- | --- -- --- | F-4 07 --- |
|  42 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  43 | C-4 04 --- | B-4 03 --- | --- -- --- | A-4 07 --- |
|  44 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|  45 | --- -- --- | --- -- --- | --- -- --- | E-4 07 --- |
|  46 | --- -- --- | D-5 03 --- | C-4 06 C14 | --- -- --- |
|  47 | --- -- --- | --- -- --- | C-4 06 C10 | G-4 07 --- |
|  48 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- --- |
|  49 | --- -- --- | --- -- --- | --- -- --- | E-4 07 --- |
|  50 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  51 | C-4 04 --- | E-4 03 --- | --- -- --- | G-4 07 --- |
|  52 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|  54 | --- -- --- | G-4 03 --- | C-4 06 C14 | --- -- --- |
|  55 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
|  56 | C-4 04 --- | A-4 03 --- | --- -- --- | --- -- --- |
|  57 | --- -- --- | --- -- --- | --- -- --- | E-4 07 --- |
|  58 | --- -- --- | --- -- --- | C-4 06 C14 | --- -- --- |
|  59 | C-4 04 --- | C#5 03 --- | --- -- --- | G-4 07 --- |
|  60 | C-4 05 --- | --- -- --- | --- -- --- | --- -- --- |
|  61 | --- -- --- | --- -- --- | C-4 06 C10 | --- -- --- |
|  62 | C-4 04 --- | A-4 03 --- | C-4 06 C14 | --- -- --- |
|  63 | C-4 05 C24 | --- -- --- | C-4 06 C18 | --- -- --- |

## Validation status

The file passes structural checks for:

* four cells per emitted row;
* decimal, unique row numbers within `0–63`;
* correct sample slots and assigned note ranges;
* `C-4` notation for every unpitched percussion hit;
* only the intended `F`, `C`, and `3` effect families;
* bass entry at row `8`;
* clav entry at row `25`;
* simultaneous Ch1/Ch4 hard cut at Pattern `00`, row `56`;
* no emitted rows after the cut.

Each pattern lasts approximately **6.9565 seconds** at `F06/F8A`. The tables are syntax-validated but have not yet passed the user’s compiler or MilkyTracker playback. The immediate checkpoint is to compile these two patterns and verify the dual `Fxx` commands, the `304` glide, the row-56 hard cut, and the final three-row drum fill.
