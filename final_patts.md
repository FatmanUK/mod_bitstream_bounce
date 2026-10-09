Patterns `08` and `09` are complete. I treated the uploaded `00–07` files as authoritative, including their actual row data rather than the increasingly fictional prose left over from earlier sample choices. The current order list uses `08` twice as the climax and `09` once as the final pattern. pattern00

## Pattern `08`: Overclock

This is the reusable climax. It is built to work in both of its order-list positions, whether followed by Pattern `06` or Pattern `04`.

The structure is:

- First sax climb: `D-4 → F-4 → G-4 → A-4`
- Faster MuteClav exchange in the second quarter
- `G-3` Tubes pivot at row `31`
- More forceful second sax climb reaching `B-4`
- `A-3` Tubes accent at row `61`
- A bass pickup at row `62`, resolving naturally to the next pattern’s D

The sax movement uses the established `305` plus `300` continuation method already present in the auditioned Pattern `04`. pattern04

There is no dropout, collapse, fade-and-restart, or drum-only reconstruction. The rhythm section stays active throughout, following the rule now embodied by Pattern `07`. pattern07

## Pattern `09`: Checksum Coda

The ending has three connected stages:

1. A descending sax phrase against an ascending bass counter-line.
2. A short MuteClav exchange that preserves momentum while giving the sax a breath.
3. A final contrary-motion flourish:

```text
Sax:  B-4  A-4  G-4  F-4  E-4  D-4
Bass:      E-5  A-4  D-4  F-4  G-4  A-4  C#5  D-5
```

Row `56` is the definite final strike:

```text
Ch1: C-4 04 C2C   kick
Ch2: D-5 03 ---   bass
Ch3: D-4 01 C18   Strings7
Ch4: D-3 08 C2A   Tubes
```

Rows `57–62` contain no new events, allowing the one-shot samples to decay. Row `63` applies `C00` only to Strings7 so its forward loop cannot hang after the ending. It is a firm cadence with natural decay, not a fade, fake crash, or suspiciously convenient reboot.

## Files

:chatgpt-content-reference{index="3"}[Download Pattern 08: Overclock](sandbox:/mnt/data/pattern08.md)

:chatgpt-content-reference{index="4"}[Download Pattern 09: Checksum Coda](sandbox:/mnt/data/pattern09.md)

:chatgpt-content-reference{index="5"}[Download the combined Patterns 08–09 document](sandbox:/mnt/data/bitstream_bounce_patterns_08_09.md)

bitstream_bounce_patterns_08_09.zip[Download the ZIP package](sandbox:/mnt/data/bitstream_bounce_patterns_08_09.zip)

## Validation

Both tables pass static checks:

- decimal rows only, ordered and unique;
- rows confined to `00–63`;
- exactly four channel fields per emitted row;
- no `Fxx` speed or tempo commands;
- no notes outside the established instrument ranges;
- all unpitched percussion remains `C-4`;
- only established PT2-compatible effects are used;
- no entirely empty rows are emitted;
- Pattern `08` preserves continuous momentum;
- Pattern `09` has no events after the final strike except the necessary Strings7 loop cut.

Pattern `08` contains 59 emitted rows and Pattern `09` contains 52. They are syntax-validated but still require the compiler and MilkyTracker audition, because music has stubbornly resisted becoming a purely clerical exercise.