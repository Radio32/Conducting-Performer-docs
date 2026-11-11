# Conducting Performer

**A chord-led firmware for the PER|FORMER eurorack sequencer.** One conductor plays a chord
progression; every track follows it in its own role: arpeggio, bass, melody, drums or modulation.
Change a chord and the whole band moves with it.

Current version: **1.14.2**

## The idea

Most step sequencers play notes. The Conducting Performer plays *music around a harmony*: you set
up a progression of chords, and the tracks turn their patterns into notes that fit the chord that
plays. Patterns, phrases and drum beats come from a library on the SD card, can be captured from
what you play, and are arranged into sections and a playlist, so a module on its own can carry a
whole piece, live.

## What it does

**The conductor**
- A progression of up to 16 chords (root, type, voicing, length), sent as CV (bass note and four
  chord voices) and MIDI, with a chord trigger.
- Sixteen **sections** (A–P) over the progression: runs of chords that repeat until the next is cued,
  each with its own drums and its own pattern chain entries.
- The **section playlist**: a chord lane (sections and chord runs, each from its own progression
  pattern) and a drum lane (drum chain entries) that play an arrangement by themselves, with repeats
  or HOLD, and live cues that fit into it.
- Key, chord colour (triads to ninths), chord jump and voicing, by hand or by modulation;
  progressions from the library, loaded from any chord.
- **Transpose** the whole progression, and a master **degree**: every chord heard as degree I–VII of
  a key, the tracks on that degree's mode (T4 SETUP, PERF page 2's F1 / F2 and the encoder, or by
  modulation).

**Tracks by role**
- **Arp:** an arpeggiator on the conductor's chord: mode, octaves, rate, gate (to legato), pattern,
  steps, chance.
- **Bass, Melody, Free:** step patterns that follow the chords (chord scale, home key, chord tones,
  the played bass note, or off), with spread, density and magnet, and a **pattern chain** of up to
  16 entries.
- **Drums, Lane, Drum Kit:** the drum section (below).
- **Mod:** an LFO, envelope, the progression or section position, or a CV input, on a CV output.

**The drums**

The drums are a section of their own, next to the harmony:
- **One kit, two outputs.** 16 patterns and 8 fills of eight voices (BD SNR CLP CHH OHH P1 P2 CYM),
  with accents and a chance per step. The **Drum Kit** track plays all of them over MIDI (pattern N
  plays kit N on the Performer Drums plug-in for the disting NT); the **drum machine** (Drums and
  Lane tracks) plays a voice per track on CV and gate.
- **A mixer** (T3 DRUMS): each voice's slot (the playing pattern, or another pattern's lane as a
  variation), chance and mute; the drums have their own swing.
- **The drum chain** (T4): an arrangement of patterns and bars, with **morphs** that crossfade one
  entry into the next.
- **Fills:** eight of them, from the library, captured from what played, or made from the playing
  pattern (ROLL, TOMS, BUILD, BREAK, HITS), each with its own chance; held on the PERF page.
- **In the song:** a section can bring its own drum pattern, and the playlist has a drum lane of
  chain entries that runs next to the chords.
- **Around it:** CAPTURE into a pattern or a fill, a drum library by style, modulation of every
  voice's chance, density, fill and morph, drum editing on a Launchpad, and a step editor with
  built-in drum sounds in the [Library Manager](https://radio32.github.io/Performer-Library-manager/).

**The library**
- Bass lines, melodies, drum patterns and progressions on the SD card, grouped in styles; browsed
  into patterns, chains and the conductor; edited patterns saved back.

**Performing and modulating**
- The **PERF** page: page 1 the selected track's tools by its role (punch, octave, rate, spread,
  latch, thin, fill in, reverse, fills) and its chain on F5, page 2 the song (fills, beat repeat, TRANSPOSE and DEGREE on
  the encoder); mutes and solo on page 1's S9–S16 (a tap latches, a hold is only while held).
- **CAPTURE**: what a track played, its chances settled, into a pattern or a fill, with undo.
- The **MOD matrix**: LFOs, envelopes, positions, CV inputs and outputs and MIDI, on the
  destinations of the selected track's role, the conductor, the song and the drum chain.
- A MIDI controller map for the Novation Launch Control XL 3 (made in the Library Manager): transpose,
  degree, sections, the playlist, the drum chain, track and drum mixes, the arp and the LFOs.
- **Launchpad** (every model from the S and Mini Mk1 on): sections, patterns, fills, mutes and the
  playlist on the pads, drum patterns edited and browsed from the library.

## The pages

Hold **PAGE** to see the map. The track keys open the main pages:

| Key | Page | | Key | Page |
|---|---|---|---|---|
| T1 | CONDUCT: the progression | | T5 | MOD: the matrix |
| T2 | TRACKS: roles and outputs | | T6 | PLAYLIST: the section playlist |
| T3 | DRUMS: the kit | | T7 | PROJECT: load, save, tempo |
| T4 | DRMCHAIN: the drum chain | | T8 | SYSTEM: calibration, MIDI, update |

The step keys open the selected track's pages: S1 STEPS, S2 SETTINGS, S3 LIBRARY, S4 FILLS (or
the chain), and S5 SECTIONS, S6 PLAYLIST, S7 TUNE, S8 MONITOR. **PATT** opens the track's chain
(on T1: the progression patterns); **PERF** the performance page. Hold PERF and click a parameter
to modulate it.

## Installing

1. Download `UPDATE.DAT` from the [latest release](https://github.com/Radio32/Conducting-Performer-docs/releases).
2. Copy it to the root of the module's SD card. The phrase libraries go in a `LIBRARY` folder next
   to it (`BASS.LIB`, `MELODY.LIB`, `DRUMS.LIB`, `PROGS.LIB`); without them the firmware runs, and
   the library pages say "NO LIBRARY ON SD CARD".
3. Hold the encoder while switching the module on: the bootloader installs the update.

It runs on PER|FORMER hardware with its standard bootloader. Projects saved by the original firmware
are not read.

## The phrase library

The libraries are made from MIDI files and aren't part of the download. The
[Library Manager](https://radio32.github.io/Performer-Library-manager/) (in the browser) previews,
sorts and edits the libraries on the card, edits drum patterns, makes drum kits for the Performer
Drums plug-in on the disting NT, and makes the controller map.

## Credits and licence

The Conducting Performer is by Kolbjørn Lyslo. It is built on the
[PER|FORMER firmware](https://github.com/westlicht/performer) by Simon Kallweit, whose drivers,
bootloader and framework it still uses; PER|FORMER is his eurorack sequencer. This is not an official
PER|FORMER firmware.

Released under the MIT licence: see [LICENSE](LICENSE). The firmware's source code is not public.
It uses libopencm3 and libusbhost (LGPL-3.0), FreeRTOS (GPL with the FreeRTOS exception), FatFs and
stb: each release lists them in `THIRD-PARTY-NOTICES.txt` and has a **relink kit** with their
source and the firmware's compiled code, so you can rebuild the firmware with your own versions of
those libraries.
