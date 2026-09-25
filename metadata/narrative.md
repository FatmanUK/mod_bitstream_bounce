## Structural arc: “a data stream learns to dance”

“Bitstream Bounce” becomes a miniature narrative: a carrier signal appears, synchronises into rhythm, turns into a full dance routine, suffers a buffer failure, reboots, overclocks, and finally signs off with a checksum flourish. This gives the repeated patterns an actual dramatic purpose instead of merely revealing that Amiga memory was expensive. The bootstrap specifically calls for the title to seed the narrative, with motifs recombined across reused patterns. 

The arrangement remains a four-channel, 64-row ProTracker MOD for MilkyTracker.  It preserves the required Strings7-and-lead opening, abrupt transition into the main beat, extensive pattern reuse, and definite non-fading coda. 

### Tonal and rhythmic foundation

This is a new composition decision rather than something dictated by the bootstrap:

* **Tonal centre:** D
* **Primary colour:** D Dorian
* **Turnaround colour:** A dominant, using C-sharp only as a brief leading tone
* **Tension colour:** occasional E-flat and A-flat during the buffer-failure section
* **Speed:** `06`
* **Tempo:** `8a`
* **Meter:** nominal 4/4, usually four tracker rows per beat
* **Approximate pattern duration:** 6.96 seconds
* **Proposed order length:** `16` hex positions, meaning 22 decimal positions
* **Approximate total runtime:** 2:33

D Dorian supplies minor-key character without becoming gloomy. The natural B gives the bass and clav parts a slightly brighter jazz-funk lift, while the A-dominant turnaround provides a strong route back to D.

## Structural arc

| Phase                  | Order positions | Patterns             | Narrative and musical function                                                                                                                                                                              |
| ---------------------- | --------------: | -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Carrier acquired**   |            `00` | `00`                 | Strings7 drone appears in isolation. Bratz enters as a provisional sax-shaped voice, cautiously probing the signal. Both are cut before the beat begins.                                                    |
| **Handshake**          |            `01` | `01`                 | Main drums arrive abruptly. The first part is deliberately drum-only; bass and clav enter in stages, as though separate channels are locking to the clock.                                                  |
| **Packets in motion**  |         `02–04` | `02, 03, 02`         | The principal groove is established, answered by a busier variation, then restated. This is the first complete dance section.                                                                               |
| **Side-channel party** |         `05–09` | `04, 03, 05, 02, 05` | The texture briefly opens, Strings7 returns in a supporting role, and the lead develops into the main hook. Pattern `05` becomes the recognisable party refrain.                                            |
| **Buffer underrun**    |         `0a–0b` | `06, 01`             | Notes fragment, expected hits disappear, and the whole system appears to lose synchronisation. Pattern `01` then returns unchanged as a literal reboot.                                                     |
| **Recompiled groove**  |         `0c–0f` | `02, 03, 05, 04`     | Familiar patterns return in a new dramatic context. The listener now hears them as restored material rather than simple repetition. Pattern `04` creates breathing room before the final escalation.        |
| **Overclocked finale** |         `10–14` | `07, 05, 07, 03, 02` | The densest version of the tune. The lead reaches its highest register, fills become more frequent, and the main motifs collide in controlled fashion. The final `02` acts as a deceptive return to normal. |
| **Checksum coda**      |            `15` | `08`                 | A unique closing flourish dismantles the groove, exchanges short figures between lead and bass, and ends on a deliberate final strike rather than a fade or loop.                                           |

The complete proposed order list is:

```text
00, 01, 02, 03, 02, 04, 03, 05, 02, 05, 06,
01, 02, 03, 05, 04, 07, 05, 07, 03, 02, 08
```

There are only `09` physically stored patterns. Pattern reuse does most of the structural work:

* `02` appears five times as the musical “home”.
* `03` appears four times as its more animated answer.
* `05` appears four times as the main party hook.
* `01` first introduces the machine and later reboots it.
* `04` first opens the arrangement and later prepares the finale.
* `07` occurs twice, separated by `05`, so the climax arrives in two waves.
* `00`, `06`, and `08` remain unique narrative events.

## Pattern roles

### Pattern `00`: Carrier Signal

**Primary material:** Strings7, Bratz
**Motifs:** Carrier Lock, Copper Query, Null Packet

Strings7 holds a low D-centred drone. Bratz enters with a restrained, monophonic phrase, leaving conspicuous breathing spaces. The opening should feel inquisitive rather than immediately frantic.

The final quarter cuts both drone and lead. A brief silence or isolated count-in gesture prepares the drum entrance. The cut must be unambiguous, because the bootstrap explicitly asks for the opening pair to disappear before the main beat. Humanity occasionally writes a useful specification. 

### Pattern `01`: Hard Synchronisation

**Primary material:** drums, then bass and clav
**Motifs:** Clock Lock, Packet Bounce, Split Nibble

