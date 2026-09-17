# agent-proxy releases

This repository is the release feed of **agent-proxy**, a macOS menu-bar
app that keeps real upstream credentials — LLM API keys, GitHub and Jira
tokens, the URLs a container may reach — out of the hands of the coding
agents, containers and scripts that use them. There is no source here; the
source repository is private.

Each release holds two assets:

- `agent-proxy-<version>.zip` — the notarized, stapled app, alone.
- `appcast.xml` — the feed an installed app reads.

## How an installed app uses it

The app fetches `releases/latest/download/appcast.xml` from this repository
every four hours while it runs, and whenever **Check for Updates…** is
chosen. Nothing is downloaded until the user asks. An update is installed
only when its archive's EdDSA signature verifies against the public key
built into the app and the new bundle carries the same Developer ID as the
running one.

## Installing by hand

Unzip the newest `agent-proxy-<version>.zip` and move `agent-proxy.app`
to Applications. The app is notarized and stapled, so Gatekeeper opens it.
Requirements: macOS 13 or later on Apple silicon.

## License

Business Source License 1.1: production use needs a licence from the author
until each version's Change Date, four years after its release, when that
version converts to Apache License 2.0. See [`LICENSE`](LICENSE).
