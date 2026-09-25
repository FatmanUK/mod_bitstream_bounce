# Bitstream Bounce: Project Bootstrap File

**Project:** Bitstream Bounce  
**Bootstrap version:** 0.4.0  
**Date:** 2026-09-25  
**Status:** Pre-pattern design complete; exact `Strings7` loop and pattern implementation are next  
**Tracker:** MilkyTracker  
**Platform:** Linux / PikaOS  
**Target format:** 4-channel ProTracker MOD  
**Target length:** 120-180 seconds  
**Projected length:** approximately 2:33  
**Pattern geometry:** 64 rows per pattern  

---

## Source-of-Truth Hierarchy

Use this hierarchy whenever records disagree:

1. **The auditioned project files are authoritative** for exact loop points, final sample volumes, per-row volume edits, finetune values, and any last by-ear edits.
2. **This bootstrap file is authoritative** for project architecture, sample identities, pattern roles, motif roles, order list, note/rhythm/effect structure, and tested status.
3. **The ST-01 and ST-02 archives are source material only.**

Do not restore discarded choices from earlier work. This file contains only the current accepted state.

---

# 1. Current Goal & Next 3 Steps

## Current Goal

Compose an original, polished, early-1990s Amiga game-style tune in 4-channel ProTracker MOD format. The piece should be wild, bouncy party jazz suitable for dancing NPCs, with compact pattern reuse and an unmistakably tracker-built arrangement.

The piece begins with a `Strings7` drone beneath a monophonic lead written with sax-like phrasing. The current lead sample is `ST-02/Bratz`, a provisional brass voice that can later be replaced by a better sax sample without rewriting the part. After several introductory bars, both drone and lead stop cleanly before the main drum groove enters. The composition must not loop. It ends with a deliberate checksum-like flourish rather than a fade.

Musical flow, authenticity, and ProTracker 2 compatibility take precedence over exact runtime and file size. A final size below 40 KiB remains a bonus objective.

## Next 3 Steps

### Step 1: Lock the remaining sample implementation details

- Choose exact even-byte forward loop start and loop length values for `ST-01/Strings7` in MilkyTracker.
- Audition the loop for clicks, periodic pumping, obvious level changes, and tonal wobble.
- Confirm the default balance around `Strings7` volume `20` and `Bratz` volume `24`.
- Keep all finetunes at `00` unless a later auditioned project file explicitly overrides them.

### Step 2: Write and test patterns `00` and `01`

- Write pattern `00`, **Carrier Signal**, in the compiler's Markdown row format.
- Write pattern `01`, **Hard Synchronisation**, with drums first, then staged bass and clav entry.
- Compile the first two patterns with the user's MOD compiler.
- Load the result in MilkyTracker on PikaOS and verify note decoding, sample slots, timing, hard cuts, and effect compatibility.

### Step 3: Complete the arrangement and final verification

- Write patterns `02` through `08` according to the structural and motif maps below.
- Assemble the canonical 22-position order list.
- Compile the complete MOD and test beginning-to-end playback.
- Verify ProTracker compatibility, final coda behavior, runtime, sample loops, channel collisions, and absence of unintended order looping.
- Trim sample tails only if needed for size, without sacrificing the accepted sound.

---

# 2. State of Play

## 2.1 Core Design Decisions

- **Tonal center:** D
- **Primary mode:** D Dorian
- **Turnaround color:** A dominant; use C-sharp only as a brief leading tone
- **Tension color:** occasional E-flat and A-flat in the buffer-failure section
- **Speed:** `06`
- **Tempo:** `8a` hex = 138 BPM
- **Meter:** nominal 4/4
- **Row grid:** normally 4 rows per beat and 16 rows per bar
- **Pattern duration:** approximately 6.96 seconds
- **Stored patterns:** `09` patterns, numbered `00` through `08`
- **Order positions:** `16` hex positions = 22 decimal positions
- **Projected runtime:** approximately 153 seconds, or 2:33
- **Order loop:** none
- **Ending:** unique coda with a final flourish and natural decay

## 2.2 Compatibility Rules

```text
4 channels only
64 rows per pattern
ProTracker-compatible effects only
No XM-only composition features
No notes below C-3
No notes above B-5
Forward sample loops only
No ping-pong loops
Pattern reuse preferred
No order-list loop
Unpitched percussion is always entered as C-4
Finetune defaults to 00 for every selected sample
Exact final runtime is secondary to musical flow and compatibility
```

