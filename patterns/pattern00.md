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

|Row | Ch1        | Ch2        | Ch3        | Ch4        |
|---:|------------|------------|------------|------------|
| 00 | D-4 01 C18 | --- -- --- | --- -- --- | --- -- --- |
| 07 | --- -- --- | --- -- --- | --- -- --- | --- -- EC4 |
| 08 | --- -- --- | --- -- --- | --- -- --- | A-3 02 C1C |
| 15 | --- -- --- | --- -- --- | --- -- --- | --- -- C20 |
| 16 | --- -- C1A | --- -- --- | --- -- --- | C-4 -- 305 |
| 17 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 18 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 19 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 23 | --- -- --- | --- -- --- | --- -- --- | --- -- C22 |
| 24 | --- -- --- | --- -- --- | --- -- --- | D-4 -- 305 |
| 25 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 32 | --- -- C1C | --- -- --- | --- -- --- | --- -- --- |
| 39 | --- -- --- | --- -- --- | --- -- --- | --- -- EC4 |
| 40 | --- -- --- | --- -- --- | --- -- --- | F-4 02 C20 |
| 47 | --- -- --- | --- -- --- | --- -- --- | --- -- C1E |
| 48 | --- -- C1E | --- -- --- | --- -- --- | E-4 -- 305 |
| 49 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
| 55 | --- -- --- | --- -- --- | --- -- --- | --- -- C20 |
| 56 | --- -- --- | --- -- --- | --- -- --- | D-4 -- 305 |
| 57 | --- -- --- | --- -- --- | --- -- --- | --- -- 300 |
