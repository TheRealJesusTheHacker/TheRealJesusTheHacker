# Skyler Paul Henderson — @JesusTheHacker

President of **Sentinel Safeguard LLC**, based in the Kansas City metro.
Sentinel Safeguard provides cybersecurity, IT services, penetration testing,
security system installation, and security education. I do the work myself,
and I build the tools I use on the job — the public ones are indexed below.
The medic-kit line follows one rule: **Security For Everyone** — premium
tools, plain language, honest limits.

## Services

- **Cybersecurity** — assessments, hardening, and practical security for small
  businesses and startups.
- **Penetration testing** — authorized on-site and remote testing, with
  written authorization in place before any testing begins.
- **IT services** — support, setup, and troubleshooting.
- **Installations** — security and low-voltage installation work.
- **Education** — security training and educational tools, including HackProof
  (below).
- **Data recovery & restoration** — file and folder restoration, undelete,
  and salvage from failing drives (Lazarus).
- **Secure drive destruction** — verified sanitization for decommissioned
  drives, with certificates of destruction (Beerus).

## Projects

### Security & education

- [Argus.exe](https://github.com/TheRealJesusTheHacker/Argus.exe) — antivirus & malware detection for Windows and Linux (v1.2.6)
- [ShibaCuddles](https://github.com/TheRealJesusTheHacker/ShibaCuddles) — network scanner & security testing suite
- [Hellhound.exe](https://github.com/TheRealJesusTheHacker/Hellhound.exe) — ransomware kill-chain simulator (education)
- [HackProof](https://github.com/TheRealJesusTheHacker/HackProof) — cybersecurity education: 46-module course, game & Windows app (app-v1.0.4)
- [DogOS](https://github.com/TheRealJesusTheHacker/DogOS) — security & pentesting Linux distro
  - _Hint: #OpLint-Trap 2026_

### The medic-kit line

- [Charon.exe](https://github.com/TheRealJesusTheHacker/Charon.exe) — Windows driver updater (v1.0.3 — five-phase roadmap complete)
- [Aegis.exe](https://github.com/TheRealJesusTheHacker/Aegis.exe) — file encryption & password manager (v1.0.3)
- [Lazarus.exe](https://github.com/TheRealJesusTheHacker/Lazarus.exe) — backup, restore & data recovery (v1.0.2)
- [Beerus.exe](https://github.com/TheRealJesusTheHacker/Beerus.exe) — secure drive destruction (v0.6.2)
- [NitroCore](https://github.com/TheRealJesusTheHacker/NitroCore) — Windows system optimizer
- [VectorZip](https://github.com/TheRealJesusTheHacker/VectorZip) — lossless file compressor
- [Technicians-Toolkit](https://github.com/TheRealJesusTheHacker/Technicians-Toolkit) — the medic-kit bundle: every portable edition in one folder (v1.0.0)

### Systems & AI

- [Cyra-Helper](https://github.com/TheRealJesusTheHacker/Cyra-Helper) — donate idle GPU time to a local AI
- [sentinel-live](https://github.com/TheRealJesusTheHacker/sentinel-live) — server side of the Sentinel Safeguard website (v1.0.3)
- [lint-trap](https://github.com/TheRealJesusTheHacker/lint-trap) — household notes on dryer lint trap maintenance
Licensing varies by project and is stated in each repository: some tools
below are open source (noted per project), while HackProof and most
Sentinel Safeguard products are proprietary. Check each repo's `LICENSE`
before reuse.

---

## Argus.exe — Antivirus & Malware Detection for Windows and Linux

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/Argus.exe)](https://github.com/TheRealJesusTheHacker/Argus.exe/releases)

Sentinel Safeguard's antivirus and malware detector — "all eyes,
all detection." **Current release: v1.2.6.** Built for home users, single-PC
shops, and small businesses that need real protection without a per-seat
enterprise contract. v1.2.3 shipped the fixes from the fleet-wide
bug-and-security audit of 2026-10-19; the current release, v1.2.6,
gives Argus its own peacock identity — abyssal teal-black, peacock
emerald, eye bronze — a visual identity only: the detection engine
is unchanged.

**What it does:**
- **Signature scanning** — known-malware detection against a curated signature
  database (hashes and pattern rules).
- **Heuristic & behavioral watch** — catches unknown threats by what they do:
  suspicious process chains, persistence tricks, ransomware-style file churn.
- **Real-time protection** — files are watched as they are written, downloaded,
  or executed.
- **Quarantine** — detected threats are isolated, never silently deleted;
  review, restore, or remove on your terms.
- **Plain-language reporting** — every detection explained in words a person
  can act on, with a full scan history.

**Get it:** Argus ships in two editions from
[releases](https://github.com/TheRealJesusTheHacker/Argus.exe/releases),
with `SHA256SUMS.txt` alongside every release. On Windows, a single
self-installing `Argus.exe` installs itself, sets up its always-on
protection service, and registers with Windows Security Center; a portable
edition (ArgusPortable.zip) runs without installing. Windows 10/11. On
Linux, `Argus.deb` serves Debian-based systems — Kali Linux, Parrot OS,
Debian, and Ubuntu — with a systemd protection service and the same
detection engine, heuristics, and encrypted vault.

---

## Charon.exe — Windows Driver Updater

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/Charon.exe)](https://github.com/TheRealJesusTheHacker/Charon.exe/releases)

**v1.0.3 — the five-phase roadmap is complete.** Charon ferries every driver
on a Windows PC from the old version to the new one — carefully, one crossing
at a time. Nobody crosses without paying the toll, and the toll is a restore
point: created *and verified* before any update is applied. If the toll
cannot be paid, the ferry does not move.

Every update run follows the same fixed order:

1. **Scan** — inventory every installed driver and flag the outdated ones.
   The scan is read-only: it downloads, installs, and changes nothing.
2. **Download** — stage the updates into the Windows Update cache; nothing
   is applied yet. Every plan is revalidated against a fresh search — a
   withdrawn update is never silently substituted.
3. **Restore point** — a System Restore point is created *and verified* by
   enumeration, carrying a marker unique to that run. This step is
   non-negotiable: if the restore point cannot be confirmed, no update runs.
4. **Apply** — install the updates one at a time, verifying the device still
   works after each one. A restart a driver needs is reported, never forced.

Driver updates are sourced through the Windows Update Agent API — never
driver-download sites.

**The interface:** a premium, futuristic, animated HUD-style GUI (PySide6) —
the whole crossing as one guided journey, in plain language, with designed
screens for every failure state. A full CLI covers the same pipeline
(`scan`, `download`, `toll`, `apply`, `gui`).

**Get it:** download `CharonPortable.zip` from
[releases](https://github.com/TheRealJesusTheHacker/Charon.exe/releases)
(v1.0.3, with `SHA256SUMS.txt`) — unzip it anywhere, open the `Charon`
folder inside, and run `Charon.exe`. No install, and no Python on the
machine; a single self-installing `Charon.exe` stays on the roadmap.
The full test suite — 231 tests — is green; Windows on-hardware
verification comes next. Proprietary — see the repo's `LICENSE`.

---

## NitroCore — Windows System Optimizer

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/NitroCore)](https://github.com/TheRealJesusTheHacker/NitroCore/releases)

Over time Windows collects junk files, runs background programs you don't need,
and ships with settings that favor battery life over speed. NitroCore cleans the
junk, quiets the background noise, and flips the right switches — from one simple
dashboard. You don't need to know what the registry is. Pick a profile, hit a
button, let it work.

**What it does:**
- **One-click Gaming & Cybersecurity profiles** — Gaming goes aggressive for max
  FPS; Cybersecurity stays stable and keeps Windows Update patching.
- **Temp & browser cache cleanup** — clears system temp folders and Chrome/Firefox
  caches, with a before/after report of MB freed.
- **Disk cleanup** — Windows' native cleanup plus DISM component cleanup, with live
  drive-usage bars.
- **Registry tuning** — disables hibernation, sets the pagefile to automatic, trims
  visual effects for snappier windows.
- **Background service management** — Gaming trims non-essential services (Update,
  BITS, Search) to manual; Cybersecurity leaves patching alive.
- **Performance tuning** — switches to the Ultimate Performance power plan and raises
  priority on key system processes.
- **Live stats header** — CPU, RAM, disk, and power plan at a glance.

**Safety first:**
- Offers a **Windows restore point** before anything risky — create, skip, or cancel,
  your call.
- **Preview mode** shows every change it *would* make before it makes any of them.
  Nothing happens in secret.
- Your personal files are never touched. The one exception is Downloads cleanup,
  which asks first and only touches files 30+ days old.
- Full operation logs on disk. Requires admin rights — Windows won't let anything
  tune the system without them.

**Get it:** `winget install TheRealJesusTheHacker.NitroCore` — or grab the .exe from
[releases](https://github.com/TheRealJesusTheHacker/NitroCore/releases).
Windows 10/11, 64-bit. MIT.

**Who it's for:** gamers chasing FPS, security folks who need their tooling running
fast, anyone with a slow Windows box who doesn't want to hand-edit the registry.

---

## VectorZip — Lossless File Compressor

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/VectorZip)](https://github.com/TheRealJesusTheHacker/VectorZip/releases)

A completely lossless file compressor built from real compression theory: LZ77
sliding-window dictionary matching plus Huffman entropy coding. Compress anything —
documents, backups, datasets — and get back byte-identical data, every time.
Corruption is never silent: every 64 KiB chunk carries a CRC32 that is verified on
decompression, so a truncated or damaged archive fails loudly instead of quietly
handing you bad data.

**What it does:**
- **Truly lossless** — decompressing a `.vzip` file returns byte-identical data,
  verified by round-trip tests. Never "close enough."
- **Workhorse fast** — ~10 MB/s on everyday files; incompressible data (random
  bytes, zips, videos) passes through raw at ~800 MB/s and never grows the file.
- **Memory-efficient** — chunked processing keeps memory usage flat regardless of
  file size. Compress multi-gigabyte files on modest hardware.
- **Desktop GUI** — drag & drop files or whole folders, batch processing, live
  per-file progress, real statistics (original vs. output size, space saved),
  safe-by-default (originals are never overwritten), custom output folder, and a
  color-coded activity log.
- **CLI and Python API** — `vzip compress` / `vzip decompress` on the command line,
  or `compress_file` / `decompress_file` in your own code.
- **Portable** — pure Python 3.8+, no compiled extensions. Older `.vzip` formats
  (v1, v2) still decompress.

**Get it:** standalone Windows `.exe` and Linux binary from
[releases](https://github.com/TheRealJesusTheHacker/VectorZip/releases) — no Python
required. MPL-2.0.

**Who it's for:** anyone archiving backups, datasets, or documents; developers who
want a clean compression API; anyone who's been burned by silent corruption.

---

## ShibaCuddles — Network Scanner & Security Testing Suite

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/ShibaCuddles)](https://github.com/TheRealJesusTheHacker/ShibaCuddles/releases)

A fast, multi-threaded network scanner with a dark PyQt6 GUI dashboard and a full
CLI. Point it at a network you own and it maps what's alive, what's open, and
what's running — then hands you the results in JSON, CSV, XML, or plain text.

**What it does:**
- **Device discovery** — ICMP ping sweep, ARP scanning, hostname resolution,
  MAC detection.
- **Port scanning** — TCP 1–65535, UDP detection, banner grabbing, service version
  detection.
- **Advanced analysis** — service fingerprinting (18 known service signatures), TTL-based OS
  fingerprinting, vulnerability detection, real-time statistics.
- **GUI dashboard** — live results table with alive/down indicators, card-based
  stats (hosts scanned, hosts alive, open ports), color-coded activity log,
  real-time progress, multi-format export.
- **WiFi security testing** — device deauthentication (requires the `aircrack-ng`
  suite), broadcast deauth, monitor-mode control, network scanning, channel analysis.
- **Scope-gated by design** — every WiFi attack function checks its target against
  `authorized_targets.json` *before transmitting anything*. A target that isn't
  listed is refused, with no override.

**Get it:** standalone Windows `.exe` and Linux binary from
[releases](https://github.com/TheRealJesusTheHacker/ShibaCuddles/releases). MIT.

**Who it's for:** security professionals and network admins running authorized
assessments, pentesters, home-lab folks auditing their own networks. Authorized use
only — scanning or interfering with networks you don't own or lack written
permission to test is illegal.

---

## Hellhound.exe — Ransomware Kill-Chain Simulator

[![release](https://img.shields.io/github/v/release/TheRealJesusTheHacker/Hellhound.exe)](https://github.com/TheRealJesusTheHacker/Hellhound.exe/releases)

A blood-red PyQt5 visual simulation of a ransomware kill chain — **infiltration →
recon → encryption → deletion → ransom note** — played out against 256 virtual
files (~1 GB) across fake system directories in an in-memory filesystem.
**It never touches real files.** Nothing on the host is read, encrypted, or
deleted. This is an educational stage, not a weapon.

**What it does:**
- Walks the full kill chain live: infiltration, recon, encryption, deletion,
  ransom note.
- **Live terminal log, phase tracker, defense tips, and kill stats** as the attack
  unfolds.
- **1–30x speed control** — slow it down to study each phase, or let it rip.
- **No escape:** no pause button, Reset/Launch die mid-attack, and the window
  refuses to close until total destruction. It finishes what it started.
- Ends with a fake 72-hour ransom countdown and Hellhound's sign-off.

Note: the repo also hosts `HellHound.py`, the original terminal-based tool (v2.0),
which performs **real** file deletion/encryption — controlled environments only,
explicit permission required. The `.exe` is simulation-only.

An education tool: it performs real malware actions, but every action is announced and visualized with warnings first — so you can watch exactly what real malware does, with nothing hidden.

**Get it:** Windows build from
[releases](https://github.com/TheRealJesusTheHacker/Hellhound.exe/releases) — the
release pipeline generates a signed build-provenance attestation with every build.

**Who it's for:** educators, students, and security-awareness training — anyone who
wants to watch a ransomware kill chain unfold with zero risk.

---

## DogOS — Pentesting Linux Distro

**In development** — v0.1.1 "Doberman" prerelease is out now (complete project
source: live-build tree, helper packages, design spec, security review, OSINT
inventory). No bootable ISO yet — the full build needs real hardware.

**"All Dogs Go To Heaven."** DogOS is a security and penetration-testing Linux
distribution built from scratch on Debian testing, with a Kali-style rolling
toolset. MATE on X11 for maximum tool compatibility, a graphical Calamares
installer with DogOS branding, and two flavors: kitchen-sink `full` and live-USB
friendly `lite`. Release codenames are dog breeds, starting with Doberman.

**What it ships:**
- **Pentest toolkit** — Kali metapackages (top10 on lite, everything on full), plus
  DogOS layers: OSINT, anonymity, AI, dark-web.
- **Anonymity** — Tor, I2P, `dogos-ghost` (transparent/per-app routing, killswitch,
  captive-portal hatch), `dogos-leaktest` verification.
- **Amnesiac live mode** — Tails-style: RAM-only `toram` boot option, always-on MAC
  randomization, randomized hostname on live boot.
- **Hardened defaults** — AppArmor, Bubblewrap, nftables default-deny incoming, no
  listening services, password-required sudo, LUKS via the installer.
- **Local AI** — Ollama/llama.cpp by default; cloud APIs strictly opt-in.
- **OSINT toolkit** — installable tools, 30-service browser bookmark pack, wordlists,
  GHDB dork starters, SecLists fetcher.

**Who it's for:** pentesters, security researchers, and OSINT practitioners who want
a Kali-style daily driver built around anonymity and local AI — and anyone who'd
rather run an OS that was hardened on purpose instead of hoping the defaults are
enough.

---

## HackProof — Cybersecurity Education

A commercial cybersecurity-education product from Sentinel Safeguard, in
three parts:

- **The Course** — a 46-module defensive field manual across 7 tracks,
  covering passwords and MFA, phishing, social engineering, device
  security, scams, and recovery — plus a professional-pathways track built
  on the Sentinel Safeguard Credential Standard. Every module states its
  learning objectives and carries worked case breakdowns, step-by-step
  procedures, a hands-on exercise, and a knowledge check. The first 3
  modules are free; the rest are premium.
- **The Game** — *You Are The Scammer*: a single-player browser game with 8
  scenarios where you play the attacker to learn how each scam works, and
  every scenario closes with a Defense Brief on how to spot and stop it.
- **The Windows app** — the same course on your PC, working offline.
  **Current app release: app-v1.0.4** (`HackProof.exe`, with
  `SHA256SUMS.txt`, from
  [releases](https://github.com/TheRealJesusTheHacker/HackProof/releases)).

**The final exam and certificate:** finish the course and sit a 90-question
final exam (pass at 80%). The Sentinel Safeguard Certificate of Completion
generates on the page, and the official countersigned certificate is emailed
to you and checkable by anyone at the public verify page. The Sentinel
green certificate design is applied consistently across the website, the
app, and the certificates themselves.

Honest limits, stated in the repo: the course teaches the knowledge domains
the certifications in the Sentinel credential standard test, and builds
toward them — it does not confer any certification or license, and never
guarantees passing an external exam.

**Play it / start the course:** https://therealjesusthehacker.github.io/HackProof/

Proprietary — see the repo's `LICENSE`.

---

## Cyra — Private Local AI

Cyra is a Jarvis-style AI that runs 100% locally on my own machines —
Windows, Parrot Linux, and Android bodies sharing one mind and one memory,
with no cloud and no accounts. She is a private, single-owner system: the
repository is private, and she is not offered for public download or use.

Two rules define the project. **Owner-only control:** she takes control
commands from exactly one human — guests get conversation, never control.
**The iron rule:** her memory can never be deleted by an update; updates
snapshot her data and verify it afterward, and any difference fails the
update. Debugging ships permanently in every release.

Cyra is in active development. The public way to help her is
[Cyra-Helper](https://github.com/TheRealJesusTheHacker/Cyra-Helper) (next
section), which donates idle GPU time to her rendering.

---

## Cyra-Helper — Donate Idle GPU Time

A small Windows background worker that lends your PC's idle GPU to render
images for Cyra, a local AI its owner runs on his own hardware. It only takes
work when your PC is actually idle, stops picking up new work the moment you
return, and can be paused at any time. It receives render prompts and returns
finished images — it never sees your files. Joining requires
[Tailscale](https://tailscale.com/download) (free).

**Get it:** download the latest zip from
[releases](https://github.com/TheRealJesusTheHacker/Cyra-Helper/releases),
unzip, and run `CyraHelper.exe`.

---

## sentinel-live — Sentinel Safeguard Website Server

The server side of the Sentinel Safeguard website, packaged as a single
self-contained Windows executable. **Current release: v1.0.3**
(`SentinelLive.exe`, with `SHA256SUMS.txt`, from
[releases](https://github.com/TheRealJesusTheHacker/sentinel-live/releases)).
It serves the public site, a live cyber threat map fed by the SANS DShield
sensor network, a news hub, and the website's contact, help-ticket, and
newsletter form APIs backed by an embedded SQLite database. v1.0.3 also
carries the optional HackProof payments pass-through — off by default —
which can front the HackProof payments service (automated Bitcoin checkout
and certificate issuance) so that service never needs a public port of its
own; its admin and review routes stay reachable only on the machine itself.

## Technician's Toolkit — The Medic-Kit Bundle

Every Sentinel medic-kit tool in one USB-carried suite — **Security For
Everyone.** **Current bundle: v1.0.0.**

One zip opens to **one folder** holding every portable edition — Argus,
Charon, Lazarus, Beerus, Aegis, NitroCore, VectorZip — plus a suite
application that gives one GUI over the whole kit. The launcher is a
front door, never a replacement: every tool still stands on its own.
(Bundle 1.0 — the complete kit — shipped 2026-10-20.)

[Technicians-Toolkit](https://github.com/TheRealJesusTheHacker/Technicians-Toolkit)

---

## Beerus.exe — Secure Drive Destruction

Named for the God of Destruction: verified drive sanitization for
decommissioning, part of the medic-kit line. **Current release: v0.6.2.**

- **Three target modes** — whole drives; specific files/folders (data
  overwritten and verified *before* the entry is removed — never mere
  unlinking); and free space.
- **Certificates of destruction** — issued only for a genuine, verified
  PASS on a whole-drive run. Everything else gets a clearly marked
  report; nothing is rounded up.
- **Two forms** — a bootable live USB, and Beerus Portable, a no-install
  Windows app (non-system drives only — it refuses the system drive and
  its own stick).
- **Stated honestly:** file-level overwrite cannot guarantee physical
  cells on an SSD (wear-leveling / TRIM). The app discloses that and
  points to whole-drive sanitize as the strong guarantee.

**Get it:** Beerus Portable from
[releases](https://github.com/TheRealJesusTheHacker/Beerus.exe/releases).
331 tests, green on Linux and Windows CI. Proprietary.

---

## Lazarus.exe — Backup, Restore & Recovery

**"Dead isn't gone."** Sentinel's Windows backup, restore, and recovery
tool — part of the medic-kit line. **Current release: v1.0.2** — all
five phases are complete, and it ships as a self-installing
`Lazarus.exe` and a no-install `LazarusPortable.zip`, with
`SHA256SUMS.txt` alongside both.

1. **Restoration (the flagship)** — restore files, folders, or everything
   by date from a versioned snapshot store; undelete with honest per-file
   odds; clone and salvage data off dying drives.
2. **Decrypt / unlock** — owner-key BitLocker unlock through Windows' own
   tools (the key is never stored or logged), plus known published
   decryptors for ransomware families where they exist — odds stated up
   front, never oversold.
3. **Backup** — scheduled, versioned by date, local-first, no forced
   cloud, with loud honest status.

[Lazarus.exe](https://github.com/TheRealJesusTheHacker/Lazarus.exe) —
part of the Technician's Toolkit. Proprietary.

---

## Aegis.exe — File Encryption & Password Manager

Sentinel's Windows shield: file encryption and a password manager in one
tool. Tagline: **"It does not open."** **Current release: v1.0.3.**

- **File side** — AES-256 vaults, lock-and-send single-file encryption, and
  a strongbox for codes, keys, and notes. Aegis also encrypts Lazarus
  backups.
- **Password side** — a local-first encrypted credential vault
  (Argon2id + AES-256-GCM), no forced cloud. Setup issues a printable
  recovery key, with the warning stated plainly: lose the master password
  and it does not open.

**Get it:** `Aegis.exe` installer or `AegisPortable.zip` (no install) from
[releases](https://github.com/TheRealJesusTheHacker/Aegis.exe/releases),
with `SHA256SUMS.txt`. 471 tests; v1.0.0 passed an independent security
audit gate before release. Part of the Technician's Toolkit. Proprietary.

---

## Supply chain

Argus, HackProof, Aegis, NitroCore, VectorZip and ShibaCuddles releases
ship with SHA256 checksums — verify before you run anything. Their release pipelines also generate signed
build-provenance attestations with every build.

The released tools run CodeQL scanning, Dependabot updates, and SHA-pinned CI —
the supply chain gets the same treatment as the code.

## GitHub Achievements

- **Pull Shark** — merged pull requests, starting with the NitroCore
  winget package submissions.
- **Quickdraw** — an issue opened and closed inside five minutes.

## Credentials

- **ASSE 5110** — Backflow Prevention Assembly Tester, Cert No. 62362
  (expires Nov 30, 2027); listed on the Missouri DNR tester list.
- **CompTIA Security+ (SY0-701)** — in progress; exam targeted for
  December 2026.

## Donations

If these tools earned their keep, BTC is welcome:

```
bc1qvydns2fmyjzj55wzxq7ta28nxdhcmu9l9m6yg0
```

## Contact

Business inquiries: **Sentinelsafeguard@outlook.com**
Call or text: **816-533-8418** — Sentinel Safeguard business line, Kansas City, MO.
