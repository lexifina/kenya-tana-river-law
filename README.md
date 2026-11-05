# Tana River County (Kenya): law history in git

The Acts of the County Assembly of Tana River, Kenya, as a git history: one folder per Act, one file per section, one paragraph per line, so `git blame`, `git log` and `git diff` work line by line. The text is the English text of each Act as published in the Kenya Gazette Supplement by the Government Printer and posted by the County Assembly of Tana River on its website.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law).

## What this repository holds

**Acts as enacted, not yet a history.** The County Assembly posts each Act as the Kenya Gazette Supplement that published it; there is no consolidated text. So each Act is one commit holding its text as enacted ("oldest version available"), credited to the publisher, not to an amending law. An amending Act is its own folder; its amendments are not applied to the Act it amends.

| Folder | What |
| --- | --- |
| one folder per Act (by its short title) | Usually `000-title.md` (the Act's title, long title and enacting words), one file per section, one per Schedule. The Inspectorate Service Act, 2025 is held as one complete `000-full-text.md` file. |

The Acts come in parts of about fifty, in date order. An Act is left out until it can be read reliably: scans with no text layer (no OCR is used), documents that are not Gazette Supplements (drafts, Bills, Word copies), PDFs with tables or forms the independent check below does not find in the same order, and PDFs whose sections do not match their own arrangement of sections. Subsidiary legislation is not included.

## Source

[County Assembly of Tana River: Acts](https://tanariverassembly.go.ke/house-business/acts/), each a Kenya Gazette Supplement ("Tana River County Acts") printed and published by the Government Printer, Nairobi. Each PDF's sha256 is recorded with its version in `data/versions.json`.

## Dates

Each Act is dated by the "Date of Commencement" its Supplement prints, at noon in Nairobi. Where that is not a date (for example "See Section 1"), the Act is dated by the date of the Gazette Supplement that published it, and never before its Date of Assent. The version note of each Act gives its number, Supplement, Date of Assent and the rule used.

## How it is built

Lexifina reads the sources listed here and records each act's dated versions, and the laws that made each change, in one corpus file. `tools/build.py` writes this repository from that file, and the same corpus always gives the same commit hashes; `REPRODUCE.md` gives the details and the checks. A model (Claude) wrote Lexifina's code; it wrote no legal text, and no model runs when the history is built.

For section-split Acts, the text layer of each PDF (no OCR) becomes one file per section. The Supplement cover, the title block (number, Dates of Assent and Commencement), the arrangement of sections, running heads and page numbers are left out. Part headings and section headings (bold rows or margin notes) stand above the section they head.

The Inspectorate Service Act, 2025 keeps the entire Gazette Supplement text layer in one file, including the cover, arrangement and running heads. Its official PDF states commencement on 31 July 2025. The assembly listing labels the PDF as a Fire and Rescue Act, while the PDF itself names the Inspectorate Service Act. The First Schedule's RANKING grid is represented as a table in that file, retaining its four division columns and the staffing notes spanning multiple rank rows.

## How it is checked

Every version is read back from git on the day it took effect and must match the corpus. A second, independent reading of every PDF (a different PDF engine) must contain every letter and digit of each Act in the same order, with nothing in the body left out. Results are in `REPRODUCE.md`.

## What "author" means

The author of each commit is the publisher, with an e-mail address that cannot exist; the committer is always Lexifina.

## Limits

Only the Acts as enacted are here: no later amendments, no consolidation, and only the Acts the County Assembly posts with a text layer. The Kenya Gazette is authoritative. This record holds only part of Tana River County's legislation.

## Licence

See [LICENSE](LICENSE): written law is excluded from copyright by the Copyright Act, 2001 (Cap. 130), s. 2. Source: County Assembly of Tana River; Kenya Gazette Supplement (Government Printer).
