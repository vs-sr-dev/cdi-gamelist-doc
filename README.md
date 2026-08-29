# cdi-gamelist-doc

**Index of the Philips CD-i disc documentation** — 5 titles, one repository
each, plus the shared platform checklist they all feed into.

Green Book discs opened from the pre-file-system region up: sector layouts,
OS-9/68000 module validation, coding bytes, DYUV, real-time interleave and the
symbol tables that survived mastering. No repository here contains disc images
or game assets — only measurements and the code to reproduce them.

| | |
|---|---|
| **Shared platform findings** | [**cdi-platformnotes-doc**](https://github.com/vs-sr-dev/cdi-platformnotes-doc) — the canonical checklist all 5 discs feed into |
| **Disc-by-disc comparison** | [section 10, *Baselines*](https://github.com/vs-sr-dev/cdi-platformnotes-doc/blob/master/cdi-platform-notes.md#10-baselines-so-you-can-tell-signal-from-noise) — it lives there and is **not** copied here, so there is only ever one of it |

## The discs

Listed in the order they were documented. The **Saga** column is filled in where
the title belongs to a series that may one day earn its own index; it is empty
where it does not.

| Title | Year | Studio | Saga | What it is |
|---|---|---|---|---|
| [**Ultra CD-i Soccer**](https://github.com/vs-sr-dev/cdi-ultracdisoccer-doc) | 1997 | Krisalis / Philips Interactive Media |  | A Green Book disc 2.4 % full that compresses nothing, with 10 % of its file system shipped as empty files |
| [**Origami**](https://github.com/vs-sr-dev/cdi-origami-doc) | 1993 | EagleVision interactive productions |  | The opposite end of the format: a disc 98 % full in which 52 sectors out of 326,400 are the file system and the program |
| [**Link: The Faces of Evil**](https://github.com/vs-sr-dev/cdi-linkthefacesofevil-doc) | 1993 | Animation Magic / Philips Interactive Media | Zelda | The retail build still carries 325 C function names, handing over the architecture of a game whose source was never public |
| [**Merlin's Apprentice**](https://github.com/vs-sr-dev/cdi-merlinsapprentice-doc) | 1995 | Philips Interactive Media of America |  | Cliff Johnson's only CD-i game, pressed with the linker's symbol file still on it: 887 named symbols nobody references |
| [**The Apprentice**](https://github.com/vs-sr-dev/cdi-theapprentice-doc) | 1994 | The Vision Factory / Philips |  | The CD-i's best action game, and a CD-i Ready disc: the whole thing hides in the 69,150-sector pregap of track 1 |

## The write-ups

Each entry below is the write-up that used to sit in the
*Game and engine documentation* table of the [profile
README](https://github.com/vs-sr-dev), moved here **verbatim**. Nothing was
rewritten or summarised in the move: same prose, same numbers, same links. The
only change is that a `\|` written to escape a pipe inside a table cell is now
a plain `|`, because these are no longer table cells.

### [Ultra CD-i Soccer](https://github.com/vs-sr-dev/cdi-ultracdisoccer-doc)

*Ultra CD-i Soccer* (Krisalis / Philips Interactive Media, 1997) — a Green Book disc **2.4 % full that compresses nothing**, with **10 % of its file system shipped as empty files**: three abandoned localisations, palettes real and pictures never drawn. The executable asks for a **Sega logo** nobody pressed, and the studio put itself in the team database

### [Origami](https://github.com/vs-sr-dev/cdi-origami-doc)

*Origami* (EagleVision interactive productions, 1993) — the opposite end of the CD-i format: a disc **98 % full** in which **52 sectors out of 326,400** are the file system and the program. Catalogued `(En,Fr,De,Nl)`, it carries **five** narration languages — the fifth is Japanese — and stores every photograph twice, one per video standard, so 21.7 % of the pressing is video your player never reads

### [Link: The Faces of Evil](https://github.com/vs-sr-dev/cdi-linkthefacesofevil-doc)

*Link: The Faces of Evil* (Animation Magic / Philips Interactive Media, 1993) — the retail build still carries **325 C function names**, handing over the architecture of a game whose source was never public. **Half the 600 MB disc is deliberately empty**, eight stereo music channels run in parallel so switching tunes costs no seek, and each playfield ships two dozen compiled 68000 subroutines

### [Merlin's Apprentice](https://github.com/vs-sr-dev/cdi-merlinsapprentice-doc)

*Merlin's Apprentice* (Philips Interactive Media of America, 1995) — Cliff Johnson's only CD-i game, pressed with **the linker's symbol file still on it**: 19,752 bytes nobody references, holding **887 named symbols** that give up eight puzzle engines and all 27 puzzles by name, a cheat flag, and a streaming scheduler the error strings call the **Traffic Cop**. The **BOLT** asset container is mapped to the byte — 129 groups, 7,703 members, zero chain breaks — and its compressor turns out to manage 1.17:1

### [The Apprentice](https://github.com/vs-sr-dev/cdi-theapprentice-doc)

*The Apprentice* (The Vision Factory / Philips, 1994) — the CD-i's best action game, and a **CD-i Ready** disc: the whole thing hides in the **69,150-sector pregap of track 1**, so every ripper reads it as audio and hands it back scrambled. It ships the linker's symbol table (**521 named symbols**), a **68000 disassembler** switched on by a file in the player's NVRAM, and a default high-score table naming **twenty** people where the credits name three. The soundtrack is pressed twice — 22 Red Book tracks and 22 ADPCM channels, mapped one-to-one, 21 of 22 durations agreeing to a quarter-second — and **714 KB of the Philips bumper is byte-identical to Link's**

