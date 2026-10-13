# TRINITY Release Security

- **Never** commit publisher private keys, passphrases, Android tokens, personal files or backups.
- Publisher key generation and signing happen **off the Android executor**, on a trusted machine with secure encrypted key backup.
- Verify the publisher public-key fingerprint via an **independent** channel before pinning; a value hosted here cannot vouch for itself.
- RC4 allows *only* exact UI-target files. It must not update core, approval logic, bootloader, updater or trust anchor.
- Releases must be Ed25519-signed, SHA-256 checked, sequence-monotonic, non-expired and manually approved.
- Do not configure an unverified URL, bypass HOLD, downgrade or auto-install.
- On startup/health failure, restore the prior qualified version. Fail closed.
- Do not add signing secrets to public GitHub Actions.
