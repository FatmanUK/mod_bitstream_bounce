# ST-02/Tubes analysis

| Property | Result |
|---|---:|
| Format | Headerless signed 8-bit PCM |
| Length | 7,000 bytes, `1b58` hex |
| Duration at 8,287 Hz | 0.845 seconds |
| Peak | 0.00 dBFS |
| RMS | −12.55 dBFS |
| Main envelope peak | About 52 ms |
| Main body below 20% | About 146 ms |
| Resonant tail below 10% | About 516 ms |
| Last 100 ms RMS | −31.33 dBFS |
| Estimated fundamental | About 259 Hz |
| Approximate pitch | C4, 18 cents flat |
| Strongest partial | About 519 Hz |
| Spectral centroid | About 515 Hz |
| Energy below 1 kHz | About 97.8% |
| Loop | None |
| Finetune | `00` |


bytes	sample_rate_hz	duration_s	peak	peak_dbfs	rms	rms_dbfs	dc_mean	zero_crossing_rate	envelope_peak_ms	decay_below_20pct_ms	decay_below_10pct_ms	tail_rms_dbfs_last100ms	sustain_ratio_last_quarter_to_first	spectral_centroid_hz	spectral_rolloff85_hz	spectral_flatness	autocorr_f0_hz	autocorr_strength	pitch_estimate	clip_count	last_sample_value_int8	last_nonzero_index
7000	8287.0	0.8446965126101122	1.0	0.0	0.2357896296319333	-12.549505994374732	-0.013415178571428571	0.1264466352336048	51.76782912996259	146.01182575117656	515.6268854832871	-31.33232710550513	0.07870895319787026	515.2339556140073	524.4487142857142	0.0012112628011176781	258.96875	0.9955777346127516	C4-18c	54	0	6997

```
"08":
  source: "ST-02/Tubes"
  role: "rare pitched tubular/metallic structural accent"
  default_volume_hex: "20"
  accent_volume_hex: "28"
  finetune_hex: "00"
  loop: "none"
  recommended_range: "C-3..B-4"
  preferred_stab_register: "C-3..B-3"
```

Start exposed hits at C28. The sensible comparison range is C24, C28, and C2A. There is no compelling reason to hurl it at C40 unless the rest of the arrangement has become an active demolition site.

A literal C-5 08 replacement in Pattern 06 will be a very short, brilliant flash. That may be exactly what you heard and accepted. For more body, audition the same event at C-4 08. Octave 3 is preferable for the weighty, sonorous structural hits.

