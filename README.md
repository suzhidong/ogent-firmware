# Ogent firmware downloads

This repository distributes approved Ogent recorder firmware and release notes. Source code is managed separately. No recordings, transcripts, voice profiles, pairing data, credentials or signing keys belong here.

The current stable firmware is [Ogent recorder 0.3.31](https://github.com/suzhidong/ogent-firmware/releases/tag/v0.3.31). Laboratory and spare-board test images are not stable releases.

The earlier [0.3.26 spare-board preview](https://github.com/suzhidong/ogent-firmware/releases/tag/v0.3.26-test.1) remains a **Pre-release** for already-provisioned test hardware. It is not offered by the app's stable update channel. Read its hardware and acceptance limits before use.

Version 0.3.31 improves SD transfer error reporting and retries an outstanding multi-block read stop before reinitialization. Controlled real-card recovery completed without a power cycle or MCU restart while phone audio continued. Directory reindexing during recovery can take about one minute. The original historical timeout trigger was not recorded by the old firmware; this release does not establish that every SD fault has the same cause. Activation of this version through the user's Check update flow remains a separate verification step.

The prior version 0.3.28 passed real iPhone download, cancellation, disconnect recovery, process-restart retry, firmware activation and a subsequent bounded background reception/transcription check. The background observation included a verified locked interval; it was unlocked by the final query. An earlier reception stall did not recur during that observation, but its initial cause is unresolved. Read the release notes for these limits and the separate spare-board recovery evidence.

## Updating a recorder

In an Ogent app build with official update-channel support, open **My device → Firmware update → Check for updates**. When an approved newer version is available, tap **Update**. The app downloads and validates the correct package; you then confirm when to restart the recorder. There is no file picker or link to paste. Older app builds may have a different update screen.

Older recorders require initial USB preparation before Bluetooth updates are supported. Downloading a file does not add OTA support to an older bootloader. Restarting to update temporarily pauses recording.

## Fixed update addresses

- Release history: <https://github.com/suzhidong/ogent-firmware/releases>
- App version check: <https://api.github.com/repos/suzhidong/ogent-firmware/releases/latest>
- Latest approved package: <https://github.com/suzhidong/ogent-firmware/releases/latest/download/recorder.ogentfw>

The latest-release addresses resolve to 0.3.31. The versioned and latest package downloads are verified against the signed production package and SHA-256. Test prereleases are excluded from this channel.

Each stable release includes `recorder.ogentfw` and `LICENSES.txt`. The package embeds its hardware ID, signed-image version, checksum and third-party license notices. The recorder verifies the firmware signature before running an update.

See [Publishing a release](PUBLISHING.md) for the maintainer workflow. Firmware licensing is specified in the notices attached to each release.
