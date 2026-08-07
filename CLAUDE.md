# Reaper_Scripts — manual

A collection of small, standalone JSFX effects and ReaScripts — each one
a single-purpose utility, not a full tool with its own repo (those live
separately: MidiCloud, ReaSamp, MidiLog, etc., each in their own
`~/Downloads/<Name>` repo with a direct GitHub remote). If something
here grows past single-script weight — gains a companion file, its own
manual, ongoing feature work — it graduates out into its own repo
rather than staying here (MidiLog did exactly that, 7 Aug 2026).

## JSFX

**MIDI CC+ Remapper** — remaps MIDI expression messages into different
CC numbers, channels, and value ranges. Four independent remap
sections, each with its own input/output scaling: CC → CC (with an
input channel filter), Polyphonic Aftertouch → CC, Channel Pressure →
CC, and Pitchbend → CC (14-bit input scaled down to a 7-bit CC value).
Useful for adapting a controller's expression output to whatever a
downstream instrument actually expects.

**MPE channel Remapper** — compresses an MPE zone's note channels down
to a smaller range. Channel 1 (the MPE global/master channel) always
passes through untouched; channels 2-16 get remapped based on a
configurable channel count (1-15), for feeding a wide MPE zone into
something that only listens on fewer channels.

**Randomize MIDI Channel for Notes** — scatters incoming note MIDI
across a channel range (configurable min/max, 1-16) using one of three
assignment strategies: Cyclic, Swing, or Random (seeded). This is the
direct precedent for MidiCloud's At Will channel mode (7 Aug 2026) —
same idea (channel diversification for multi-timbral triggering, not
expression isolation), applied here to live MIDI input generally rather
than a captured buffer.

**MPE Scaler** — reshapes MPE expression data (Note-On Velocity,
Channel Pressure, CC74 Brightness, Pitch Bend) through independent
per-parameter response curves (Linear/Exponential/Logarithmic/S-curve),
each with its own amount/scale/offset and, for pitch bend, a
configurable dead zone. Includes a live scrolling event log (`@gfx`)
showing the last ~90 messages across three columns, color-coded by
parameter type, with old→new values and inter-event timing — useful
for seeing exactly what a curve is doing to real incoming gestures, not
just guessing from the knob position.

**test** — empty placeholder, not a real script.

## Lua

**test** — empty placeholder, not a real script.
