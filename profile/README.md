# Bombadil Systems

Security research company. We build tools that poke at the assumptions underneath how security products work.

## What we're looking at

Many security scanners decide what a file is by reading its header. `%PDF` means PDF. `MZ` means EXE. If the header matches, they run their detection rules for that format. If it doesn't match anything they recognize, a lot of them just skip it.

We've been building tools that test what happens when you mess with that assumption, and with some of the other assumptions stacked on top of it. The short version is: things fall apart faster than you'd expect.

## Tools

**Veriduct** started it all. It strips file headers and breaks files into salted chunks stored as a SQLite database. The scanner sees a database, not a PDF or an EXE. We tested it against Cobalt Strike, Emotet, and ValleyRAT samples on VirusTotal and went from 143 combined detections to zero. Reconstruction is bit-for-bit perfect (SHA256 verified). Presented at DEF CON DC862 and BSidesROC.

**BIRL** (Byte Interpretation Rewriting Language) came out of wanting to understand *why* Veriduct works so well. It maps which bytes inside a file actually get read by parsers and which get ignored. Turns out most PE scanners only look at the entry point region and skip everything else. BIRL measures that gap, and can build polyglots and inject payloads into the parts nobody's reading. About 9,000 lines of Python covering PE, ELF, ZIP, PNG, x86, and UTF-8.

**Latent Logic** is a Z3 constraint solver for Windows privilege escalation. You give it your current integrity level and privileges, it finds chains of operations to get to SYSTEM. It also does evasion path discovery, finding payload placements that fall in regions most static scanners don't inspect. The scanner coverage data comes from empirical testing across 24 engines, categorized by behavior rather than named individually.

**Tnsyr** is a weird one. It runs Windows x64 binaries in a browser, using pure JavaScript, no plugins. It parses PE headers, resolves imports, applies relocations, interprets x86-64 instructions, and has about 580 Win32 API function stubs. It's for watching what a binary does in a controlled environment without giving it a real system.

**OIS-ROP** is a different approach entirely. Every byte value from 0x00 to 0xFF already exists somewhere inside kernel32.dll. So instead of storing payload bytes, you store a list of offsets into signed Microsoft DLLs. At runtime you just read the byte at each offset. The payload never exists as bytes until assembly. The file on disk is just a list of numbers.

## How they fit together

Veriduct proved that removing format signatures kills detection. That raised the question of what scanners are actually parsing, which led to BIRL. BIRL's coverage data feeds into Latent Logic's solver. Tnsyr exists because we wanted to watch PE execution without trusting a sandbox. OIS-ROP started as a "what if the payload itself doesn't need to exist" experiment.

They weren't planned as a suite. They grew out of each other.

## Repos

| Project | Description |
|---------|------------|
| [Veriduct-Prime](https://github.com/Bombadil-Systems/Veriduct-Prime) | Format destruction for security testing |
| [birl](https://github.com/Bombadil-Systems/birl) | Parser coverage analysis, residue measurement, polyglot construction |
| [latent-logic](https://github.com/Bombadil-Systems/latent-logic) | Z3 privesc and evasion path solver |
| [tnsyr](https://github.com/Bombadil-Systems/tnsyr) | Browser-native PE runtime |
| [ois-rop](https://github.com/Bombadil-Systems/ois-rop) | Payload projection from signed binary offsets |

## Talks

DEF CON DC862 (Dec 2025) and BSidesROC. Both on Veriduct and format destruction.

## Contact

Chris Aziz / chris@bombadil.systems

Everything here is MIT licensed and intended for authorized security testing.
