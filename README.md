# Interactive fiction (IF) - Text Adventure cross platform porting.

Text adventures from the 8-bit era, preserved and ported to real hardware.

This project started as one thing and turned into three. All of it is tied together by the same idea: take a classic game - not a tribute, not a reimagining, the actual original game logic - and get it running properly on hardware it was never built for.

## The story so far

It began with **Blake's 7 - The Oric Game**, a graphic adventure built on a custom 6502 engine called OASIS. The plan was a straight port to the NABU PC. The graphics side turned out to be the wall - translating the Oric's display approach to the NABU's video hardware ground progress down long before the game logic itself was ever really tested.

That raised the question: how do you prove out a game's room flow, puzzle chain, and pacing when the graphics layer is what's stuck? The answer was to stop waiting on graphics and build a text-only layer first - engine and puzzle logic locked down before a single pixel is drawn.

**Beatle Quest**, a Spectrum Quill adventure, became the proving ground. Unlike the Oric game, it's a database-driven format - extractable, replayable, testable. Building a Python runner for it, then a Z80/CP/M engine, turned into the actual breakthrough: a complete, playable NABU port, published in full.

That same approach went back into **Blake's 7** itself - not as a graphics port this time, but as a careful text adaptation built directly from the original Oric scripts, room data, and puzzle chain, with one rule: the Oric game is the authority. All three episodes now run and complete, confirmed on physical NABU hardware.

A third game, **Pyramid 2000** (the 1979 TRS-80 classic), followed the same path and is out as a pre-release too.

And then Beatle Quest kept going: the same core engine, re-adapted by hand for seven more 8-bit and 16-bit machines, each one a native build reading the same shared game data. Pyramid 2000 followed the same route to five of those machines.

None of this went in a straight line. That turned out to be fine.

## The games

### NABU / CP/M editions

The original target platform, and where all three games were first built and proven.

