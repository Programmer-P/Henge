# PocketMac — Henge fork

PocketMac is the personal, GPL-compliant fork of [Henge](https://github.com/Leviidev/Henge), intended to emulate macOS on the user's iPhone and iPad. This project is separate from Code2Go (the iOS IDE).

- Upstream base: Leviidev/Henge, GPL-2.0-or-later. Preserve original attribution, source notices, and license.
- Installed iPad bundle ID: com.programmerp.henge. Keep this ID stable for existing sandbox/guest data.
- Do not delete or overwrite the existing guest macOS disk, app container, or saved machine state.
- macOS Tahoe is the target guest; boot, JIT, command-line Swift, then full Xcode are separate QA gates.
- Henge's current source requires Xcode 27+ for rebuilding; current host Xcode 26.6 is insufficient.
- PocketXcode connects only through an explicitly built and authenticated bridge; no implicit cross-app filesystem access.
- Henge upstream notes emulation is slower than a real Mac; no Xcode-in-guest pass has been established.

## Code2Go relationship

Code2Go is the separate iPhone/iPad IDE, not a replacement for PocketMac. The safe Henge Files Shared handoff and guest Swift/Xcode QA gates are documented in docs/code2go-integration.md.
