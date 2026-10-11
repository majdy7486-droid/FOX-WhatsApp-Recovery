# FOX WhatsApp Recovery AI

A local-first Android app for finding recoverable WhatsApp photos, videos
and media — still-present files the gallery stopped showing, files in
WhatsApp's media folders, and local backup files (detected, not
decrypted). Kotlin, Jetpack Compose, MVVM, Room.

**Read `docs/STATUS.md` first.** This is a real, partially-built project:
Phase 1–2 of the 12-phase plan are implemented with working code (not
stubs), the rest is an explicit, documented roadmap — not silently
missing. No build/test run has been claimed that wasn't actually
performed; see that file for exactly what was and wasn't verified and how.

## Quick orientation
- `app/` — the Android app (Kotlin, Compose, Room)
- `core/file-signatures/` — pure Kotlin/JVM magic-byte file-type detection,
  independently verified (see `docs/STATUS.md`)
- `docs/` — architecture, privacy design, recovery limitations, build
  instructions, and current status

## Principles this codebase follows (from the project spec)
- Local processing by default; no upload without explicit consent; no
  `INTERNET` permission until an online feature actually needs it.
- No request for broader storage access than the features need
  (no `MANAGE_EXTERNAL_STORAGE`).
- Never claims a file is recoverable without checking it; never claims a
  build or test passed without running it.
- No bypassing encryption, lock screens, or another app's protections.

See `README.ar.md` for the Arabic original spec's framing of the same
project.
