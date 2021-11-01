# scriptsnake

[![Chrome Web Store](https://img.shields.io/chrome-web-store/v/jinjaccalgkegednnccohejagnlnfdag.svg)](https://chrome.google.com/webstore/detail/scriptsnake/jinjaccalgkegednnccohejagnlnfdag)
[![Firefox Add-ons](https://img.shields.io/amo/v/scriptsnake.svg)](https://addons.mozilla.org/firefox/addon/scriptsnake)
[![Microsoft Edge Add-on](https://img.shields.io/badge/dynamic/json?label=microsoft%20edge%20add-on&query=%24.version&url=https%3A%2F%2Fmicrosoftedge.microsoft.com%2Faddons%2Fgetproductdetailsbycrxid%2Feeagobfjdenkkddmbclomhiblgggliao)](https://microsoftedge.microsoft.com/addons/detail/eeagobfjdenkkddmbclomhiblgggliao)
[![Gitter](https://img.shields.io/gitter/room/scriptsnake/scriptsnake.svg)](https://gitter.im/scriptsnake/scriptsnake)
[![Subreddit subscribers](https://img.shields.io/reddit/subreddit-subscribers/scriptsnake)](https://www.reddit.com/r/scriptsnake/)

scriptsnake provides userscripts support for browsers.
It works on browsers with [WebExtensions](https://developer.mozilla.org/en-US/Add-ons/WebExtensions) support.

More details can be found [here](https://scriptsnake.github.io/).

## Automated Builds for Testers

A test build is generated automatically for changes between beta releases. It can be installed as an unpacked extension in Chrome and Chromium-based browsers or as a temporary extension in Firefox. It's likely to have bugs so do an export in scriptsnake settings first. This zip is available only if you're logged-in on GitHub site. Open an entry in the [CI workflows](https://github.com/scriptsnake/scriptsnake/actions/workflows/ci.yml) table and click the `scriptsnake-...` link at the bottom to download it.

## Environment Variables

The following environment variables will be injected at compilation time for some features to work:

- `SYNC_GOOGLE_CLIENT_ID` / `SYNC_GOOGLE_CLIENT_SECRET` - Google sync service
- `SYNC_ONEDRIVE_CLIENT_ID` / `SYNC_ONEDRIVE_CLIENT_SECRET` - OneDrive sync service

## Workflows

### Development

Make sure [Node.js](https://nodejs.org/) greater than v10.0 and Yarn v1.x is installed.

``` sh
# Install dependencies
$ yarn

# Watch and compile
$ yarn dev
```

Then load the extension from 'dist/'.

### Building

After a new (pre)release is created, we should build the project and upload to web stores.

``` sh
# Build for normal releases
$ yarn build

# Build for self-hosted release that has an update_url
$ yarn build:selfHosted
```

## Release

Just create a tag and push it.

When a tag is pushed to GitHub, a (pre)release will be created with assets built by GitHub Actions.

```sh
# Create a prerelease
$ yarn bump

# Create a patch release
$ yarn version --patch
```

## Related Projects

- [scriptsnake for Opera Presto](https://github.com/scriptsnake/scriptsnake-oex)
- [scriptsnake for Maxthon](https://github.com/scriptsnake/scriptsnake-mx)
