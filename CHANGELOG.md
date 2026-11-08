# Changelog

## Conducting Performer 1.13.0 (8 November 2026)

#### Improvements

- **PERF page 1 is laid out like page 2:** TOOLS (S1–S8; a drum track: FILL 1–8, the held fill's
  name) and TRACKS 1–8 on the same columns, the selected track inverted, the muted ones grey. The
  header shows the track, its role and its playing pattern.
- **F5 CHAIN on page 1:** a bass, melody or free track's pattern chain on / off; on a drum track the
  drum chain. Lit while it plays; with no chain entries yet it says so. (F5 no longer opens page 2:
  tapping PERF does.)

## Conducting Performer 1.12.0 (6 November 2026)

#### Improvements

- **New controller map functions** (XL3.MAP, made on the Library Manager's Controller page):
  - Conductor: TRANSPOSE (−24…+24) and DEGREE (Auto, I–VII).
  - Song: a section A–P next, the next section, the section playlist play / stop.
  - Tracks: all tracks on; an arp track's mode, octaves and gate.
  - Drums: a drum chain entry (the chain plays from it, starting if it was off).
- Saved maps work as before. The Library Manager's suggested layout puts transpose, degree, colour,
  jump, drum density, drum fill, swing and tempo on encoder row 1, the next section on PAGE ▲, the
  drum chain's next entry on PAGE ▼ and the playlist on FN2.

## Conducting Performer 1.11.0 (6 November 2026)

#### Improvements

- **TRANSPOSE runs −24…+24 semitones** (two octaves each way); SHIFT + turn moves it an octave, on T4
  SETUP and on PERF page 2.

## Conducting Performer 1.10.0 (6 November 2026)

#### Improvements

- **PERF page 2 is the song page:** FILL 1–8 and REPEAT on two rows, then TRANSPOSE and DEGREE.
  **F1 TRANSPOSE / F2 DEGREE** pick what the encoder turns (the one it turns is inverted). Page 1 is
  the selected track (its role in the header); its encoder no longer transposes.
- **DEGREE moves a bass on Chord tones too:** with a degree set, it walks the degree's scale (its
  notes 0, 1, 2, 3 are the mode's root, 2nd, 3rd, 4th); AUTO: the chord's tones as before.

#### Fixes

- **TRANSPOSE moves every follower by exactly its semitones.** The roots are kept near C as the
  progression has them, then moved: a G chord transposed −2 now goes down to F (it jumped up almost an
  octave), and +7 is a fifth up.

## Conducting Performer 1.9.0 (6 November 2026)

#### Improvements

- **DEGREE on its own key:** PERF page 2, hold **F1 DEGREE** and turn the encoder (AUTO, I–VII). Page
  2 shows TRANSPOSE and DEGREE; the encoder alone still turns TRANSPOSE.
- **DEGREE is a MOD destination** (Chord Degree, on the matrix's new CONDUCTOR 2 page; PERF + click on
  T4 SETUP's Degree row assigns it).

#### Removed

- **MORE on the steps page** (F4: retrigger, retrigger chance and condition): melodic tracks have
  GATE, LENGTH and NOTE. The sequencer no longer plays retriggers or step conditions; a project that
  had them plays those steps once, always. The project's FILL MODE has no Condition any more.
- **RATCHET on the PERF page** (S7 of a bass, melody or free track is empty now).

## Conducting Performer 1.8.0 (6 November 2026)

#### Improvements

- **TRANSPOSE** (T4 SETUP, under PATTERN): the whole progression moves by −11…+11 semitones, shown
  with the key it gives (e.g. +2 (D)). The **PERF page's encoder** turns it too (both pages).
- **DEGREE** (T4 SETUP): AUTO (each chord's own scale, as before), or I–VII: every chord is heard as
  that degree of a key, and the tracks on the chord's scale take that degree's mode from the chord
  root. A C major chord as IV: C Lydian (F#); as V: C Mixolydian (B♭); a minor chord as II: Dorian.

#### Fixes

- **A bass no longer jumps an octave or two when a chord's voicing changes.** An inversion picks the
  chord tone in the bass; the bass stays within −5…+6 semitones of C, as the roots always have
  (voicing +3 used to put the bass an octave up, −3 an octave down, and with the mod's voicing on
  top more). The arp, the conductor's CV and its MIDI chord start from the same bass.

## Conducting Performer 1.7.0 (30 October 2026)

#### Improvements

- **A new Launchpad controller** for the Launchpad S, Mini Mk1 and Mk2, Mk2, Mk3 / Mini Mk3 / X, Pro
  and Pro Mk3 (the original's SEQUENCE and PATTERN modes are gone). Top buttons: UP DOWN LEFT RIGHT,
  PERF, DRUMS, BROWSE, SHIFT (the module's SHIFT works too); UP held + DOWN: PLAY. Side buttons:
  select T1–T8 (dim ones flash with their gates).
  - **PERF:** sections A–P (cue), the selected track's patterns P1–P16 (on T1 CONDUCT: the progression
    patterns; SHIFT: at the next bar), the fills (held: played), the drum chain's entries 1–8, solo
    and mute T1–T8.
  - **PLAY:** the playlist's chord rows (rows 1–4) and drum rows (rows 5–8): press a row to play it
    next (stopped: play from it); UP + DOWN there again: play / stop.
  - **DRUMS:** the playing drum pattern, 4 lanes × 16 steps; UP/DOWN lanes 1–4 / 5–8, LEFT/RIGHT
    the bars (following the play position until then; both: following again). A fill pad held on
    PERF + DRUMS edits that fill. The module's S1 STEPS on a drum track and T3 DRUMS open it.
  - **BROWSE:** the drum library's patterns of a style on the pads (press: into the playing pattern,
    its style and name on the module; again: UNDO); LEFT/RIGHT the styles, UP/DOWN the next 64.
  - Red, green and amber on every model; the RGB models show the tracks' roles in colour.
- A connected Launchpad has the USB port to itself (the XL3 map no longer catches its buttons).

## Conducting Performer 1.6.0 (30 October 2026)

#### Improvements

- **PAGE + S5: SECTIONS, PAGE + S6: the PLAYLIST**, next to the track's pages on the step keys (PAGE +
  PATT and T6 still open them).
- **The PAGE map shows PERF + CLICK: MODULATE**: hold PERF and click a parameter for its MOD strip.

## Conducting Performer 1.5.0 (30 October 2026)

#### Improvements

- **PATT on T1: the progression patterns.** P1–P16 with their first chords; S1–S16 (or turn and
  click) play one (SHIFT: at the next bar); the one that plays is inverted. Before, only T1 F4 SETUP
  switched them.
- **T1 F3 SECTIONS.**
- **S4 on Arp, Bass, Melody, Free and Mod tracks** opens the track's PATTERN CHAIN (drum tracks: FILLS).
- **The section playlist:** SHIFT + turn moves the selected row; SHIFT + click plays it next (when
  the playing part ends); the title shows what the selected row plays (a section's chords); a line
  under each playing row shows how far into its pass it is; the lanes follow their playing rows;
  SHIFT + F4 locks the drum rows to the chord rows (drum row n plays as long as chord row n).
- **PERF:** the header shows 1/2 and 2/2, and F5 on page 1 opens page 2.
- **SHIFT shows the SHIFT functions** on FILLS (F2 UNDO, SHIFT + turn: chance or another variant),
  PERF (CAPTURE: UNDO, S9–S16: solo) and in the library browser (F1: the style before).
- **T7 PROJECT: Drum Swing** next to Swing (All) (it is on T3 SETUP too).

## Conducting Performer 1.4.0 (30 October 2026)

#### Improvements

- **VAR makes a new fill every time.** Each kind is a recipe with its choices rolled: where the fill
  starts, its rhythm, voices, accents, what closes it. Turning picks the kind, SHIFT + turn rolls
  another variant of it.
- **A fifth kind, HITS:** band hits, kick and snare together (a cymbal on the accented ones) on a
  syncopated figure (3-3-2, 3-3-3-3-4, the and of 3 and 4), with rests or the hats between them.
- **A CHANCE per fill** (50–100%): SHIFT + turn on a fill. At 100% the fill plays as written; lower,
  each of its hits plays only that often. Shown in the fill's box under 100%.

## Conducting Performer 1.3.0 (30 October 2026)

#### Improvements

- **VAR is a toggle** (PAGE + S4 FILLS): F5 VAR makes a fill from the playing pattern, and while it is
  on the encoder picks the kind (ROLL, TOMS, BUILD, BREAK), written into the fill as you turn (hold F1
  PLAY to hear it). VAR again, or a click, is done.
- **T1 F5 BROWSE loads from the selected chord:** the browser opens with the chord selected on T1
  marked, so progressions load from there (F2: from chord 1).
- **T6:** the selected lane's name is inverted, and the other lane says how to get to it (PREV / NEXT).

## Conducting Performer 1.2.0 (30 October 2026)

#### Improvements

- **T6 is the SECTION PLAYLIST.** It plays the arrangement, not patterns, in two lanes side by side:
  - the **chord lane**: SECT rows play a section (A–P), CHORD rows a run of chords (first–last), each
    from its progression pattern (P1–P16);
  - the **drum lane**: DRUM rows play drum chain entries (first–last); while it has rows it plays the
    drums (a section's DRUMS give way, the drum chain need not be on).
  Each row plays its repeats (1–16, or HOLD until a cue), then the next; at the end the lanes start
  over (END: LOOP) or their last rows play on (END: STOP, SHIFT + F2). A section cued on SECTIONS (or
  by a MOD route) while the playlist plays plays once, then the playlist carries on with its next row.
  F1 ADD (SHIFT: INSERT), F2 REMOVE, F3 DUPL (SHIFT: CLEAR the lane), F4 SECTIONS, F5 PLAY / STOP
  (SHIFT: from the selected rows); turn: the fields, click: edit, S1–S16: the field's value,
  PREV/NEXT: the lanes. The old song (pattern slots) is not carried over.
- **Sections: CHAINS.** FOLLOW, or the entry every pattern chain plays from when the section starts.
- **SECTIONS F2 CHORDS** shows the conductor page while it is held. **F4 PLAYLIST** goes to T6, and
  T6 **F4 SECTIONS** comes back.

## Conducting Performer 1.1.1 (28 October 2026)

#### Fixes

- **T1 showed the selected track's pattern number, not the conductor's.** The conductor page, its
  progression browser and SECTIONS now all show and edit the progression pattern that plays (switched
  on T1 F4 SETUP: PATTERN). The header on these pages shows PROG and that pattern (and the one that
  waits, after >).

## Conducting Performer 1.1.0 (28 October 2026)

#### Improvements

- **Progressions from a marked chord** (T1 F5 BROWSE): S1–S16, or a click, a turn and a click, mark
  the chord progressions load from. The chords before it stay; from it on the progression is written,
  as many of its chords as fit before chord 16 (a message says when some are left out). The browser
  shows the chords eight at a time with the marked one; F2 FROM goes back to chord 1.

## Conducting Performer 1.0.0 — master release (27 October 2026)

The first complete version of the Conducting Performer, a firmware for the PER|FORMER sequencer
built around a conductor: one chord progression that every track follows. It is the result of the
development builds 0.13 to 0.69. From here on, releases bring bug fixes (1.0.1, 1.0.2 ..) and small
improvements (1.1, 1.2 ..).

#### The conductor (T1)

- A progression of up to 16 chords, each with its root, type, voicing and length, played as CV
  (the bass note and four chord voices) and as a chord trigger.
- Sections A–P (PAGE + PATT): runs of chords that repeat until the next one is cued; MAIN plays
  the whole progression. Each section can bring its own drum pattern.
- Key, chord colour (triads to ninths), chord jump and voicing, by hand or by modulation.
- Progressions from the library, MIDI progressions with their colour voicings.

#### Tracks by role

- **Arp:** an arpeggiator on the conductor's chord: mode, octaves, rate, gate (up to legato),
  pattern, steps and chance.
- **Bass, Melody, Free:** step patterns that follow the chords (chord scale, home key, chord tones,
  bass note, or off), with spread, density and magnet, and a PATTERN CHAIN of up to 16 entries.
- **Drums, Lane, Drum Kit:** a CV drum machine with lanes, and an eight-voice MIDI drum kit for the
  Performer Drums plug-in, playing one store of kit patterns; the DRUM CHAIN with morphs between
  entries, eight fills, and a kit mixer.
- **Mod:** an LFO, envelope, the progression or section position, or a CV input on a CV output.

#### The library

- Bass lines, melodies, drum patterns and progressions on the SD card, grouped in styles, browsed
  on S1 and loaded into patterns, chains and the conductor; edited patterns saved back.

#### Performing

- The PERF page: tools for the selected track by its role (punch, octave, rate, spread, latch,
  thin, fill in, ratchet, reverse, fills, beat repeat), mutes and solos.
- CAPTURE: what a track played, chance and variation settled, into a pattern or a fill, with undo.
- The MOD matrix: LFOs, envelopes, the progression and section positions, CV inputs and outputs and
  MIDI on the destinations of the selected track's role, the conductor, the song and the drum chain.
- A MIDI controller map (XL3.MAP, made in the Library Manager).
