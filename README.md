# Interactive fiction (IF) - Text Adventure cross platform porting.

Text adventures from the 8-bit era, preserved and ported to real hardware.

This project started as one thing and turned into three. All of it is
tied together by the same idea: take a real, classic game — not a
tribute, not a reimagining, the actual original game logic — and get it
running properly on hardware it was never built for.

## The story so far

It began with **Blake's 7 — The Oric Game**, a graphic adventure built on
a custom 6502 engine called OASIS. The plan was a straight port to the
NABU PC. The graphics side turned out to be the wall — translating the
Oric's display approach to the NABU's video hardware ground progress
down long before the game logic itself was ever really tested.

That raised the real question: how do you prove out a game's room flow,
puzzle chain, and pacing when the graphics layer is what's stuck? The
answer was to stop waiting on graphics and build a text-only layer first
— engine and puzzle logic locked down before a single pixel is drawn.

**Beatle Quest**, a Spectrum Quill adventure, became the proving ground.
Unlike the Oric game, it's a database-driven format — extractable,
replayable, testable. Building a Python runner for it, then a real
from-scratch Z80/CP/M engine, turned into the actual breakthrough: a
genuine, complete, playable NABU port, published in full.

That same approach went back into **Blake's 7** itself — not as a
graphics port this time, but as a careful text adaptation built directly
from the original Oric scripts, room data, and puzzle chain, with one
rule: the Oric game is the authority. All three episodes now run and
complete on real NABU hardware.

A third game, **Pyramid 2000** (the 1979 TRS-80 classic), followed the
same from-scratch path and is feature-complete too.

And then Beatle Quest kept going: the same core engine, re-adapted by
hand for six more real 8-bit and 16-bit machines, each one a genuine
native build reading the same shared game data.

None of this went in a straight line. That turned out to be fine.

## The games

### NABU / CP/M editions

The original target platform, and where all three games were first built
and proven.

| Game         | Status                                | How to run                                                                                                            |
|--------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Beatle Quest | 📦 Released                           | Get it from [nabu.ca](https://nabu.ca/cpm-software/262) or this repo's [Release](../../releases/tag/bq-nabu-v1.00.22) |
| Blake's 7    | 🧪 Feature-complete, not yet released | Real NABU PC / CP/M, confirmed hands-on                                                                               |
| Pyramid 2000 | 🧪 Feature-complete, not yet released | Real NABU PC / CP/M, confirmed hands-on                                                                               |

- *Beatle Quest* — a port of the 1985 Spectrum Quill adventure by Garry
  Marsh (Number 9 Software), and the game that actually got this whole
  project started — built first just so it could finally be played on
  the NABU.
- *Blake's 7* — a text adaptation of Chema Enguita's 2018 Oric graphic
  adventure, built directly from the original game's scripts and puzzle
  chain, all three episodes.
- *Pyramid 2000* — a from-scratch port of the 1979 TRS-80 classic
  (Radio Shack, Cat. No. 26-1905), all 11 treasures collectable for a
  full 220/220.

### Beatle Quest — other platforms

Beatle Quest didn't stop at NABU — the same game data now runs natively
on six more machines, each a genuine native build for its target.

| Platform              | Status         | Emulator tested | Hardware tested | How to run                                              |
|-----------------------|----------------|-----------------|-----------------|---------------------------------------------------------|
| Commodore 64          | ✅ Playable    | ✅ Yes          | ❓ Not yet      | Load `BEATLEQUEST.D64` in VICE or on real hardware      |
| Commander X16         | 🚧 In progress | ✅ Yes          | ❌ Known issue  | Load `BQ.PRG` in x16emu                                 |
| MSX (MSX-DOS 1)       | 🚧 In progress | ✅ Yes          | ❓ Not yet      | Boot `BQ.DSK` in openMSX or on real hardware            |
| Apple II (ProDOS)     | 🚧 In progress | ✅ Yes          | ❓ Not yet      | Boot `BQ_APPLE2.po` in AppleWin or on real hardware     |
| Amiga (AmigaOS)       | 🚧 In progress | ✅ Yes          | ❓ Not yet      | Run `BQ` from AmigaDOS in WinUAE or on real hardware    |
| TRS-80 Color Computer | ✅ Playable    | ✅ Yes          | ✅ Confirmed    | Boot `BEATLEQUEST.DSK` in VCC/XRoar or on real hardware |

Every platform above passes a full, automated, perfect-score playthrough
of the game's puzzle chain. Downloads are attached to the
[Releases](../../releases) page as they become available — not every
platform has a packaged release yet.

## Status key

- 📦 **Released** — publicly available now
- ✅ **Playable** — hands-on confirmed, start to finish
- 🧪 **Feature-complete, not yet released** — playable, awaiting a packaged release
- 🚧 **In progress** — engine work underway, not yet fully playable
- ⏳ **Planned** — not started yet
- ❓ **Not yet** — not yet tested on real hardware (works in emulator)
- ❌ **Known issue** — confirmed failing on real hardware, not yet fixed

## Article / further reading

- [Blake's 7 & Beatle Quest](https://www.amigaretro.com/projects/blakes-7-beatle-quest/)
- [Beatle Quest on real hardware](https://www.amigaretro.com/projects/beatle-quest-real-hardware/)
- [Six Machines, One Game](https://www.amigaretro.com/projects/six-machines-one-game/)

## Credits

- *Blake's 7* — original Oric game by Chema Enguita (2018)
- *Pyramid 2000* — original game, Radio Shack / Tandy (1979)
- *Beatle Quest* — original game by Garry Marsh / Number 9 Software (1985)
- NABU and multi-platform engine work: Intangybles
