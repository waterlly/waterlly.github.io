# FlightGear warning samples

The five legacy warning WAVs are original, byte-for-byte samples from FGDATA/fgdata at commit `e41d83b90f80b88b28a2027aa9caa6e02ae0d64a`, distributed under GPL-2.0-or-later. See [manifest.json](manifest.json) for exact source URLs, Git blob hashes, SHA-256 checksums and sample metadata, and [COPYING](COPYING) for the original license.

PULL UP, SINK RATE, TOO LOW GEAR and TRAFFIC use FlightGear prerecorded simulator voice samples. The legacy generic STALL horn remains available for C182 and unclassified profiles. No manufacturer hardware or human-recording provenance is asserted. English browser/OS speech synthesis is a separately identified fallback for non-transport-stall warnings only if a sample cannot play.

The five legacy WAVs and the three new source WAVs retain their original bytes. The Airbus playback cue is a separate arrangement described below. Runtime playback normalizes peak gain with headroom, then applies the user volume from 0 to 1.

## Aircraft-specific stall cues

Airbus profiles use a two-second game arrangement of original FlightGear A320-family cricket and STALL STALL WAVs. The three original source WAVs are preserved byte-for-byte. The new arrangement uses an approximate simulator cadence, not a manufacturer hardware recording. Boeing profiles share the original FlightGear 737 simulator stick-shaker WAV; C182 and unclassified profiles retain the legacy horn. All stall cues loop until cleared or stopped. Transport stall cues never fall back to browser text-to-speech. Other warning speech fallback is unchanged.

New GPL-2.0 source licenses, copyright and acknowledgements are linked individually in manifest.json; the legacy five samples keep their existing GPL-2.0-or-later records.