## 2.3 Current Eight-Slot Sample Set

Volumes are hexadecimal; `40` is the maximum ProTracker sample volume.

| Slot | Source sample | Function | Default volume | Finetune | Loop | Allowed tracker range | Measured behavior |
|---|---|---|---:|---:|---|---|---|
| `01` | `ST-01/Strings7` | Opening drone and later pad | `20` | `00` | Yes, exact forward loop pending | `C-4..B-5` | 9,900 bytes; 1.195 s; peak -3.45 dBFS; sustained, slowly swelling body; strongest measured swell near 0.97 s |
| `02` | `ST-02/Bratz` | Provisional brass lead written like sax | `24` | `00` | No | `C-3..B-4` | 6,500 bytes; 0.784 s; peak 0.00 dBFS; main attack around 64 ms; falls below 20% near 522 ms; natural decay |
| `03` | `ST-01/SlapBass` | Main bass | `1c` | `00` | No | `C-4..B-5` | 4,900 bytes; 0.591 s; peak -0.07 dBFS; strong slap transient; useful body for about 425 ms |
| `04` | `ST-02/BassDrum5` | Kick | `20` | `00` | No | `C-4` only | 3,500 bytes; 0.422 s; full-scale peak; rounded low-frequency body; main decay about 151 ms |
| `05` | `ST-01/Snare4` | Snare | `20` | `00` | No | `C-4` only | 2,000 bytes; 0.241 s; full-scale peak; immediate broad noisy attack; main decay about 81 ms |
| `06` | `ST-01/HiHat2` | Closed hi-hat | `18` | `00` | No | `C-4` only | 2,000 bytes; 0.241 s; peak -0.07 dBFS; bright short noise; main decay about 116 ms |
| `07` | `ST-01/MuteClav` | Syncopated comping | `1c` | `00` | No | `C-4..B-5` | 5,100 bytes; 0.615 s; peak -0.07 dBFS; immediate pluck; main decay about 243 ms |
| `08` | `ST-01/CowBell` | Party accents and fills | `14` | `00` | No | `C-4` only | 1,400 bytes; 0.169 s; full-scale peak; short pitched-metal strike; main decay about 70 ms |

### Sample-writing constraints

- `Bratz` remains monophonic and receives short, breath-shaped phrases with deliberate gaps.
- Retrigger long lead notes rather than relying on an artificial loop.
- Prefer brief pickups, small bends, restrained portamento, and modest vibrato.
- Keep most lead writing in octave 3 and the lower part of octave 4 so a later sax replacement remains practical.
- Keep ordinary `SlapBass` lines mainly in octave 4; reserve octave 5 for fills and peaks.
- Use `CowBell` sparingly as punctuation, not as continuous decoration.
- Loop only `Strings7`. Search roughly between source offsets `1000` and `1c00`, then determine exact even-byte values by ear.

## 2.4 Structural Arc

The narrative is: **a data stream learns to dance**. A carrier signal appears, synchronizes into rhythm, becomes a party routine, suffers a buffer underrun, reboots, overclocks, and signs off with a checksum flourish.

| Phase | Order positions | Patterns | Function |
|---|---:|---|---|
| **Carrier acquired** | `00` | `00` | `Strings7` drone and tentative `Bratz` query; both cut before the beat |
| **Handshake** | `01` | `01` | Abrupt drum entry; drums begin alone; bass and clav lock in by stages |
| **Packets in motion** | `02-04` | `02, 03, 02` | Main groove, animated reply, then home-pattern return |
| **Side-channel party** | `05-09` | `04, 03, 05, 02, 05` | Breakdown, development, and first full statement of the party hook |
| **Buffer underrun** | `0a-0b` | `06, 01` | Fragments and dropped events, followed by literal reboot through reused pattern `01` |
| **Recompiled groove** | `0c-0f` | `02, 03, 05, 04` | Familiar material returns in a restored context; final breath before escalation |
| **Overclocked finale** | `10-14` | `07, 05, 07, 03, 02` | Densest arrangement, upper-register lead, more fills, two climax waves |
| **Checksum coda** | `15` | `08` | Unique closing exchange, groove dismantling, and definite final D-centered strike |

