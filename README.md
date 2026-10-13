# TRINITY Mobile — Signed Releases

Public **distribution-only** repository for TRINITY Mobile Bridge.

**Current state: HOLD — no signed update channel is active yet.** Android continues working offline with its installed version.

This repository will publish only qualified, Ed25519-signed **UI-only** release archives compatible with RC4. It must never contain private signing keys, passphrases, browser tokens, personal data, database files, evidence bundles or backups.

GitHub hosting alone does not authorize code execution. The Android Cockpit independently pins a publisher public key and fingerprint, verifies signature and file hashes, inspects the exact changes, requests explicit approval, and checks restart health with rollback on failure.

See [PUBLISHING.md](PUBLISHING.md) and [SECURITY.md](SECURITY.md).

TRINITY Mobile is separate from U-FORGE and Gate #76.
