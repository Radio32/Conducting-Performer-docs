# Conducting Performer — Quick Reference (v1.11.0)

The controls of firmware 1.11.0 on one page. What changed in each release: [CHANGELOG](../CHANGELOG.md).

## The big picture

The conductor's chord leads every harmony track; the drum kit's patterns lead the drums. Sections pick which chords play, and can pick the drums too.

```
 CONDUCTOR (16 chords) ──▶ SECTIONS A–P ──▶ SECTION PLAYLIST (chord lane)
        │ the chord that sounds
        ▼
 Arp · Bass · Melody · Free · Mod tracks follow it

 DRUM KIT (16 patterns + 8 fills) ──▶ DRUM CHAIN ──▶ SECTION PLAYLIST (drum lane)
        │ the pattern that plays
        ▼
 Drum Kit track (MIDI) · Drums + Lanes tracks (CV and gate)
```

Everything below is in the order you would set up a song: chords, sections, tracks, drums, then performing and modulating.

## The PAGE map

Hold PAGE and press a button to open a page; holding PAGE alone shows this map on the screen. The top row is the music and the project, the step row is the selected track.

| PAGE + | Page | What it is for |
| --- | --- | --- |
| T1 | CONDUCTOR | The chord progression (16 chords), chord pads, setup, progression library |
| T2 | TRACKS | Each track's role and outputs |
| T3 | DRUMS | The drum voices as a mixer: slot, chance, mute; drum setup |
| T4 | DRUM CHAIN | The drums' chain of patterns, with morph |
| T5 | MOD | The modulation matrix: sources × destinations |
| T6 | PLAYLIST | The section playlist: sections and chords (chord lane), drum chain entries (drum lane), with repeats |
| T7 | PROJECT | Tempo, swing (all), time signature, launch, fill mode; load and save |
| T8 | SYSTEM | Calibration, MIDI ports, utilities, firmware update |
| S1 | STEPS | The selected track's steps (the arp: its setup) |
| S2 | SETTINGS | The selected track's settings (by role) |
| S3 | LIBRARY | Bass and melody phrases (other tracks: a message) |
| S4 | FILLS | The drums' eight fills (drum tracks); on the other roles the track's PATTERN CHAIN |
| S5 | SECTIONS | The sections A–P (as PAGE + PATT, T1 F3) |
| S6 | PLAYLIST | The section playlist (as T6) |
| S7 | TUNE | Steady voltages for tuning and calibrating; F5 PULSE opens the gates every 0.5–5 s |
| S8 | MONITOR | CV in and out, MIDI, stats |
| PREV | OVERVIEW | Home: the whole project at a glance |
| CLOCK | CLOCK SETUP | Clock source, divisors, MIDI and USB clock |
| PATT | PATTERN CHAIN | The selected track's chain (drum tracks: the DRUM CHAIN); SECTIONS with PAGE + PATT |
| PLAY | — | Record on and off |

**Without PAGE**

| Key | Does |
| --- | --- |
| PLAY | Play and stop. SHIFT + PLAY: restart or pause (Clock Setup › Shift Mode) |
| PATT (tap) | The selected track's PATTERN CHAIN (tap again: back). PAGE + PATT: SECTIONS |
| PERF (tap) | The PERFORM page (tap again: page 2, again: back) |
| PERF (hold) + click a parameter | Its modulation strip (see Modulation) |
| CLOCK | Held: the tempo page. Turn: tempo (SHIFT ×10, pressed: 0.1). PLAY taps the tempo, PREV/NEXT nudge it, PERF: the shared swing |
| T1–T8 | Select a track (on most pages) |
| SHIFT + PAGE | The page's menu (Project: INIT, LOAD, SAVE, SAVE AS) |
| Encoder | Turn: move or change. Click: start or end editing |

## Conductor (PAGE + T1)

The conductor plays a progression of up to 16 chords; the tracks that follow the harmony play over the chord that sounds. Four chords a page (PREV/NEXT), each with KEY, TYPE, VOICING and LENGTH.

**Chords view**

