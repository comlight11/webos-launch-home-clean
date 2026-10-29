# Launch Home Clean

An independent, public community edition of [webos-launch-home](https://github.com/gprot42/webos-launch-home), with a large mountain-depth clock, a remote-friendly Home menu, configurable app dock and optional root helpers for LG webOS TVs.

**Download the source ZIP and installable IPK from [Releases](https://github.com/comlight11/webos-launch-home-clean/releases).** Version 0.0.133 is a cleaned distribution; it is not the private session archive.

## What is included

- Full editable source, tests, build scripts and MIT license.
- Original **Midnight Peaks** vector wallpaper with a larger clock partly behind the ridge; Pacific Coast (CC0) as another offline background.
- Generic icon artwork; installed apps can use their local TV icons.
- Optional root-helper source for Home takeover, graceful close on exit, LG-push guard and a small exact-host blocklist. These are not automatically enabled by a fresh clean installation.

## Public defaults

Fresh installs start without a personal app list. Add installed apps from **Menu → Alle apps** or **Home aanpassen → Apps**. Weather, music, voice, automatic boot and Home-button routing are off. The system screensaver timeout is unchanged unless **Apply timeout to LG screensaver** is explicitly enabled. Existing local preferences may remain when upgrading the same app ID.

No firmware, partition dump, chat history, diagnostic logs, IP addresses, location/profile exports, credentials, screenshots or private session links are included. Media without clear redistribution provenance was removed. See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

## Install

Use an already-rooted TV with a working [Homebrew Channel](https://github.com/webosbrew/webos-homebrew-channel). Download the clean IPK from this repository's release and install it with a compatible trusted package installer. Open **Launch Home Clean** as a normal app first. This app does not root a TV and does not flash firmware.

The app ID remains `org.webosbrew.lounge.launcher`, so installing it can replace another Launch Home distribution with that ID. A system-Home takeover is a separate advanced opt-in; review the helper and restore commands before enabling one. The clean package has been software-tested and packaged, but this new distribution has not been installed on a TV for an additional hardware-validation run. Keep working Homebrew access for root changes.

## Build

Use Node.js 22 or newer and npm:

```sh
npm ci
npm test
npm run pack
```

The IPK appears in `dist/`. Windows builds can use a writable temporary directory and a workspace-local `APPDATA` location for the webOS packaging CLI. `LAUNCH_HOME_BOUNDED_FS=1` enables the included resolver for restricted Windows environments. Root helpers require Python 3 on the TV; optional voice features have separate dependencies and use credentials entered on the device.

## Scope and privacy

This repository contains a generic software distribution. The original private archive and the owner's TV are not modified by publishing it. Weather and AI providers, if explicitly enabled, contact their respective services; this is not a guarantee of blocking all advertising or telemetry.

## License

Project code is [MIT](LICENSE), retaining attribution to gprot42. New clean artwork is MIT; the Pacific Coast photograph is CC0. Dependency and media notices are listed separately. This community fork is not an official LG or Apple product.