The first eight rows are drums alone. Bass enters next; MuteClav joins after the groove has stabilised. Bratz remains absent.

Because this exact pattern follows the buffer-failure pattern later, its staged entrances also sound like system components coming back online. No altered duplicate is needed.

### Pattern `02`: Main Bounce

**Primary material:** full rhythm section with sparse lead punctuation
**Motifs:** Packet Bounce, Clock Lock, Split Nibble, Bell Marker

This is the core dance pattern and therefore must survive repeated hearings. Its interest should come from internal four-bar phrasing:

1. Establish bass and backbeat.
2. Add the clav response.
3. Introduce a small bass variation.
4. End with a short lead or cowbell tag pointing toward the next pattern.

Bratz should not play continuously. Its absence leaves room for the bass and clav groove to become memorable.

### Pattern `03`: Offset Reply

**Primary material:** varied bass, more active lead response
**Motifs:** Packet Bounce variation, Copper Query, Clock Lock

The harmony remains recognisable, but the bass accents shift and the lead answers phrases left incomplete in `02`. The drum groove gains a short fill near the end.

This is not a completely new section. It is the same data interpreted with different timing, which sounds suitably technical while sparing another kilobyte.

### Pattern `04`: Sideband Break

**Primary material:** reduced drums, Strings7, clav, isolated bell
**Motifs:** Carrier Lock variation, Split Nibble, Bell Marker

The kick thins out, hats become less continuous, and Strings7 returns without recreating the introduction. Short clav figures imply the harmony while CowBell marks selected phrase boundaries.

Its first appearance acts as a breakdown. Its second appearance, much later, becomes the inhale before the final escalation.

### Pattern `05`: Party Hook

**Primary material:** full drums, bass, principal Bratz phrase
**Motifs:** Packet Bounce, Clock Lock, Copper Query, Bell Marker

This is the tune’s central refrain. Bratz states the longest and most recognisable phrase here, but it remains written like a saxophone:

* one note at a time;
* clear breaths;
* short pickups;
* restrained scoops;
* held notes only where a later sax sample could sustain them naturally.

The hook should end with enough space for the bass to answer, rather than filling every row like an anxious ringtone.

### Pattern `06`: Buffer Underrun

**Primary material:** fragments and silence
**Motifs:** Dropped Packet, corrupted Copper Query, broken Clock Lock

This is the sole deliberate instability section. Elements fail in sequence:

1. Hats disappear.
2. Bass repeats a shortened fragment.
3. Clav or lead lands on an unexpected chromatic note.
4. A kick arrives without its expected snare reply.
5. A short near-silence creates the impression of lost synchronisation.
6. A compressed drum fill throws the tune directly into reused pattern `01`.

The disruption should remain rhythmically legible. It is a buffer failure, not somebody dropping the MOD file down a staircase.

### Pattern `07`: Overclock

**Primary material:** fullest four-channel arrangement
**Motifs:** Overclock Ladder, Packet Bounce, Clock Lock, Copper Query

The lead reaches upward more often, bass fills become denser, and CowBell accents appear at wider intervals. Because four channels remain four channels regardless of artistic ambition, texture changes must be achieved through rapid role exchange:

* hats yield briefly to clav;
* clav yields to lead;
* lead rests during drum fills;
* CowBell replaces, rather than accompanies, another upper-register event.

The second occurrence can remain byte-for-byte identical. Its greater intensity will come from placement between `05` and the final run of familiar material.

### Pattern `08`: Checksum Coda

**Primary material:** lead, bass, drums, final Strings7 trace
**Motifs:** Checksum Flourish, Null Packet, Carrier Lock fragment

The coda should proceed in three stages:

1. The main groove begins normally but sheds parts.
2. Bratz and SlapBass exchange short descending and ascending figures.
3. A compact drum flourish leads to a final D-centred strike.

Strings7 may return very briefly beneath the final cadence, linking the ending to the opening. The final event should decay naturally into silence. There is no order-list loop and no fade, in accordance with the project goal. 

## Motif map

### Motif A: Carrier Lock

**Character:** calm signal beneath surrounding chaos
**Instrument:** Strings7
**Pitch skeleton:** sustained `D-4`, with occasional rearticulation on `A-4` or a brief return to `D-4`
**Rhythmic identity:** long values and slow volume shaping
**Appears in:** `00`, `04`, `08`

The opening version is exposed. In `04` it becomes a supporting pad. In `08` it returns only as a memory.

### Motif B: Packet Bounce

**Character:** springy, syncopated forward motion
**Instrument:** SlapBass
**Pitch skeleton:**

```text
D-4  A-4  C-5  D-5  B-4  A-4
```

The exact rests matter more than the literal sequence. Notes should land around the kick rather than mechanically doubling it.

**Appears in:** `01`, `02`, `03`, `05`, `07`

