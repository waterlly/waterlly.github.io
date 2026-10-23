# FlightGear warning samples

Original, byte-for-byte samples from FGDATA/fgdata at commit `e41d83b90f80b88b28a2027aa9caa6e02ae0d64a`, distributed under GPL-2.0-or-later. See [manifest.json](manifest.json) for exact source URLs, Git blob hashes, SHA-256 checksums and sample metadata, and [COPYING](COPYING) for the original license.

PULL UP, SINK RATE, TOO LOW GEAR and TRAFFIC use FlightGear prerecorded simulator voice samples. STALL uses the original sampled warning horn; it is not an English voice recording. No manufacturer hardware or human-recording provenance is asserted. English browser/OS speech synthesis is a separately identified fallback only if a sample cannot play.

Asset bytes are unchanged. Runtime playback normalizes peak gain with headroom, then applies the user volume from 0 to 1.