## 2.5 Canonical Pattern Roles

| Pattern | Name | Primary content | Motifs used | Reuse role |
|---:|---|---|---|---|
| `00` | Carrier Signal | `Strings7` and `Bratz`; exposed intro; hard cut | Carrier Lock, Copper Query, Dropped Packet | Unique opening |
| `01` | Hard Synchronisation | Drums alone, then staged bass and clav entry | Clock Lock, Packet Bounce, Split Nibble | Introductory lock-in and later literal reboot |
| `02` | Main Bounce | Core drums, bass, clav, sparse lead or bell tag | Packet Bounce, Clock Lock, Split Nibble, Bell Marker | Principal home pattern; appears five times |
| `03` | Offset Reply | Shifted bass accents, more active lead, end fill | Packet Bounce variation, Copper Query, Clock Lock | Animated answer; appears four times |
| `04` | Sideband Break | Reduced kick, thinner hats, `Strings7`, clav, isolated bell | Carrier Lock variation, Split Nibble, Bell Marker | Breakdown and later pre-finale inhale |
| `05` | Party Hook | Full groove and longest recognizable lead phrase | Packet Bounce, Clock Lock, Copper Query, Bell Marker | Central refrain; appears four times |
| `06` | Buffer Underrun | Missing hits, shortened fragments, chromatic corruption, near-silence | Dropped Packet, corrupted Copper Query, broken Clock Lock | Unique instability event |
| `07` | Overclock | Fullest role exchange, upper lead, denser fills | Overclock Ladder, Packet Bounce, Clock Lock, Copper Query | Two-wave climax |
| `08` | Checksum Coda | Lead/bass exchange, groove dismantling, final flourish | Checksum Flourish, Dropped Packet, Carrier Lock fragment | Unique ending |

## 2.6 Motif Map

### Motif A: Carrier Lock

- **Instrument:** `Strings7`
- **Character:** calm carrier signal beneath surrounding motion
- **Pitch center:** sustained `D-4`, with occasional `A-4` or rearticulated `D-4`
- **Rhythm:** long values and slow volume shaping
- **Patterns:** `00`, `04`, `08`

### Motif B: Packet Bounce

- **Instrument:** `SlapBass`
- **Character:** springy syncopated propulsion
- **Pitch skeleton:**

```text
D-4  A-4  C-5  D-5  B-4  A-4
```

- Preserve the opening attack and the rests around it.
- Variations may omit octave notes, displace the final note, or shorten the idea to one bar.
- **Patterns:** `01`, `02`, `03`, `05`, `07`

### Motif C: Clock Lock

- **Instruments:** `BassDrum5`, `Snare4`, `HiHat2`
- **Character:** the machine locating a danceable pulse
- Kick anchors beat one and answers around beats two and three.
- Snare establishes beats two and four.
- Hats favor offbeats, with short sixteenth-note activity near phrase endings.
- Vary mainly through subtraction and fills rather than replacing the groove.
- **Patterns:** all except most of `00`

### Motif D: Split Nibble

- **Instrument:** `MuteClav`
- **Character:** dry clipped harmonic answers
- **Typical sequential note pairs:**

```text
F-4 / A-4
G-4 / B-4
E-4 / G-4
```

- These are sequential jabs, not simultaneous two-note chords.
- **Patterns:** `01`, `02`, `03`, `04`, `05`

### Motif E: Copper Query

- **Instrument:** `Bratz`, replaceable later by sax
- **Character:** a brassy question phrased like a reed lead
- **Pitch skeleton:**

```text
A-3  C-4  D-4  F-4
E-4  C#4 D-4
```

- Use rests, pickups, occasional restrained portamento, and breath-shaped phrase lengths.
- `00` is tentative, `05` is the full statement, and `07` extends upward without exceeding `B-4`.
- **Patterns:** `00`, `03`, `05`, `07`

### Motif F: Bell Marker

- **Instrument:** `CowBell`
- **Note:** always `C-4`
- **Character:** displaced party punctuation, sometimes implying a `3+3+2` grouping
- **Patterns:** `02`, `04`, `05`, `07`

### Motif G: Dropped Packet

- **Instruments:** any or all channels
- **Character:** an expected event is omitted, followed by a strong synchronized return
- **Patterns:** `00`, `06`, `08`