Transformations include omitted octave notes, displaced final notes, and shortened one-bar fragments. The recognisable opening attack should remain intact.

### Motif C: Clock Lock

**Character:** the machine finding a danceable pulse
**Instruments:** BassDrum5, Snare4, HiHat2
**Basic behaviour:**

* kick anchors beat one;
* additional kick answers around beats two and three;
* snare establishes beats two and four;
* hats favour offbeats, with brief sixteenth-note activity near phrase endings.

**Appears in:** every pattern except most of `00`

Its variations should come from subtraction and fills, not replacing the groove every few seconds.

### Motif D: Split Nibble

**Character:** dry, clipped harmonic answer
**Instrument:** MuteClav
**Pitch language:** short alternating notes implying D minor, G major, and A dominant colours

Typical note pairs might include:

```text
F-4 / A-4
G-4 / B-4
E-4 / G-4
```

These are sequential jabs, not literal two-note chords. The instrument gets one channel, because physics remains obstinate.

**Appears in:** `01`, `02`, `03`, `04`, `05`

### Motif E: Copper Query

**Character:** brassy question written for a future saxophone
**Instrument:** Bratz, later replaceable by a better sax sample
**Pitch skeleton:**

```text
A-3  C-4  D-4  F-4
E-4  C#4 D-4
```

The phrase should use rests, small pickups, and occasional restrained portamento. A held final D may receive gentle vibrato when the rows are written.

**Appears in:** `00`, `03`, `05`, `07`

The opening version is tentative. Pattern `05` presents the complete phrase. Pattern `07` extends it upward without exceeding `B-4`.

### Motif F: Bell Marker

**Character:** an exclamation point rather than constant decoration
**Instrument:** CowBell
**Note:** always `C-4`, following the project’s percussion convention. 
**Rhythmic identity:** isolated displaced accents, sometimes suggesting a `3+3+2` grouping
**Appears in:** `02`, `04`, `05`, `07`

It should be used sparingly. Cowbell ceases to be festive when it begins filing taxes.

### Motif G: Dropped Packet

**Character:** negative space used as an audible event
**Instruments:** potentially all channels
**Musical action:** an expected note or beat is omitted, followed by a forceful synchronised return
**Appears in:** `00`, `06`, `08`

In `00` it separates the introduction from the beat. In `06` it becomes structural failure. In `08` it creates room before the final hit.

### Motif H: Overclock Ladder

**Character:** rising pressure and slightly reckless optimism
**Instrument:** Bratz, answered by SlapBass
**Lead contour:**

```text
D-4  F-4  G-4  A-4  B-4
```

The bass answers in the opposite direction, rather than doubling the lead. This prevents the four-channel texture from becoming a single thick line.

**Appears in:** `07`

### Motif I: Checksum Flourish

**Character:** final confirmation that the piece has ended correctly
**Instruments:** Bratz, SlapBass, drums, optional Strings7
**Lead contour:**

```text
B-4  A-4  G-4  F-4  E-4  D-4
```

The bass rises or leaps while the lead descends. A final compact drum fill resolves to D, optionally with a very short Strings7 return beneath it.

**Appears in:** `08` only

## Default channel grammar

This is a working allocation, not an inflexible rule:

| Channel | Usual responsibility                       |
| ------- | ------------------------------------------ |
| Ch1     | Kick and snare                             |
| Ch2     | SlapBass                                   |
| Ch3     | HiHat2, or Strings7 when the hats thin out |
| Ch4     | Bratz, MuteClav, or CowBell                |

The upper instruments deliberately share Ch4. That forces call-and-response writing and prevents the arrangement from becoming cluttered. When Bratz speaks, MuteClav usually stops. When CowBell strikes, it replaces another accent rather than magically creating a fifth channel.

The intro is the main exception:

| Channel | Pattern `00` role |
| ------- | ----------------- |
| Ch1     | Strings7          |
| Ch2     | Mostly empty      |
| Ch3     | Mostly empty      |
| Ch4     | Bratz             |

All later pattern writing must remain inside the stated PT2 limits: four channels, ProTracker-compatible effects, notes from `C-3` through `B-5`, and forward loops only. 

## Compactness consequence

With `09` unique patterns:

* Pattern data: `2400` bytes
* MOD header and sample table: `043c` bytes
* Maximum total for the bonus target: `a000` bytes
* Remaining sample allowance: `77c4` bytes
* Current untrimmed sample payload: `89e4` bytes
* Required reduction to cross the 40 KiB line: approximately `1220` bytes

That reduction appears plausible through the accepted Strings7 loop and conservative tail trimming. It should remain secondary to sound quality, as the bootstrap says compatibility and musical flow matter more than exact size. 

The structural arc and motif map are now complete. This is the checkpoint at which the bootstrap says to generate an updated Markdown project file.  After that snapshot, the next composition task is pattern `00`, written in the compiler’s Markdown row format.