| Control | Does |
| --- | --- |
| Turn | Move the selection; click, then turn: edit it |
| SHIFT + turn on KEY | The root around the circle of fifths |
| S1–S16 | Pick a chord's parameter (SHIFT: add it to the selection, edit several at once) |
| LENGTH | A beat per turn, SHIFT a bar; 0 switches the chord off |
| F1 PADS | The chord pads |
| F2 FOLLOW | The page follows the playing chord |
| F3 SECTIONS | The sections (also PAGE + PATT) |
| PATT | The progression patterns P1–P16: S1–S16 or turn + click plays one (SHIFT: at the next bar); F5 or PATT: back |
| F4 SETUP | Pattern, transpose (−24…+24, SHIFT: an octave a turn; with the key it gives), degree (Auto, I–VII), chord length, colour (triads … ninths), jump chance, MIDI channel and out |
| F5 BROWSE | The progression library (style, undo, P-write). It opens with T1's selected chord marked and loads from the marked chord: S1–S16, or click, turn, click. The chords before it stay; the ones past chord 16 are left out. F2 FROM: back to chord 1 |
| SHIFT + F1–F4 | INSERT, DELETE, DUPL, RANDOM progression |

Editing the playing chord's key, type or voicing sounds from the next 1/16; stopped, an edit plays the chord briefly on MIDI.

TRANSPOSE moves the whole progression, and every following track by exactly that many semitones. DEGREE hears every chord as that degree of a key, and the tracks on the chord's scale take that degree's mode from the chord root: C major as IV plays C Lydian (F♯), as V C Mixolydian (B♭); a bass on Chord tones walks that scale too. Auto keeps each chord's own scale and tones. A chord's voicing picks the tone in the bass; the bass keeps its register.

**Pads view (F1)**

| Control | Does |
| --- | --- |
| S1–S16 | Play a chord of the key (it holds; the progression waits) |
| Encoder | Turn: the key around the circle of fifths (SHIFT + turn: the mode) |
| F1 CHORDS | Back to the chords |
| F2–F5 | TRIAD, 7TH, SUS2, SUS4 |
| Record on (PAGE + PLAY) | Each pad played fills the next chord |

## Sections (PAGE + PATT)

A section is a run of chords that repeats until you pick another; the picked section starts when the playing one has played its last chord. Sixteen sections, A to P, two rows of four a page (PREV/NEXT).

| Field | Values |
| --- | --- |
| START | AUTO (where the section before ends; shown as a plain number) or a chord (“@3”) |
| LENGTH | 1–16 chords (“x3”) |
| DRUMS | FOLLOW (“D-”: the drums play on as they do) or pattern 1–16 (“D5”: the Drum Chain waits) |

| Control | Does |
| --- | --- |
| S1–S16 | That section next (blinks while it waits); stopped: the section to start with |
| Turn / click | Move between the fields / edit one |
| F1 MAIN | The main progression after this section |
| F2 CHORDS | Held: the conductor page at the section's first chord (let go: back) |
| F4 PLAYLIST | T6 PLAYLIST |

Each section also has **CHAINS** (`C-` or `C1`–`C16`): FOLLOW, or the entry every pattern chain plays from when the section starts.

## Section playlist (T6)

Two lanes side by side; each row plays its repeats, then the next one.

- **Chord lane:** SECT rows play a section (A–P), CHRD rows play chords first–last. Each row has repeats (1–16, or HOLD until a cue) and a progression pattern (P1–P16).
- **Drum lane:** DRUM rows play drum chain entries first–last, with repeats. While it has rows, the drum lane plays the drums: a section's DRUMS give way, and the drum chain's PLAY need not be on.
- **At the end:** the lanes start over (END: LOOP), or their last rows play on (END: STOP).
- **A cue** on SECTIONS (or from a MOD route) while the playlist plays: that section plays once, then the playlist carries on with its next row.

