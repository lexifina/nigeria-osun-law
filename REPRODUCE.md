# How this repository was made (State of Osun)

This file is written by the build on 2026-11-01, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| State Government of Osun: Laws (PDF) | <https://www.osunstate.gov.ng/> | 2026-11-01 | Laws of the State of Osun, from the copies the State Government of Osun publishes at osunstate.gov.ng. Official texts of a legislative nature are not eligible for copyright: Copyright Act, 2022 (Nigeria), s. 3(b). |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `public-procurement-law-2015` | State of Osun Public Procurement Law, 2015 (No. 8 of 2015) | 1 | 2015-02-10 to 2015-02-10 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-01.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 2 tags.

## Dates

Each commit is dated at noon (Africa/Lagos) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Law is dated by its own commencement provision; a Law that states none is dated by the day the Governor assented to it, the day it was made. https://www.osunstate.gov.ng/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `a25eed01f5ba551503cf4a2cc9f3b7236c379f46af63baa5430ed4b96158e3a1` (102759 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `5d0eabdf207e7a114e8dbc8112ed3b044537b711`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Public Procurement Law 2015 is dated 2015-02-10, the day the Governor assented to it ("ASSENTED to by me this 10th day of February, 2015"): the Law prints no commencement provision of its own, and a State Law without one comes into force on the day it is assented to.
- Each Law is one version: the text as enacted, credited to the Law itself (first_law) and dated by its commencement. Later amendments are not in this record.
- One file per section. The title lines printed before the enacting formula are "000-title", the enacting formula (where printed) is "001-enacting-formula", and schedules follow the sections. Each section's heading is its printed margin note (or, where there is none, "Section N") and stands as the file's first line; it is not part of the checked text.
- The text layer is read with line positions: running heads, page numbers and margin notes are set apart by their place on the page, and the pieces of one printed row are joined left to right. Lines wrapped by the printer are joined into one paragraph per line; a new paragraph starts at a section number, a bracketed (sub)paragraph letter or number, a quoted definition, a Part heading or a schedule heading. A Part heading printed after a section is placed at the head of the next section. Typing errors in the source stay as printed.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none: the text is the PDF text layer, parsed by rules; no model wrote or corrected legal text.
