# Bitstream Bounce: **Initial** Project Bootstrap File

**Project:** Bitstream Bounce  
**Status:** We Got As Far As The Title  
**Tracker:** MilkyTracker  
**Platform:** Linux / PikaOS  
**Target format:** 4-channel ProTracker MOD  

---

## Source-of-Truth Hierarchy

Use this hierarchy whenever records disagree:

1. **The auditioned project files are authoritative** for:
   - exact sample loop points
   - exact sample volumes
   - exact per-row volume edits
   - exact finetune values
   - any last by-ear edits
2. **The bootstrap file is authoritative** for:
   - project architecture
   - pattern roles
   - order list
   - note/rhythm/effect structure
   - final sample identities
   - tested status
3. The sample archives (currently ST-01 and ST-02) are only the source of the sample files.

---

## Primary Goal

Compose an original, classic, highly-polished 1990s-Amiga-game-style tune (`.mod`) using authentic **ProTracker 2** (PT2) constraints, ST-01/ST-02 samples, four channels and compact pattern reuse. Do not loop the composition; there should be a definite coda. The coda should not be a simple fade out but an interesting flourish instead.

The intended character of the piece is:

* wild, bouncy, party jazz tune to make NPCs dance
* start with a Strings7 drone under a saxophone
* play for a few bars then cut the sax and drone for the main drum beat
* continue from there
* heavy on the pattern reuse
* interesting pattern order list
* inspirations: Tim Wright/David Whittaker
* unmistakably early-1990s tracker in construction
* 4 channels
* 64 rows per pattern

The `.mod` should be 120-180 seconds long, but exact final runtime is not important. Musical flow, authenticity, and ProTracker compatibility matter more.

Since we're insisting on PT2 compatibility, there are to be no XM-only features.

---

## First Steps

We already have a title: Bitstream Bounce. A title isn't strictly necessary, but having one helps keep the musical direction consistent. It gives the piece a little identity before pattern00 is even composed.

Assign an appropriate speed and beats-per-minute.

### 2. Select a solid sample set

The first sample will be ST-01/Strings7. It's already proven itself a stolid workhorse. The initial drone will be Strings7.

Select seven other samples from the ST-01 and ST-02 archives which will accomplish the goal and achieve the desired character for the `.mod`. One must be a saxophone to provide the first bars (at least, and maybe more). State which samples are to be looped, if any. The user will determine exact loop points and accept or reject samples for looping. Forward loops are the only kind of loops allowed per **ProTracker 2** compatibility rules.

Analyse the samples' envelopes and recommend default volume settings for each one. Note recorded peak and envelope behaviour. If you don't have access to the samples, report this lack and the user will upload the samples.

Set finetune values to 0. The sample archives predate finetune, so it doesn't apply to them.

Generate note-range maps. Per **PT2** compatibility rules, only octaves 3-5 are allowed. Low-pitched samples should be restricted to octaves 4-5, and high-pitched samples should be restricted to octaves 3-4.

Suggest audition criteria for the samples. The user will audition the sample set based on these criteria.

### 3. Write a structural arc and a motif map

The structural arc should be a narrative guiding the creation of patterns and their reuse in the order list. The structural arc springs forth from the name of the piece, which is our narrative and thematic 'seed'.

Each motif has a descriptive character. For example:

- Motif A: heartbeat kick + bass pulse
- Motif B: descending pad figure
- Motif C: metallic chime
- Motif D: chromatic tension figure

Then each pattern becomes a recombination of those motifs. Do not use this exact example in your motif map.

When this step is complete, remind the user that now is a good time to generate an updated bootstrap Markdown file.

---

## Compatibility Rules

```text
4 channels only
ProTracker-compatible effects only
No XM-only composition features
No notes below C-3
No notes above B-5
Forward sample loops only
No ping-pong loops
Pattern reuse preferred
Exact final runtime is unimportant
```

Bonus points if the final `.mod` weighs in at less than 40KB. This is a difficult goal to achieve.

## Arbitrary Guidelines

- All unpitched percussion hits written as note `C-4`.
- Unless otherwise specified or required, output lone numbers in hex format (eg. "3f").
- Explain effects the first time they're used.

## Tools Used

Testing Operating System: PikaOS
Testing Tracker: MilkyTracker

## Pattern Format

The patterns will not be entered into MilkyTracker directly. Instead, I have written a compiler for the final `.mod`. The compiler requires pattern rows in a specific format, as follows:

`| RR | NNN II EEE | NNN II EEE | NNN II EEE | NNN II EEE |`
where RR is the row number, NNN is the note, II is the instrument slot and EEE is the effect.

Row number must be in decimal, not hex. This is due to a bug in the compiler.

The row format is compatible with Markdown tables, so each pattern should have a Markdown table header. Headers should be 'Row', 'Ch1', 'Ch2', 'Ch3' and 'Ch4'.

Write no note as '---'. Write no instrument as '--'. Write no effect as '---'. Omit entirely empty lines.
