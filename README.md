# infracom-updates

Public update feed for **Infracom Mail**, the internal messaging client.

This repo holds only the Sparkle `appcast.xml` for the macOS client, the
`updates.json` manifest for the Windows client, and the release archives they
point at, so installed copies can find and verify updates.

**No application source is ever published here.** The source lives in a
separate private repository. Releases are published by `release.sh` in the
client source tree, which builds, signs, notarizes and uploads in one step.

Every macOS archive is Developer ID signed, Apple-notarized, and signed again
with an EdDSA key whose public half is compiled into the app; Sparkle refuses
anything that does not verify. Windows archives carry a SHA-256 that the client
checks before installing. Being public makes the feed readable, not writable:
it cannot be used to push a build we did not sign.
