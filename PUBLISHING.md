# Publishing plan — pending first qualified release

**STATUS: HOLD.** This repository currently has no signing identity, served signed archive, or Android end-to-end update qualification.

1. On a trusted off-device publisher, generate an encrypted Ed25519 private key using the qualified TRINITY `tools/publisher_setup.py`. Keep private key and passphrase outside GitHub and Android. Back it up safely.
2. Independently verify the SHA-256 fingerprint of its **public** PEM before authorizing that key in Android Cockpit.
3. Enable GitHub Pages through repository Settings → Pages → Deploy from a branch → main, /(root). Verify a real static URL returns HTTP 200 with no redirects.
4. Candidate URL only, **not verified or activated yet**: `https://endy1506.github.io/TRINITY-Mobile-Releases/latest.zip`.
5. From an independently qualified UI-only source tree, use `tools/sign_ui_release.py` to create the release ZIP (signed release.json, release.sig and allowlisted payload). Validate hashes, signer, expiry, scope and sequence.
6. Publish only a reviewed, signed `latest.zip`; preserve immutable release evidence and prior signed copies.
7. In Android Cockpit, one-time configure independently trusted public PEM/fingerprint and verified HTTPS URL. Then Check → Inspect → Approve → Restart → Health check → PASS or rollback/HOLD.

Never use redirecting GitHub Releases asset URLs with RC4. Never claim that core/updater/bootloader updates are handled by this UI-only channel.