| Control | Does |
| --- | --- |
| Turn / click | Move between the fields (SHIFT: the row moves up or down) / edit one (SHIFT + click: this row next, while it plays) |
| S1–S16 | The field's value: section, chord, entry, repeats, pattern |
| PREV / NEXT | The chord lane / the drum lane |
| F1 ADD | A row after the selected one (SHIFT: INSERT before it) |
| F2 REMOVE | Remove the row (SHIFT: END LOOP or STOP) |
| F3 DUPL | Duplicate the row (SHIFT: CLEAR the lane) |
| F4 SECTIONS | Back to SECTIONS (SHIFT: the drum rows LOCKED to the chord rows, or FREE) |
| F5 PLAY / STOP | Play from the top (SHIFT: from the selected rows) |

The playing section's letter is inverted, with a progress bar under it.

## Tracks

Each of the eight tracks has a role (PAGE + T2: F1 ROLES, F2 OUTPUTS, F5 COMMIT); the role decides what S1, S2 and S3 show.

| Role | Follows the harmony | S1 STEPS | S3 LIBRARY |
| --- | --- | --- | --- |
| Bass | The chord's bass and chord tones | Steps (F5 BROWSE: phrases) | Bass phrases |
| Melody | Its FOLLOW: chord scale, home key or chord tones | Steps (F5 BROWSE: phrases) | Melody phrases |
| Arp | The chord, live | The arp setup: mode, octaves, rate, gate, pattern, steps, chance | — |
| Free | Only when FOLLOW is set | Steps | — |
| Drums (+ Lanes) | No: a drum voice per track on CV and gate | The voice's steps (see Drums) | A message (patterns: T4 DRUM CHAIN) |
| Drum Kit | No: all eight voices over MIDI | The voice's steps (see Drums) | A message (patterns: T4 DRUM CHAIN) |
| Mod | No: an LFO, envelope, song or CV in on its CV out | The source's setup | — |

