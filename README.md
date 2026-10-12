# sc-pick

Search SoundCloud from the terminal, pick results from a numbered list, and download them.

Only download tracks you own or have permission/licence to download.

## Requirements

- [soundcloud-cli](https://github.com/tamnd/soundcloud-cli): `go install github.com/tamnd/soundcloud-cli/cmd/soundcloud@latest`
- [yt-dlp](https://github.com/yt-dlp/yt-dlp)

## Install

```bash
git clone <this repo> && sudo install sc-pick/sc-pick /usr/local/bin/
```

## Usage

```bash
sc-pick "my track name"   # or just: sc-pick
```

Enter one or more numbers to download, `s` for a new search, `q` to quit.

Files go to `~/Music/soundcloud` (override with `SC_PICK_DIR`). Result count: `SC_PICK_LIMIT` (default 15).
