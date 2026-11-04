# Ogent firmware downloads

This repository distributes approved Ogent recorder firmware and release notes. Source code is managed separately. No recordings, transcripts, voice profiles, pairing data, credentials or signing keys belong here.

**No stable firmware has been published yet.** Existing laboratory and spare-board test images are not stable releases.

## Updating a recorder

In Ogent, open **My device → Firmware update → Check for updates**. When an approved newer version is available, tap **Update**. The app downloads and validates the correct package; you then confirm when to restart the recorder. There is no file picker or link to paste.

Older recorders require initial USB preparation before Bluetooth updates are supported. Downloading a file does not add OTA support to an older bootloader. Restarting to update temporarily pauses recording.

## Fixed update addresses

- Release history: <https://github.com/suzhidong/ogent-firmware/releases>
- App version check: <https://api.github.com/repos/suzhidong/ogent-firmware/releases/latest>
- Latest approved package: <https://github.com/suzhidong/ogent-firmware/releases/latest/download/recorder.ogentfw>

Until the first stable release is published, the latest-release addresses return 404. Ogent displays that no stable update is available; it does not offer a test image or claim the recorder is up to date.

Each stable release includes `recorder.ogentfw` and `LICENSES.txt`. The package embeds its hardware ID, signed-image version, checksum and third-party license notices. The recorder verifies the firmware signature before running an update.

See [Publishing a release](PUBLISHING.md) for the maintainer workflow. Firmware licensing is specified in the notices attached to each release.
