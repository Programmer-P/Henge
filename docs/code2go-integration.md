# Code2Go integration — PocketMac (Henge fork)

PocketMac is the user's fork of Leviidev/Henge, and remains separate from Code2Go.
Code2Go is the iPhone/iPad coding editor. Neither is renamed to MaciOS.

## File handoff
- PocketMac keeps its installed bundle ID com.programmerp.henge and existing VM data.
- Henge source Sharing.swift exposes Documents/Shared in Files and at ~/Henge inside its macOS guest after the Henge agent is configured.
- Code2Go uses the Files folder picker to choose PocketMac (Henge) / Shared.
- Code2Go stores a bookmark and copies source files into Shared/Code2Go without overwriting existing versions.
- The generated GuestTest-XXXXXXXX subfolder contains Code2GoProbe.swift and RunGuestTest.command.
- Copy success is NOT proof of guest macOS startup, JIT, compilation, or Xcode compatibility.

## Guest-only QA
1. Enable JIT and boot macOS in PocketMac. A previous JIT pass is not a current session pass.
2. Set up Henge Shared in the guest by using PocketMac Details > Type the Set Up Command, and checking the source and permissions.
3. From Code2Go, select Shared and prepare the guest Swift test.
4. In the macOS Terminal inside PocketMac, run: cd ~/Henge/Code2Go/GuestTest-XXXXXXXX && zsh RunGuestTest.command (use the actual folder name).
5. Mark Swift as passed only when the guest prints CODE2GO_GUEST_SWIFT_PASS after executing its own Swift compiler.
6. Test Xcode installation and xcodebuild separately, and then app compilation, signing, and iOS installation separately.

## Known limitations
- Current PocketMac-to-Code2Go path is an explicit file handoff, not a persistent compiler connection.
- iOS may suspend PocketMac when Code2Go is in the foreground.
- Henge has not been verified running full Xcode in the guest.
- The installed Henge fork remains untouched; this documentation changes no guest disks.
- Henge is GPL-2.0-or-later. Retain upstream license notices and credit.