### Motif H: Overclock Ladder

- **Instrument:** `Bratz`, answered by `SlapBass`
- **Lead contour:**

```text
D-4  F-4  G-4  A-4  B-4
```

- The bass answers in contrary motion instead of doubling the lead.
- **Pattern:** `07`

### Motif I: Checksum Flourish

- **Instruments:** `Bratz`, `SlapBass`, drums, optional brief `Strings7`
- **Lead contour:**

```text
B-4  A-4  G-4  F-4  E-4  D-4
```

- The bass rises or leaps while the lead descends.
- A compact drum flourish resolves to a final D-centered strike.
- **Pattern:** `08`

## 2.7 Default Channel Grammar

| Channel | Normal responsibility |
|---|---|
| Ch1 | Kick and snare |
| Ch2 | `SlapBass` |
| Ch3 | `HiHat2`, or `Strings7` when hats thin out |
| Ch4 | `Bratz`, `MuteClav`, or `CowBell` |

Pattern `00` is the main exception:

| Channel | Pattern `00` responsibility |
|---|---|
| Ch1 | `Strings7` |
| Ch2 | Usually empty |
| Ch3 | Usually empty |
| Ch4 | `Bratz` |

The upper-register instruments deliberately share Ch4. This enforces call-and-response writing and prevents accidental five-channel thinking. When the lead speaks, clav normally stops. When cowbell strikes, it replaces another upper event rather than accompanying it.

## 2.8 Canonical Order List

```text
00, 01, 02, 03, 02, 04, 03, 05, 02, 05, 06,
01, 02, 03, 05, 04, 07, 05, 07, 03, 02, 08
```

Reuse count:

| Pattern | Uses |
|---:|---:|
| `00` | 1 |
| `01` | 2 |
| `02` | 5 |
| `03` | 4 |
| `04` | 2 |
| `05` | 4 |
| `06` | 1 |
| `07` | 2 |
| `08` | 1 |

## 2.9 Size Budget

```text
Current untrimmed sample payload: 0x89e4 = 35,300 bytes
Nine stored patterns:              0x2400 =  9,216 bytes
MOD header/sample table:           0x043c =  1,084 bytes
Projected untrimmed total:         0xb220 = 45,600 bytes
40 KiB target:                     0xa000 = 40,960 bytes
Required reduction for bonus goal: 0x1220 =  4,640 bytes
```

The most plausible savings are a compact accepted `Strings7` loop and conservative removal of inaudible sample tails. Do not damage attacks, natural decays, or the accepted balance merely to hit the bonus size.

---

# 3. Dependency Map & Version Log

## 3.1 Dependency Map

```text
ST-01 archive -----------------------------------------------+
  Strings7, SlapBass, Snare4, HiHat2, MuteClav, CowBell      |
                                                              +--> canonical 8-slot sample manifest
ST-02 archive -----------------------------------------------+              |
  Bratz, BassDrum5                                                          |
                                                                            v
Exact Strings7 loop + final by-ear volumes ---------------------> pattern tables 00-08
                                                                            |
Canonical motif map + pattern roles + order list ---------------------------+
                                                                            v
User-owned Markdown-to-MOD compiler
  input row grammar: Row | Ch1 | Ch2 | Ch3 | Ch4
                                                                            |
                                                                            v
Bitstream Bounce.mod
                                                                            |
                                                                            v
MilkyTracker on PikaOS
  load test -> playback test -> loop test -> compatibility test -> final approval
```

## 3.2 Required Dependencies

| Dependency | Required state | Current state |
|---|---|---|
| `ST-01` archive | Selected source samples available | Present and inspected |
| `ST-02` archive | Selected source samples available | Present and inspected |
| `Strings7` exact loop | Even-byte forward loop, auditioned | Pending |
| Sample default volumes | Starting values available; final values by ear | Starting values established |
| User MOD compiler | Must accept documented Markdown row format | Compiler exists; version not provided |
| MilkyTracker | Final playback and inspection | Available on target platform; version not provided |
| PikaOS | Test operating system | Selected; version not provided |
| Pattern tables `00-08` | Complete compiler input | Not yet written |
| Final `.mod` | Compiled, loaded, and auditioned | Not yet produced |

## 3.3 Accepted Version Log

