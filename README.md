### Pierre · Blackwellcode · Graz, Austria

I build software that runs on hardware I operate myself: Linux servers, Windows workstations and game clients.
Each project ships with a README that someone else can follow without asking me, and with CI and tests wherever code runs unattended.

**Open to remote roles and project work.** Contact: [blackwellcode.site](https://blackwellcode.site)

---

#### What I do

| | Focus | Where to see it |
| :--- | :--- | :--- |
| **Self-hosted backends** | Recording pipelines, background workers, Nginx in front of Python, Docker Compose or bare-metal installs | [streamvault](https://github.com/Blackwellcode/streamvault) |
| **Windows tooling** | PowerShell and .NET 8 tools that are safe by design: read-only guarantees checked in CI, no vendor bloat | [winsec-audit](https://github.com/Blackwellcode/winsec-audit), [ultra-light-rgb-control](https://github.com/Blackwellcode/ultra-light-rgb-control) |
| **Large UI codebases** | A Lua addon of 26k lines (including generated data tables) with a module system and 14 languages, maintained through 17 releases | [BlackwellUI](https://github.com/Blackwellcode/BlackwellUI) |

#### Featured projects

**[StreamVault](https://github.com/Blackwellcode/streamvault)** · Python, Flask, Streamlink, FFmpeg, Nginx, SQLite, Docker
- *Problem:* Twitch and YouTube broadcasts and their chat disappear, and hosted archive services keep the data.
- *Solution:* Three services (recorder, worker, web UI) on one Linux server. Flask checks access and Nginx delivers the video through `X-Accel-Redirect`, so Python never streams video bytes. Live HLS segments stay on a RAM disk.
- *Result:* Replay of a stream together with its chat, clips, per-user access, optional cloud sync, a web UI in 12 languages, 179 test functions run in CI.

**[BlackwellUI](https://github.com/Blackwellcode/BlackwellUI)** · Lua 5.0, WoW 1.12.1 client API, Python build tooling
- *Problem:* The game's stock interface hides the numbers that decide a run: damage share, boss timers, spawn locations.
- *Solution:* A modular HUD: a core registry drives every module through one ticker, options pages are generated from each module's declarations, and Python tools extract spell, icon and string tables from the game files.
- *Result:* 200+ settings, 14 languages, 17 releases, 3,731 release downloads (GitHub API, 2026-11-10).

**[winsec-audit](https://github.com/Blackwellcode/winsec-audit)** · PowerShell 5.1/7, GitHub Actions
- *Problem:* Security audit scripts tend to "fix" things as they go, which no one wants to run on a production workstation.
- *Solution:* 44 read-only checks across Defender, firewall, network, accounts, platform, logging and persistence, with Markdown and JSON reports.
- *Result:* "Read-only" is enforced by CI on every commit: an AST guard with an allowlist, a self-test with 15 forbidden samples, and a runtime test that fingerprints system state before and after the run.

**[Ultra Light RGB Control](https://github.com/Blackwellcode/ultra-light-rgb-control)** · C#, .NET 8, HidSharp, LibreHardwareMonitor, OpenRGB SDK
- *Problem:* Showing CPU and GPU temperature on an AIO display and on RGB lighting normally means installing the vendor's suite.
- *Solution:* One background process, started at boot as SYSTEM, reads the sensors, renders the LCD and drives the LEDs over HID, NVAPI I2C and the OpenRGB protocol. No save or EEPROM command is ever sent.
- *Result:* 0.15 % CPU (whole system) and 46 MB private memory with the Classic theme, measured on a Ryzen 7 9800X3D.

**[Requiem](https://github.com/Blackwellcode/requiem-desktop)** · Rainmeter, Windhawk, Windows Terminal, PowerShell
- A complete Windows 11 desktop theme with a one-command install and a documented revert.

#### Tech stack

| Area | Technologies |
| :--- | :--- |
| Backend | Python (Flask, Babel), SQLite, C# / .NET 8 |
| Media | FFmpeg, Streamlink, yt-dlp, HLS |
| Infrastructure | Linux (Debian/Ubuntu), Nginx, systemd, Docker Compose, GitHub Actions |
| Windows | PowerShell 5.1/7, scheduled tasks, HID and I2C device access |
| Scripting and UI | Lua 5.0, Jinja templates, Rainmeter |
| Not on GitHub | Next.js, TypeScript, self-hosted Supabase (PostgreSQL), Playwright |

#### How I work

- I measure before I optimise. Performance figures in my READMEs come from real runs.
- Safety rules live in tests: read-only guards, no device writes, no secrets in Git.
- Documentation covers installation, configuration and how to undo it.
