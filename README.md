# Astra Launcher Releases

This repository hosts public Astra Launcher downloads and the in-app update feed.

## Publishing a release

1. Build and sign both supported APKs from the source repository.
2. Create a GitHub Release in this repository and upload the APK files.
3. Name APK assets so their ABI is visible, for example:
   - `AstraLauncher-2.8.3-Alpha1-arm64-v8a.apk`
   - `AstraLauncher-2.8.3-Alpha1-armeabi-v7a.apk`
4. Add a line to the release description containing the new Android version code:
   `Version Code: 200054`
5. Publish the release.

The `Publish Astra update feed` workflow will read the release notes and APK assets, then update `latest_version_md.json`. The Astra app checks this feed on startup (rate-limited to once per hour) and from Settings > About > Check for Updates.

The version code must be greater than the version code of the previously published app. Never publish an APK signed with a different key from the installed Astra app, or Android will reject it as an update.
