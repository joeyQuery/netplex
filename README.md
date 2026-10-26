# NetPlex

Another [Plex](https://www.plex.tv/) client for LG webOS televisions. based on the native solution [plx-native](https://plxnative.com/)

[Install guide (same as plx-native)](https://plxnative.com/install/) 

The same install steps are in the original plx-native repo: [installation guide](docs/install-and-verify.md).*

## Why this exists

For those who like the look, feel and performance of the Netflix UI.

## What it looks like

No screenshots available for now.

## What it does

This part isn't available yet.

## Will it work on my television?

Since it relies on plx-native, it follows the same requirements to run: **webOS 4.0 or newer**, with two tested exceptions: a 2016 set on **webOS 3.4.3** signs
in, browses, searches and plays (direct play, transcodes, subtitles and seeking) through Developer
Mode, and a 2018 set on **webOS 3.9.3** plays direct play the same way when built from source at
or after [`60f99c7`](https://github.com/GLinnik21/plx-native/commit/60f99c7) — the catalogue's
prebuilt v0.8.0 predates that fix (see [Known issues](#known-issues)). Other 3.x releases are
untested, and anything older than 3.4 is unknown. Past that, it most
likely will. I develop and test on a 2019 set, and opt-in usage reports show
video playing on sets from 2018 through the newest, on webOS 11 — both direct play and server
transcodes, Developer Mode installs included.

### Known issues

Please see plx-native for known issues

## Installing

**First time installing an app outside the LG Content Store?** Follow the
[**step-by-step installation guide**](docs/install-and-verify.md). It starts with a regular LG
webOS TV, a computer on the same network, and a Plex account with access to your own or a shared
server. **No root is required.**

Set up LG Developer Mode and connect with webOS Dev Manager, then choose:

- **Install NetPlex directly:** add only NetPlex to the TV; install future `.ipk` updates from
  your computer.

**Developer Mode needs periodic renewal.** If it expires and LG disables Developer Mode, apps
installed through it are removed. Installing Homebrew Channel through Developer Mode does not
remove that requirement. The guide explains [how to renew the session](docs/install-and-verify.md#important-developer-mode-expires).

For manual `.ipk` downloads, [verify the release checksum](docs/install-and-verify.md#verifying-the-package)
before installing. Homebrew Channel verifies catalogue downloads for you.


## Privacy

**Your library data never reaches me.** The app talks to your Plex server, to `plex.tv` to sign in,
and to `discover.provider.plex.tv` for cast biographies.

**Crash reports and usage analytics are off until you turn them on** — two separate first-run
questions, each answerable with Don't Share, both reversible later under Account → Settings →
Privacy & data. No title, search term, subtitle line, server name or address can appear in any
report. [`PRIVACY.md`](PRIVACY.md) is the whole statement, including the schemas.

ASS/SSA subtitles render natively during direct play, including styles, positioning, overlapping
signs and dialogue, karaoke, and embedded fonts. External ASS files retain their original scripts.
A re-encode still burns the selected subtitle on the server; over a remux the app draws a sidecar, and an embedded track when the link is local and the Part is 1..=30000 kbps, and otherwise the server burns it.


## Licence

[GPL-3.0-or-later](LICENSE), © 2026 Gleb Linnik. The PlxNative name and its brand artwork are excluded — see
[`TRADEMARKS.md`](TRADEMARKS.md), which also carries the Plex and LG non-affiliation statements.
Third-party components and their licences are in
[`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) and `licenses/` — notably the app ships its own
LGPL build of FFmpeg. Those notices and licence texts ship inside the `.ipk` too, so they travel
with the binary and not only with this repository.

This is an unofficial client, not affiliated with, endorsed by, or sponsored by Plex GmbH or LG
Electronics. "Plex", "Rotten Tomatoes", "IMDb", "TMDB", "LG" and "webOS" are trademarks of their
respective owners; where they appear in the app, they identify whose service or score is being shown.
