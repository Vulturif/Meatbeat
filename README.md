# Meatbeat

A local Windows pacer — a metronome that runs a *routine* instead of a fixed
tempo. 18+.

Meatbeat plays a sample-accurate click (20–300 BPM) and walks it through tempo
segments — hold, ramp, pulse, pause, or a seeded random drift — while surfacing
timed prompts and drawing a weighted outcome at the end. Build your own routines
in the editor, save them as `.mbr` files, and share a run exactly by its seed.

## What it does

- **Sample-accurate beat.** One audio stream; every click is written at its
  exact sample position in the callback, so the tempo never drifts against the
  wall clock. The on-screen meter reads the same sample clock.
- **Routines.** A routine is a list of tempo segments plus a pool of commands
  (fired on a cadence, with weights and cooldowns) and a pool of outcomes drawn
  at the end. Everything is seeded, so the same seed replays the same run.
- **Spoken prompts.** Commands and the outcome can be read aloud by a Windows
  voice — pick the voice, or turn speech off.
- **Panic key.** <kbd>Esc</kbd> while focused, or <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>
  from anywhere, instantly cuts the sound and the speech.
- **Hard time cap.** A safety ceiling that force-ends any run, however long the
  routine is.

Nothing you make leaves your machine. Opt-in usage stats (off by default) count
only which features get used — never your routines, commands or outcomes.

## Running from source

```
python -m venv .venv
.venv\Scripts\pip install -r requirements.txt
.venv\Scripts\python main.py
```

Needs Python 3.11+ and a working audio output. Speech uses the Windows voices
already installed on the system.

## Part of the Vulturif family

Meatbeat shares the [vulturif-kit](https://github.com/Vulturif/vulturif-kit)
machinery (signed self-update, opt-in stats, feedback, supporter keys) with the
other Vulturif apps and is distributed through
[vulturif.com](https://vulturif.com/). A supporter key unlocks early access to
new versions and works across all of them; nothing is ever switched off when a
key lapses — you simply get the public releases again.
