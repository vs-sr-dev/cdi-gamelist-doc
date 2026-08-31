# cdi-gamelist-doc

**Index of the Philips CD-i disc documentation** — 8 titles, one repository
each, plus the shared platform checklist they all feed into.

Green Book discs opened from the pre-file-system region up: sector layouts,
OS-9/68000 module validation, coding bytes, DYUV, real-time interleave and the
symbol tables that survived mastering. No repository here contains disc images
or game assets — only measurements and the code to reproduce them.

| | |
|---|---|
| **Shared platform findings** | [**cdi-platformnotes-doc**](https://github.com/vs-sr-dev/cdi-platformnotes-doc) — the canonical checklist all 8 discs feed into |
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
| [**Laser Lords**](https://github.com/vs-sr-dev/cdi-laserlords-doc) | 1992 * | Spinnaker Software Corp. and American Interactive Media, Inc. ** |  | The oldest CD-i disc measured here, and the one that moves the shared head-region recording back a year: ten jukebox streams carrying 6 h 34 m of speech |
| [**A Visit to Sesame Street — Letters**](https://github.com/vs-sr-dev/cdi-avisittosesamestreetletters-doc) | 1991 \*\*\* | American Interactive Media \*\*\*\* |  | The oldest disc measured here: 13,138 DYUV frames of alphabet cartoons decoded at 172 × 108, and a publisher bumper byte-identical to a disc eleven months younger |
| [**Burn:Cycle**](https://github.com/vs-sr-dev/cdi-burncycle-doc) | 1995 \*\*\*\*\* | Trip Media and Philips Media \*\*\*\*\*\* |  \*\*\*\*\*\*\* | A film with a program inside it: 7 directory entries, 99.23 % of the volume in one real-time file, a 69-minute RL7 picture at 384 × 240 and 12.5 fps, and 77:49 of ADPCM the pressing tags as *video* |

\* **Laser Lords, Year.** The volume descriptor's creation field at offset 813
reads `1992083119164000` and its modification field at 830 reads
`1992090914254400`, so the volume was laid out on 1992-08-31 and cut on
1992-09-09. The directory records run back to **1991-08-13**, and the two
oldest files are the publisher's bumper player and its data module. The cell says 1992
because that is when the *disc* was made; 1991 is when two of its components
were.

\*\* **Laser Lords, Studio.** The descriptor's publisher field at offset 318 says
`Philips Interactive Media of America`. The studio is not in a descriptor field:
it is in `/COPYRIGHT`, 425 bytes at LBA 2,271, which reads
`Copyright (c) 1992  Spinnaker Software Corp. and American Interactive Media,
Inc.`, and the same 104-byte string is inside the executable at
`cdi_launcher+0x28a`. Two places, one wording.

\*\*\* **A Visit to Sesame Street — Letters, Year.** The volume descriptor's
creation field at offset 813 reads `1991091316023100` and its modification
field at 830 reads `1991091411185600`, so the volume was laid out on
1991-09-13 at 16:02:31 and re-cut nineteen hours later, after the executable
was rebuilt overnight. The directory records run back to **1991-08-26**, and
the two oldest files are the hot-spot table and the publisher's bumper player.
The cell says 1991 because both dates do.

\*\*\*\* **A Visit to Sesame Street — Letters, Studio.** The descriptor's
publisher field at offset 318 says `American Interactive Media`, and **that is
the only attribution the disc makes**: there is no `COPYRIGHT`, no `ABSTRACT`
and no `BIBLIOGRAPHY` — all three name fields are 32 spaces — and the string
`Philips` does not occur in any of the 673,448,160 bytes of the image. External
sources give the publisher as *Philips Media* and the developer as *Children's
Television Workshop*; the disc confirms neither and the conflict is recorded
rather than resolved in
[chapter 01](https://github.com/vs-sr-dev/cdi-avisittosesamestreetletters-doc/blob/master/docs/01-what-this-is.md).
What the disc *does* confirm about CTW is a picture: a 384 × 240 CLUT7 still
inside both bumper streams reading `CHILDREN'S TELEVISION WORKSHOP`. The
**Saga** cell is empty on purpose. An external source names a companion title,
*Numbers* (1991), in the same *A Visit to Sesame Street* series; that disc has
not been measured here, and a saga of one is not a saga.

\*\*\*\*\* **Burn:Cycle, Year.** All three date fields of the volume descriptor —
creation at offset 813, modification at 830 and effective at 864 — read
`1995052418395600`, the same second: **1995-05-24 at 18:39:56**. That is the
first disc in this collection where all three agree, and it is a fact about the
authoring tool rather than the schedule. The directory records disagree with it
in one direction only: `/BurnCycle.rtr` is stamped 45 minutes earlier at
17:54:37, and **the three text files are from 1994** — `copyright.txt`
1994-03-31, `bibliographic.txt` 1994-08-30, `abstract.txt` 1994-08-31 — with
`copyright.txt` reading, in its entirety, `(c) Trip Media 1994.` The cell says
1995 because that is when the disc was made; external catalogues say 1994
because that is what the copyright line says, and both are right about different
things.

\*\*\*\*\*\* **Burn:Cycle, Studio.** Two places on the disc name it and **for
the first time in this collection they corroborate each other.** The descriptor's
publisher field at offset 318 says `Trip Media`; `/bibliographic.txt`, 3,902
bytes at LBA 2,273, opens `Burn:Cycle` / `From Trip Media and Philips Media`. The
data-preparer field at offset 446 says `Graham Deane`, and the same credit roll
names him twice — `Graham Deane — Runtime and Production Software` and
`Graham Deane — Technical Director` — which is the first time a preparer field
here has been confirmed by the disc's own credits. That roll is 113 name-shaped
strings, about 98 of them people, and it is the largest in the collection by a
factor of three.

\*\*\*\*\*\*\* **Burn:Cycle, Saga.** Empty on purpose, and the filename is why it
had to be checked. The dump is called `Burn-Cycle (Italy) (Il Gioco)` — *the
game* — which reads like a disc designation distinguishing one disc of a set
from another. It is not: external sources give the Italian box line as *"Il Gioco
che ti Manda Fuori"*, so `(Il Gioco)` is a fragment of an advertising slogan.
A companion object does exist and it is **a Red Book soundtrack album** — Discogs
catalogues *Simon Boswell and Chris Whitten — Burn:Cycle* as a CDi + CD pairing,
and the Italian release shipped in two configurations, with and without it. An
audio CD is not a second title, so **a saga of one is not a saga**.

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

### [Laser Lords](https://github.com/vs-sr-dev/cdi-laserlords-doc)

*Laser Lords* (Spinnaker Software Corp. and American Interactive Media, Inc., published by Philips Interactive Media of America, 1992) — the **oldest CD-i disc in this collection by a full year**, and the one that rewrites the strongest result the CD-i pipelines had. The 5,229,000-byte recording in front of the file system, known on three discs of 1993–95, is **byte-identical here on a volume cut 1992-08-31** — and so are 2,269 of the first 2,270 sectors of the pressing, the only difference being the volume descriptor itself. Ten of its twenty-two real-time files are **jukeboxes** of fourteen to sixteen parallel speech channels descending from channel 15, so **6 h 34 m of dialogue** are permanently in front of the head and switching speaker costs no seek. It carries the first **Level A** audio in the collection — eleven seconds of it, in the publisher's logo, pressed twice for NTSC and PAL with byte-identical soundtracks — 95 DYUV stills proved to the byte at 384 × 240, a sixteen-slot table naming real-time files **that were never pressed**, and 64,629 sectors of a video coding the Green Book does not define. This session also gave the CD-i branch its first six **`sha1-all.txt`** lists, 324 records, and the finding that a file-level hash list is blind to both kinds of sharing this platform actually does

### [A Visit to Sesame Street — Letters](https://github.com/vs-sr-dev/cdi-avisittosesamestreetletters-doc)

*A Visit to Sesame Street — Letters* (American Interactive Media, USA, September 1991) — **the oldest disc in this collection by eleven and a half months**, and the first one made for people who cannot read: no text file of any kind, no symbol table, no `printf`, and two human names in a mastering field as the only credit anywhere. Four painted rooms of Sesame Street, **640 pixels wide** and seen through a 384-pixel window, with a 20 KB **hot-spot table** whose coordinates are half-pixels — proved by drawing thirteen of its rectangles over the street and landing on the letterbox, the bird and the trash can. **13,138 DYUV frames at 172 × 108 and 8 fps** decoded, every one aligned, in **32 animated alphabet cartoons**; the eight-sector frame slot is proved by the fact that all 31 interruptions of the video channel's sector run fall *between* frames. The publisher's two bumper streams are **byte-identical to Laser Lords'** eleven and a half months later — eight streams, 2,246,756 bytes, invisible to every file-level hash list because the two files differ — and inside them is the one place the disc spells out its own abbreviation, as a drawing. The executable it replaced **overnight on 1991-09-14 is still on the pressing**, in 41 sectors the file system no longer points at, and the 5.2 MB recording in front of the file system gets eleven months older: five discs of seven, 1991 to 1995

### [Burn:Cycle](https://github.com/vs-sr-dev/cdi-burncycle-doc)

*Burn:Cycle* (Trip Media / Philips Media, UK, May 1995) — **a film with a program inside it**, and the first object in this collection that arrived as a **CHD** rather than an image. **Seven directory entries**, no directories, and **99.23 % of the volume space in one real-time file**: sixty-nine minutes and fifty-six seconds of disc carrying a picture, its soundtrack and the game's own logic past the head at 1×, with **0.68 % padding** — thirty-five times lower than anything else here. The film decodes: **RL7 at 384 × 240, 55,368 frames at 12.5 fps**, 99.977 % of 13,301,593 lines ending exactly on the boundary, and the geometry proved four ways — the bit-7 disproof of the CLUT7 the coding byte claims, the exact-line-end count saturating at 384, vertical autocorrelation at 240, and the **TRIGGER submode bit turning out to be the frame clock**, one per frame, matching the frame count exactly on 857 of 1,025 records. The census says **zero audio sectors** on a disc with a famous Simon Boswell soundtrack, and the census is right and completely misleading: **21,888 sectors carry Green Book ADPCM with the VIDEO type bit set**, found by running section 8's sound-group structure test over every stream rather than only over the ones the type bits call audio — **77 minutes and 49 seconds** of it. The game ships as **353 named, compiled 68000 script objects interleaved with the film they belong to**, one per viewpoint, which is why a 92,880-byte module runs a two-hour game; the linker's **symbol table is still on the pressing**, 633 symbols in three tables whose headers bind each to its module by CRC-24, and it names the whole engine — a stream manager, a video manager that writes the MCD212's control tables by name, and 164 script opcodes behind a `dispatch`. And the box says *Italian*: **twenty-two strings in thirty-four places say so too**, in two encodings, four of them a dirty-disc panic screen stored bottom-line-first inside the executable and eighteen inside the stream — where nobody had looked, because the search had been for the word `italiano` rather than for the language
