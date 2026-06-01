# homebrew-fsvc

Homebrew tap for [`fsvc`](https://github.com/j4y-w4lk3r/fsvc) — financial-services CLI for the j4y suite (Revolut Business today, ING tomorrow).

## Install

```bash
brew install j4y-w4lk3r/fsvc/fsvc
```

That command implicitly runs `brew tap j4y-w4lk3r/fsvc` first (pointing at this repository).

## What's in here

`Casks/fsvc.rb` — a Homebrew Cask that pulls the prebuilt binary for your platform from the latest [`fsvc` GitHub release](https://github.com/j4y-w4lk3r/fsvc/releases). The Cask is auto-generated and pushed by [goreleaser](https://goreleaser.com/) on every `vX.Y.Z` tag in the upstream repo — see [`.goreleaser.yaml`](https://github.com/j4y-w4lk3r/fsvc/blob/main/.goreleaser.yaml) and [`.github/workflows/release.yml`](https://github.com/j4y-w4lk3r/fsvc/blob/main/.github/workflows/release.yml) for the release flow.

Don't edit `Casks/fsvc.rb` by hand — it's overwritten on every release.

## Why a Cask, not a Formula

`fsvc` ships as a precompiled Go binary. Homebrew's Cask format is the right packaging mode for that (Formula was historically a hack for binary distribution). On macOS, the Cask post-install hook also strips the `com.apple.quarantine` xattr so the binary runs without Gatekeeper warnings — `fsvc` isn't notarized (Apple Developer Program fee not justified for a personal CLI).

## Related taps

- [`j4y-w4lk3r/homebrew-bbm`](https://github.com/j4y-w4lk3r/homebrew-bbm) — Backblaze B2 manager
- [`j4y-w4lk3r/homebrew-rui`](https://github.com/j4y-w4lk3r/homebrew-rui) — router-UI CLI for Orange/UPC home routers
- [`j4y-w4lk3r/homebrew-ykw`](https://github.com/j4y-w4lk3r/homebrew-ykw) — multi-recipient YubiKey GPG workflow
- [`j4y-w4lk3r/homebrew-pikvm`](https://github.com/j4y-w4lk3r/homebrew-pikvm) — Pi-KVM helper CLI