This log records accepted milestones only. It does not preserve discarded alternatives.

| Version | Date | Accepted milestone |
|---|---|---|
| `0.1.0` | 2026-09-25 | Project identity, PT2 target, four-channel limit, 64-row patterns, non-looping coda, and compiler row grammar established |
| `0.2.0` | 2026-09-25 | Eight-slot sample manifest accepted; `Bratz` designated as provisional sax-shaped lead; starting volumes and ranges established |
| `0.3.0` | 2026-09-25 | Tempo, tonal plan, narrative arc, nine-pattern architecture, 22-position order list, motif map, and channel grammar completed |
| `0.4.0` | 2026-09-25 | Current comprehensive bootstrap consolidated as the canonical project handoff |

---

# 4. Golden Code Blocks

These blocks are the canonical values to copy forward. Do not substitute older values.

## 4.1 Project Constants

```yaml
project:
  title: "Bitstream Bounce"
  format: "4-channel ProTracker MOD"
  tracker: "MilkyTracker"
  platform: "Linux / PikaOS"
  rows_per_pattern: 64
  speed_hex: "06"
  tempo_hex: "8a"
  tempo_bpm_decimal: 138
  tonal_center: "D"
  primary_mode: "D Dorian"
  stored_patterns_hex: "09"
  order_positions_hex: "16"
  order_positions_decimal: 22
  projected_runtime_seconds: 153
  loop_order_list: false
  final_coda: true
```

## 4.2 Canonical Sample Manifest

```yaml
samples:
  "01":
    source: "ST-01/Strings7"
    role: "drone and pad"
    volume_hex: "20"
    finetune_hex: "00"
    loop: "forward; exact even-byte values pending audition"
    range: "C-4..B-5"

  "02":
    source: "ST-02/Bratz"
    role: "provisional brass lead written with sax-like phrasing"
    volume_hex: "24"
    finetune_hex: "00"
    loop: "none"
    range: "C-3..B-4"

  "03":
    source: "ST-01/SlapBass"
    role: "bass"
    volume_hex: "1c"
    finetune_hex: "00"
    loop: "none"
    range: "C-4..B-5"

  "04":
    source: "ST-02/BassDrum5"
    role: "kick"
    volume_hex: "20"
    finetune_hex: "00"
    loop: "none"
    range: "C-4 only"

  "05":
    source: "ST-01/Snare4"
    role: "snare"
    volume_hex: "20"
    finetune_hex: "00"
    loop: "none"
    range: "C-4 only"

  "06":
    source: "ST-01/HiHat2"
    role: "closed hi-hat"
    volume_hex: "18"
    finetune_hex: "00"
    loop: "none"
    range: "C-4 only"

  "07":
    source: "ST-01/MuteClav"
    role: "syncopated comping"
    volume_hex: "1c"
    finetune_hex: "00"
    loop: "none"
    range: "C-4..B-5"

  "08":
    source: "ST-01/CowBell"
    role: "party accents and fills"
    volume_hex: "14"
    finetune_hex: "00"
    loop: "none"
    range: "C-4 only"
```

## 4.3 Canonical Order List

```text
00 01 02 03 02 04 03 05 02 05 06 01 02 03 05 04 07 05 07 03 02 08
```

## 4.4 Pattern-to-Motif Map

```yaml
patterns:
  "00": ["Carrier Lock", "Copper Query", "Dropped Packet"]
  "01": ["Clock Lock", "Packet Bounce", "Split Nibble"]
  "02": ["Packet Bounce", "Clock Lock", "Split Nibble", "Bell Marker"]
  "03": ["Packet Bounce variation", "Copper Query", "Clock Lock"]
  "04": ["Carrier Lock variation", "Split Nibble", "Bell Marker"]
  "05": ["Packet Bounce", "Clock Lock", "Copper Query", "Bell Marker"]
  "06": ["Dropped Packet", "corrupted Copper Query", "broken Clock Lock"]
  "07": ["Overclock Ladder", "Packet Bounce", "Clock Lock", "Copper Query"]
  "08": ["Checksum Flourish", "Dropped Packet", "Carrier Lock fragment"]
```

## 4.5 Compiler Row Grammar

The compiler requires decimal row numbers. Notes, instrument slots, and effects retain tracker notation.

```text
| RR | NNN II EEE | NNN II EEE | NNN II EEE | NNN II EEE |
```

