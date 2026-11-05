# How this repository was made (Tana River County)

This file is written by the build on 2026-11-05, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| County Assembly of Tana River: "Acts", Kenya Gazette Supplements (Government Printer) as PDF with a text layer | <https://tanariverassembly.go.ke/house-business/acts/> | 2026-10-31 | Text of the Tana River County Acts as published in the Kenya Gazette Supplement (Government Printer, Nairobi) and posted on the website of the County Assembly of Tana River (tanariverassembly.go.ke). Written law is not a literary work under the Copyright Act, 2001 (Cap. 130, Laws of Kenya), section 2, definition of "literary work", which ends: "but does not include a written law or a judicial decision". |
| County Assembly of Tana River: Inspectorate Service Act, Kenya Gazette Supplement No. 13 of 2025 | <https://tanariverassembly.go.ke/documents/2025-trc-fire-and-rescue-act-2025/download/> | 2026-11-05 | Written law is excluded from literary work by the Copyright Act, 2001 (Cap. 130), section 2. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `tana-river-county-health-improvement-financing-act-2025` | The Tana River County Health Improvement Financing Act, 2025 | 1 | 2025-07-31 to 2025-07-31 |
| `tana-river-county-water-and-sewerage-services-act-2024` | The Tana River County Water and Sewerage Services Act, 2024 | 1 | 2025-09-12 to 2025-09-12 |
| `tana-river-county-fire-and-rescue-services-act-2024` | The Tana River County Fire and Rescue Services Act, 2024 | 1 | 2025-11-24 to 2025-11-24 |
| `tana-river-county-sustainable-charcoal-production-act-2025` | The Tana River County Sustainable Charcoal Production Act, 2025 | 1 | 2025-11-24 to 2025-11-24 |
| `tana-river-county-ward-bursary-fund-administration-amendment-act-2025` | The Tana River County Ward Bursary Fund Administration (Amendment) Act, 2025 | 1 | 2026-03-05 to 2026-03-05 |
| `tana-river-county-inspectorate-service-act-2025` | The Tana River County Inspectorate Service Act, 2025 | 1 | 2025-07-31 to 2025-07-31 |

The build made 6 commits:

| Commits | Kind |
| ---: | --- |
| 6 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-05.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 6 tags.

## Dates

Each commit is dated at noon (Africa/Nairobi) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Act is dated by the "Date of Commencement" its Gazette Supplement prints; where that is not a date (for example "See Section 1"), by the date of the Gazette Supplement, and never before the Date of Assent. https://tanariverassembly.go.ke/house-business/acts/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `29ab64d889471349df42340d2d6f69ae06a347a5df692e456e5ba582694ecbb1` (353328 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `35388bee5aa05369f7da68f5a8fa015ea8d442b8`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

6 versions of 6 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 6 history commits and 6 tags (history tip `826fc52e1a60343fec308b107debb2b08b4a94d4`).

## Decisions made by hand

- Text as enacted only: the county assembly posts each Act as its Kenya Gazette Supplement, with no consolidated text, so each Act is one version ("oldest version available", first_law null), credited to the publisher, not to an amending law. Amending Acts in this record are separate Acts; their amendments are not applied to the Acts they amend.
- Each version is dated by the Date of Commencement the Supplement prints; where that is not a date ("See Section 1"), by the date of the Supplement, and never before the Date of Assent.
- One file per section; the long title and enacting words are "000-title", and each Schedule its own file. Part headings and section headings (bold rows or margin notes) stand above the section they head.
- Left out: the Supplement cover, the title block (number, Dates of Assent and Commencement, which go into the version note) and the arrangement of sections, running heads and page numbers.
- An Act is left out when its PDF is a scan with no text layer, is not a Gazette Supplement, cannot be read reliably (tables or forms that the independent check does not find in the same order), or its parsed sections differ from its arrangement of sections.
- The PDF title controls over the incorrect Fire and Rescue title on its listing page.
- The PDF states Date of Commencement: 31st July, 2025; this is the version's in-force date.
- This is the Gazette text as enacted, without a claimed later consolidation; the complete PDF text layer is a single unit.
- The only embedded image is the decorative Kenyan coat of arms on the Supplement cover; no normative image is present.
- First Schedule RANKING is an HTML table derived cell by cell from the official PDF's vector borders and clipped text layer; the Disaster and Traffic staffing notes span five rank rows.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Gazette Supplement PDFs.
- Model selected the source and representation; no model-written law text. The law text is copied mechanically from the PDF text layer.
