# K-releases

Update metadata for the K app. **This repository contains no source code** —
only the JSON file below, so the app can check for a new build without any
login, token, or access to the private K repository.

## Files

- `update.json` — latest build info. The app fetches this file (no auth) and
  compares the `commitShort` with the commit its own build was made from.
  A different commit means a new build is available.
- The `apkUrl` points at the private K repository's `latest` release. The
  release itself is private, so downloading opens in the browser, where the
  user's own GitHub sign-in handles access. No credential is ever embedded
  in the app.

## Updating

After a new K build lands (new commit on K's main + green CI + release
asset updated), update `update.json` with the new commit, APK size, SHA-256
and `updatedAt`. Nothing else in this repo changes.