Canonical Markdown header:

```markdown
| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
```

Empty fields:

```text
no note       = ---
no instrument = --
no effect     = ---
```

Rules:

```text
Row numbers are decimal, not hexadecimal.
Omit entirely empty rows.
Use two hexadecimal digits for instrument numbers.
Use three tracker characters for effects.
Explain an effect the first time it appears in project documentation.
```

Example syntax only, not composed pattern content:

```markdown
| Row | Ch1 | Ch2 | Ch3 | Ch4 |
|---:|---|---|---|---|
| 0 | C-4 04 --- | --- -- --- | --- -- --- | --- -- --- |
```

## 4.6 Default Channel Assignment

```yaml
channels:
  normal:
    Ch1: "kick and snare"
    Ch2: "SlapBass"
    Ch3: "HiHat2 or Strings7"
    Ch4: "Bratz, MuteClav, or CowBell"

  pattern_00:
    Ch1: "Strings7"
    Ch2: "usually empty"
    Ch3: "usually empty"
    Ch4: "Bratz"
```

---

# 5. Tested & Passing Status Confirmation

## 5.1 Passing Now

| Check | Status | Confirmation |
|---|---|---|
| Source archives accessible | PASS | Both ST-01 and ST-02 tarballs were opened and inspected |
| Selected sample paths present | PASS | All eight canonical source sample names exist in the supplied archives |
| Sample analysis | PASS | Length, duration, peak, envelope behavior, and starting volume were measured for all eight slots |
| Sample identity review | PASS WITH PROVISION | Slots `01` and `03-08` are accepted; slot `02` is accepted as the current provisional brass lead and is intentionally replaceable by a later sax sample |
| PT2 note-range policy | PASS AT DESIGN LEVEL | Every assigned range remains inside `C-3..B-5`; low material is restricted upward and high material downward as planned |
| Finetune policy | PASS AT DESIGN LEVEL | Every selected sample is currently fixed at `00` |
| Loop policy | PASS AT DESIGN LEVEL | Only `Strings7` is designated for a forward loop; no ping-pong loops are planned |
| Structural arc | PASS | Narrative arc, pattern roles, reuse strategy, and non-looping coda are defined |
| Motif map | PASS | Nine named motifs and their pattern assignments are defined |
| Order list | PASS AT DESIGN LEVEL | Canonical 22-position sequence is defined and uses nine stored patterns |
| Runtime target | PASS BY CALCULATION | 22 positions at speed `06`, tempo `8a`, and 64 rows project to about 153 seconds |
| Compiler input grammar | PASS AS DOCUMENTED | Required Markdown table format and decimal row-number rule are recorded |

## 5.2 Not Yet Tested

| Check | Status | Required action |
|---|---|---|
| Exact `Strings7` loop | PENDING | Choose and audition exact even-byte loop start and length in MilkyTracker |
| Final default sample balance | PENDING | Confirm starting volumes in the actual arrangement, not only isolated montages |
| Pattern row data | NOT STARTED | Compose patterns `00-08` in compiler format |
| Compiler execution | NOT TESTED | Compile at least patterns `00-01`, then the complete order list |
| MilkyTracker load | NOT TESTED | Open the compiled MOD on PikaOS and inspect sample, pattern, and order data |
| Beginning-to-end playback | NOT TESTED | Audition timing, transitions, hard cuts, role swaps, and coda |
| PT2 effect compatibility | NOT TESTED | Verify every used effect after pattern composition |
| Final runtime | NOT TESTED | Measure compiled playback duration |
| Final file size | NOT TESTED | Measure compiled MOD; optimize only after musical approval |
| Final sax substitution | OPTIONAL / UNRESOLVED | Replace `Bratz` only when a better compatible sax sample is available and auditioned |

## 5.3 Current Confirmation

The **design phase through structural arc and motif mapping is complete and internally consistent**. The sample manifest, tempo, harmony, pattern architecture, order list, motif assignments, channel grammar, and compiler syntax are ready for pattern writing.

No final `.mod` exists yet. Therefore, this bootstrap does **not** claim a successful compiler run, MilkyTracker playback pass, exact loop pass, final PT2 compatibility pass, or final size pass. Those confirmations begin with patterns `00` and `01` in the next stage.