| Game         | Status                                | How to run                                                                                                                          |
|--------------|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Beatle Quest | 📦 Released                           | Get it from [nabu.ca](https://nabu.ca/cpm-software/262) or this repo's [Release](../../releases/tag/bq-nabu-v1.00.22)               |
| Blake's 7    | 🧪 Engine complete, not feature-complete | Physical NABU PC / CP/M, confirmed hands-on                                                                                              |
| Pyramid 2000 | 📦 Pre-release RC2                    | Physical NABU PC / CP/M, confirmed hands-on. Get it from this repo's [Release](../../releases/tag/pyramid2000-nabu-v1.00.14-rc2)         |

- *Beatle Quest* - a port of the 1985 Spectrum Quill adventure by Garry Marsh (Number 9 Software), and the game that actually got this whole project started - built first just so it could finally be played on the NABU.
- *Blake's 7* - a text adaptation of Chema Enguita's 2018 Oric graphic adventure, built directly from the original game's scripts and puzzle chain, all three episodes.
- *Pyramid 2000* - a port of the 1979 TRS-80 classic (Radio Shack, Cat. No. 26-1905), all 11 treasures collectable for a full 220/220.

### Tools

- *UnQuill 0.9.0* - a rebuild of John Elliott's UnQuill for the z88dk CP/M toolchain, needed because the original 2013 build doesn't run on NABU CP/M. Disassembles, plays, and converts Quill adventure game snapshots. Get it from this repo's [Release](../../releases/tag/unquill-v0.9.0).

### Beatle Quest - other platforms

Beatle Quest didn't stop at NABU - the same game data now runs natively on seven more machines, each a native build for its target.

| Platform              | Status              | Emulator tested | Hardware tested | How to run                                              |
|------------------------|---------------------|------------------|------------------|----------------------------------------------------------|
| Commodore 64          | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Load `BEATLEQUEST.D64` in VICE or on physical hardware   |
| Commander X16         | 📦 Pre-release RC1  | ❌ No            | ❌ Known issue   | Load `BQ.PRG` in x16emu                                  |
| MSX (MSX-DOS 1)       | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Boot `BQ.DSK` in openMSX or on physical hardware         |
| Apple II (ProDOS)     | 📦 Pre-release RC1  | ✅ Yes           | ❓ Not yet       | Boot `BQ_APPLE2.po` in AppleWin or on physical hardware  |
| Amiga (AmigaOS)       | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Run `BQ` (or windowed `BQG`) from AmigaDOS in WinUAE or on physical hardware |
| ZX Spectrum Next      | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Boot `BQ.nex` in CSpect or on physical hardware          |
| TRS-80 Color Computer | 📦 Pre-release RC1  | ✅ Yes           | ✅ Confirmed     | Boot `BQ.DSK` in VCC/XRoar or on physical hardware       |

Every platform above except Commander X16 passes a full, automated, perfect-score playthrough of the game's puzzle chain, and each has a downloadable pre-release package (program, data, manual, and a disk image where one exists) on the [Releases](../../releases) page: the RC2 platforms (Commodore 64, MSX, Amiga, ZX Spectrum Next) carry input, word-wrap, and default-filename fixes found after RC1, and ZX Spectrum Next is a brand-new platform on this round; the rest are still on their first RC1 build. See each package's own `README.TXT` for exact status, and please report back what you find.

**Commander X16 is currently not working**, in the emulator or on real hardware - it was confirmed working before, but is not right now. Not recommended to try until this is sorted out.

### Pyramid 2000 - other platforms

The same `PYRAMID.P2K` game data, running natively on five more machines.

| Platform          | Status              | Emulator tested | Hardware tested | How to run                                                             |
|--------------------|---------------------|------------------|------------------|--------------------------------------------------------------------------|
| Commodore 64      | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Load `PYRAMID.D64` in VICE or on physical hardware                     |
| Apple II (ProDOS) | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Boot `PYRAMID_APPLE2.po` in AppleWin or on physical hardware           |
| MSX (MSX-DOS 1)   | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Boot `PYRAMID.DSK` in openMSX or on physical hardware                  |
| Amiga (AmigaOS)   | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Run `PYRAMID` (or windowed `PYRAMIDG`) from AmigaDOS in WinUAE or on physical hardware |
| ZX Spectrum Next  | 📦 Pre-release RC2  | ✅ Yes           | ❓ Not yet       | Boot `PYRAMID.nex` in CSpect or on physical hardware                   |

Commander X16 isn't included yet - it has a known crash-on-exit issue already open on the Beatle Quest X16 build, so a Pyramid 2000 port would likely hit the same problem. TRS-80 Color Computer isn't planned - an original 1982 CoCo release of Pyramid 2000 already exists and is this engine's own architectural reference.

## Status key

- 📦 **Released** - publicly available now
- 📦 **Pre-release RC1/RC2** - a public build out for external testing; not yet a stable/final release. RC2 supersedes RC1 for whichever platforms it was built for.
- ✅ **Playable** - hands-on confirmed, start to finish
- 🧪 **Engine complete, not feature-complete** - runs and plays start to finish, but there's still content/gameplay work left before it's ready to release
- 🚧 **In progress** - engine work underway, not yet fully playable
- ⏳ **Planned** - not started yet
- ❓ **Not yet** - not yet tested on real hardware (works in emulator)
- ❌ **Known issue** - confirmed failing on real hardware, not yet fixed

## Article / further reading

- [Blake's 7 & Beatle Quest](https://www.amigaretro.com/projects/blakes-7-beatle-quest/)
- [Beatle Quest on real hardware](https://www.amigaretro.com/projects/beatle-quest-real-hardware/)
- [Six Machines, One Game](https://www.amigaretro.com/projects/six-machines-one-game/)

## Credits

- *Blake's 7* - original Oric game by Chema Enguita (2018)
- *Pyramid 2000* - original game, Radio Shack / Tandy (1979)
- *Beatle Quest* - original game by Garry Marsh / Number 9 Software (1985)
- *UnQuill* - original tool by John Elliott (1996-2011)
- NABU and multi-platform engine work: Intangybles
