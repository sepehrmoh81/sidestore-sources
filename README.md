# SideStore Sources

Personal SideStore source repo. Add the link below to SideStore to install and update apps from this repo.

## Source URL

Copy this link:

```
https://raw.githubusercontent.com/sepehrmoh81/sidestore-sources/refs/heads/main/sources.json
```

## How to add the source

### Option 1: Paste the link

1. Open **SideStore** and go to the **Sources** tab.
2. Tap **+** in the top corner.
3. Paste the URL above and confirm.

### Option 2: One-tap links (on your iPhone)

- [Add to SideStore](sidestore://source?url=https://raw.githubusercontent.com/sepehrmoh81/sidestore-sources/refs/heads/main/sources.json)
- [Add to AltStore](altstore://source?url=https://raw.githubusercontent.com/sepehrmoh81/sidestore-sources/refs/heads/main/sources.json)

These only work when opened on a device that has the app installed. GitHub may block custom-scheme links in some views, so if a button does nothing, use Option 1.

## Apps

| App | Version | Min iOS | Notes |
|-----|---------|---------|-------|
| [YTKACE](https://github.com/itzzace/ytkace) | 1.1.3 | 17.0 (iOS 16 build also listed) | Open-source YouTube enhancer and downloader |

## Updating the source

When a new release comes out for an app, edit `sources.json` and update:

- `version` and `versionDate`
- `versionDescription`
- `downloadURL` (the new `.ipa` link from the app's GitHub release)
- `size` (in bytes)
- `sha256` (in the matching entry under `versions`)

Add the new build to the top of the `versions` list so older builds remain available.

Quick checks before committing:

```bash
# Validate the JSON
python3 -m json.tool sources.json > /dev/null && echo "valid"

# Get size and SHA-256 of a downloaded IPA
stat -c %s app.ipa
sha256sum app.ipa
```

## Adding another app

Copy an entry in the `apps` array of `sources.json`, give it a unique `bundleIdentifier`, and fill in its details. One source can hold any number of apps.

## Disclaimer

This repo only hosts a JSON index that links to files published by the apps' own authors. It does not host or distribute any IPA files. Make sure you are legally allowed to use any app you install.
