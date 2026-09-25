## Recommended eight-slot set

Volumes are hexadecimal; 40 is maximum. Finetune is 00 throughout.

| Slot | Sample            | Function                    | Volume | Loop    | Tracker range | Measured behaviour                                                                   |
| ---- | ----------------- | --------------------------- | -----: | ------- | ------------- | ------------------------------------------------------------------------------------ |
| 01   | `ST-01/Strings7`  | Opening drone and later pad |   `20` | **Yes** | `C-4..B-5`    | Peak −3.45 dBFS; sustained, modulating envelope with its largest swell near 0.97 s   |
| 02   | `ST-02/Blower`    | Primary sax candidate       |   `28` | No      | `C-3..B-4`    | Peak −1.72 dBFS; 85 ms rise, articulated decay, secondary late swell                 |
| 03   | `ST-01/SlapBass`  | Main bass                   |   `1c` | No      | `C-4..B-5`    | Peak −0.07 dBFS; strong slap transient, approximately 425 ms decay                   |
| 04   | `ST-02/BassDrum5` | Kick                        |   `20` | No      | `C-4`         | Full-scale peak; rounded low-frequency body, approximately 151 ms decay              |
| 05   | `ST-01/Snare4`    | Snare                       |   `20` | No      | `C-4`         | Full-scale peak; immediate attack, broad noisy spectrum, approximately 81 ms decay   |
| 06   | `ST-01/HiHat2`    | Closed hi-hat               |   `18` | No      | `C-4`         | Peak −0.07 dBFS; very bright, approximately 116 ms decay, clean zero-valued endpoint |
| 07   | `ST-01/MuteClav`  | Syncopated comping          |   `1c` | No      | `C-4..B-5`    | Peak −0.07 dBFS; immediate pluck, approximately 243 ms decay                         |
| 08   | `ST-01/CowBell`   | Party accents and fills     |   `14` | No      | `C-4`         | Full-scale peak; short pitched-metal strike, approximately 70 ms decay               |

### Sax caveat

Blower is the strongest sax candidate, based on its reed-like harmonic structure, breath/noise component, articulated envelope, and useful one-second duration. The archive does not explicitly label anything “saxophone,” however, so this is a signal-analysis choice rather than documentary certainty. Licks and Licks2 are included as direct comparisons. Your audition remains the deciding evidence, as it should be under the source-of-truth hierarchy rather than allowing a filename to acquire religious authority.

### Loop recommendation

Loop only Strings7. A promising search area for the forward loop is between source offsets approximately 1000 and 1c00. That region retains the chorused body while avoiding the final level drop. Exact start and length should be selected by ear and stored as even-byte MOD loop values.

The other samples depend on their attacks and natural decays. Looping them would turn intentional articulation into the sonic equivalent of a ceiling fan with a damaged bearing.

### Size consequence

The untrimmed primary sample payload is 940c bytes, or 37,900 decimal bytes, before the MOD header or any pattern data. A final file below 40 KiB will therefore require:

shortening the quiet tails of Blower, BassDrum5, and MuteClav;
replacing most of Strings7 with a compact accepted loop;
aggressive pattern reuse and very few physically stored patterns.

That remains a bonus objective, not something worth damaging the tune to achieve. The bootstrap explicitly prioritizes musical flow and compatibility over exact size or runtime.