**S1 STEPS (bass, melody, free):** F1 GATE (gate, probability, offset, slide), F2 LENGTH (length, variation), F3 NOTE (note, variation), F5 BROWSE (or S3). In the browser: F1 STYLE, F3 UNDO, F4 WRITE (a copy into the next pattern), F5 STEPS. SHIFT + F5 on S1: SAVE, the edited pattern over the library phrase it came from (a chain entry's).

**S2 SETTINGS**

| Role | Rows |
| --- | --- |
| Bass, Melody, Free | Follow (Chord scale, Home key, Chord tones, Bass note, Off), Octave, Length, Speed, Swing (all), Spread, MIDI Channel, MIDI Out, Slide Time, Density, Magnet |
| Arp | Octave, Swing (all), Spread, MIDI Channel, MIDI Out |
| Drums, Lane | Length, Speed, MIDI Channel, MIDI Out, MIDI Note, Density, Magnet |
| Drum Kit | MIDI Channel, MIDI Out, Length, Speed, Density, Magnet, Velocity, Accent, a note per voice |
| Mod | Source, Level, Offset, Slew |

SWING (ALL) on arp, bass, melody and free is one shared swing; the drums have their own, set on T3 SETUP. FOLLOW on bass: Chord tones counts the chord's notes (root, third, fifth); Bass note plays them over the bass as played. On melody and free, Bass note plays the chord's scale from the bass note. Spread (Off, 1–8) moves every note away from the chord's centre note: its distance in steps (arp, bass: the chord's notes; melody, free: the chord's scale) times 1 + spread; outside C1–B5 a note wraps round five octaves. It is a MOD destination (PITCH and ARP 2).

## Drums

One drum store, the kit: 16 patterns + 8 fills, eight voices each (BD SNR CLP CHH OHH P1 P2 CYM). The Drum Kit track plays all voices over MIDI; the drum machine (role Drums + Lanes) plays a voice per track on CV and gate. Both play the same kit patterns.

**S1 STEPS on a drum track:** F1 GATE (gate, probability), F2 ACCENT, F3 MUTE the voice, F4 VOICE, F5 SAVE (the edited pattern over the library pattern it came from). Turning with no step held picks the voice.

**T3 DRUMS (the mixer)**

| Control | Does |
| --- | --- |
| Per voice | SLOT (Follow, or pattern 1–16: that pattern's lane, a variation), CHANCE, mute |
| S1–S8 | Mute a voice |
| F1 MUTE, F2 FOLLOW | Mute; the voice back to the playing pattern (SHIFT: every voice) |
| F4 LANE | The voice's steps on S1 |
| F5 SETUP | Drum swing, length, speed, accent CV, velocity, accent velocity (F5 BACK) |

**T4 DRUM** **CHAIN** (only on PAGE + T4): entry n plays pattern n. Four entries a page; S1–S16 pick one.

| Control | Does |
| --- | --- |
| PATTERN | Turn: browse the drum library into the entry |
| BARS | 1/4 bar to 64 bars (the pattern loops inside) |
| MORPH | Click: F1 START, F2 LENGTH, F3 BACK, F5 DONE — crossfade into the next entry |
| “+ ADD” | Click: a new entry |
| F1 PLAY | The drum tracks follow the list (lit while on) |
| F2 FOLLOW, F3 EDIT | The page follows; the entry's pattern on S1 |
| F4 WRITE, F5 VOICES | The entry's pattern into the next one (SAVE is on S1, F5); T3 |
| SHIFT + F1–F3 | INSERT, DELETE, DUPL |

Jumps to another entry (Next Entry, matrix, controller) happen at the LAUNCH timing and keep their place in the bar.

**PAGE + S4 FILLS:** S1–S8 or turn: pick a fill. Click: browse the drum library into it (turn; an empty fill starts at the style “Fill”; SHIFT + turn: the next style), click again: done. F1 PLAY (held), F2 CAPTURE (what the drums played, as heard; SHIFT: undo), F3 CLEAR, F4 STYLE (back to the first fill), F5 VAR (a fill from the playing pattern, a new variant every time; while VAR is on, turn: the kind (ROLL, TOMS, BUILD, BREAK, HITS), SHIFT + turn: another variant; VAR again or a click: done). SHIFT + turn on a fill: its CHANCE, 50–100% (fewer of its hits).

## Perform (PERF)

Tap PERF for page 1, tap again for page 2, tap again to go back. On page 1, T1–T8 select the track the tools act on, and S9–S16 mute T1–T8 (SHIFT: solo). Held tools let go when you leave the page; LATCH stays on. Page 2 is the song: F1 TRANSPOSE and F2 DEGREE pick what the encoder turns.

**Page 1, S1–S8: the selected track's tools**

| Role | S1 | S2 | S3 | S4 | S5 | S6 | S7 | S8 | F-keys |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Arp | RUN | OCT+ | OCT− | ½ rate | ×2 rate | SPREAD +1 | LATCH (toggle) | MODE▸ (press) | F1 PUNCH (held), F2 CAPTURE |
| Bass, Melody, Free | RUN | OCT+ | OCT− | THIN | FILL IN | SPREAD +1 | — | REVERSE | F1 ◂PATT, F2 PATT▸, F3 PUNCH (held), F4 CAPTURE |
| Drums | fill 1 | fill 2 | fill 3 | fill 4 | fill 5 | fill 6 | fill 7 | fill 8 | F4 CAPTURE |

All tools are held except RUN, LATCH and MODE▸. RUN mutes and unmutes the track; it is grey while muted, ready for a punch in. PATT changes at the launch timing.

**CAPTURE** keeps what you heard (chance, variation and density settled) in a pattern. A tap: the next empty pattern. Held + S1–S16: that pattern. Held + turn: the length (the pattern's own, or 1–4 bars, lined up to the bar). SHIFT + CAPTURE undoes the last capture. It works after stopping too (a new start clears what it keeps). Bass, melody and free capture into their own patterns; the drums (F4) into a kit pattern. On an arp, CAPTURE starts a take into another track: the one picked with CAPTURE held + T1–T8 (bass, melody or free, remembered per arp), else the first Melody track to the arp's right: a running arp is recorded on every pass, a muted one only while PUNCH is held (the first punch sets 1, 2, 3 or 4 bars). Each pass or punch overwrites the steps it covers; a second tap keeps the take. **PUNCH** silences a running track, or lets a muted one be heard, from the next 1/16 while held.

**Page 2**

| Keys | What they do |
| --- | --- |
| S1–S8 (held) | The eight fills, from the next step |
| S9–S16 (held) | Beat repeat on every track: 1/4, 1/8, 1/16, 1/32, then triplets |
| F1 TRANSPOSE / F2 DEGREE | What the encoder turns: the conductor's TRANSPOSE (−24…+24, SHIFT: an octave) or DEGREE (Auto, I–VII); the one it turns is inverted |
| T1–T8 | Mute (SHIFT: solo) |
| F5 UNMUTE | Every track on |

## Modulation and the controller

**PAGE + T5 MOD:** sources down the side, four a page (F1: LFO 1–4 · CV IN 1–4 · ENV 1–2, PROG POS, SECTION POS · CV OUT 1–4 · CV OUT 5–8 · MIDI); destinations across, six a page. PREV/NEXT: the selected track's pages (by its role), then the global ones. The title says whose: "T3 ARP: ARP 1". T1–T8 jump to that track's first page. A cell is a route; its number is the depth. When a track's role changes, its routes to destinations the new role lacks are removed ("2 ROUTES REMOVED"); F3 TRACKS only takes tracks whose role has the destination.

| Role / page | Columns |
| --- | --- |
| **Arp:** ARP 1 | Rate, Mode, Octaves, Gate (up to Legato), Pattern, Chance |
| **Arp:** ARP 2 | Steps, Octave, Spread, Transpose, Slide |
| **Bass, Melody, Free:** PITCH | Octave, Transpose, Note probability, Spread, Slide |
| **Bass, Melody, Free:** RHYTHM | Probability, Length, Rotate, Density, Magnet |
| **Bass, Melody, Free:** PATTERN | Chain Entry, Chain Next, First Step, Last Step, Run Mode, Speed |
| **Drums, Lane, Kit:** DRUMS | Probability, Density, Magnet, Rotate, Voice Chance (a lane's voice) |
| **Kit:** KIT 1 / KIT 2 | Each voice's chance: BD, SNR, CLP, CHH, OHH, P1 / P2, CYM |
| **Mod:** MOD | Level, Offset, Slew, Rate, Shape, Phase (its LFO; an envelope: Rate = attack + decay, Shape = hold) |
| CONDUCTOR (global) | Key, Voicing, Colour, Jump, Next Chord, Chord Select |
| CONDUCTOR 2 (global) | Degree |
| SONG (global) | Section, Next Section, Tempo, Swing, Fill (every track), Fill Amount |
| DRUM CHAIN (global) | Entry, Next Entry, Morph, Morph Length, Drum Density, Drum Fill |

| Control | Does |
| --- | --- |
| Turn (SHIFT: up/down) / click | Move / edit the depth (5%, SHIFT or held: 1%) |
| F1 | The source page |
| F2 SETUP | The LFO's or envelope's settings (free LFO rates 0.01–60 Hz) |
| F3 TRACKS | T1–T8 share the cell's route |
| F4 DETAIL | The route: offset, input range, MIDI (SHIFT + F4: every route) |
| F5 CLEAR | Remove the route |

**PERF held + click a parameter** on any page: that parameter's matrix column on a strip at the bottom. F1–F4 pick a source, turn: its depth, PREV/NEXT: the source page, T1–T8: the track, F5 MATRIX. Turn a knob on a MIDI controller while the strip is open and it learns that CC.

**Mod track role:** an LFO, envelope, the progression or section position or a CV input on the track's own CV output (S1: the source's setup, S2: level, offset, slew).

**Controller map (XL3.MAP on the SD card, made in the Library Manager's Controller page):**

| Controls | Default |
| --- | --- |
| Encoders row 1 | Swing, tempo, chord jump, chord colour, drum density, drum fill amount, LFO 1 and 2 rate |
| Encoders row 2 | Octave of T1–T8 |
| Encoders row 3 | Chance of the eight drum voices |
| Faders 1–8 | Density of T1–T8 |
| Buttons row 1 / row 2 | Mute T1–T8 / mute the drum voices |
| PAGE UP / PAGE DOWN | Drum Chain next entry / next chord |
| TRACK ◀ ▶ | The previous / next track |
| FN1 / FN2 | Capture / Drum Chain on-off |
| PLAY / REC | Play / record |

Also available: drum swing, fills (hold), beat repeat (hold), voice slots, LFO shape and phase, solo, select, tap tempo. SYSTEM › UTILS reloads the map.

## Song, project and the rest

| Page | Controls |
| --- | --- |
| PATT: PATTERN CHAIN | A bass, melody or free track's chain (the role in the header, e.g. BASS CHAIN T2): entry n plays the track's pattern n for its BARS (¼–64, looping inside), loaded from the library (turn PATTERN); the chain loops, each on its own. S1–S16 pick an entry, click + ADD for a new one. F1 PLAY, F2 FOLLOW, F3 EDIT (on S1), F4 WRITE; SHIFT: INSERT, DELETE, DUPL |
| T6 PLAYLIST | Entries of patterns (and the section each plays, “A”), N = bars. F1 CHAIN, F2 ADD (SHIFT: INSERT), F3 REMOVE, F4 DUPL, F5 PLAY / STOP |
| T7 PROJECT | Name, Tempo, Swing (all), Time Signature, Launch, Fill Mode. MIDI is set up on T8 SYSTEM. SHIFT + PAGE: INIT, LOAD, SAVE, SAVE AS |
| T8 SYSTEM | F1 CAL (CV calibration), F2 MIDI (TX and RX ports, SysEx), F4 UTILS (reload the controller map …), F5 UPDATE |
| PAGE + CLOCK | Mode, Shift Mode, input divisor and mode, output divisor, swing, pulse and mode, MIDI and USB clock in and out |
| S7 TUNE | F1 TUNER (a reference note), F2 CALIBRATE (1V / 3V on F3), F4 GATES; S1–S8 pick the outputs |
| S8 MONITOR | F1 CV IN, F2 CV OUT, F3 MIDI, F4 STATS |
| PAGE + PREV: OVERVIEW | The whole project at a glance: the chord, the tracks, where the song is |

Projects saved before v48 are not read.

## Launchpad

Every model from the Launchpad S and Mini Mk1 on. Green: plays / on. Amber: waits or cued. Red: muted. Dim: has something. The RGB models show the tracks' roles in colour.

| Button | Does |
| --- | --- |
| Top 1–4 (▲ ▼ ◀ ▶) | Move within the view. ▲ held + ▼: PLAY (there again: play / stop the playlist) |
| Top 5 PERF | The performance view |
| Top 6 DRUMS | Drum pattern editing (a fill pad held on PERF + DRUMS: that fill; DRUMS again: the playing pattern) |
| Top 7 BROWSE | The drum library |
| Top 8 SHIFT | As the module's SHIFT (which works too) |
| Side buttons | Select T1–T8 (dim ones flash with their gates) |

| View | Pads |
| --- | --- |
| PERF | Rows 1–2: sections A–P (cue). Rows 3–4: the selected track's P1–P16 (on T1 CONDUCT: the progression patterns; SHIFT: at the next bar). Row 5: fills (held: played). Row 6: drum chain entries 1–8. Row 7: solo (again: all on). Row 8: mute |
| PLAY | Rows 1–4: chord lane rows 1–32. Rows 5–8: drum lane rows 1–32. Press: that row next (stopped: play from it) |
| DRUMS | 4 lanes × 16 steps (two rows a lane): press a step on or off. ▲ ▼ lanes 1–4 / 5–8, ◀ ▶ the bars (the view follows the play position until then; both: following again). Opens by itself on the module's S1 STEPS on a drum track and T3 DRUMS |
| BROWSE | A style's patterns: press one, it plays in the drums' pattern (its style and name on the module); press it again: UNDO. ◀ ▶ the styles, ▲ ▼ the next 64 |

