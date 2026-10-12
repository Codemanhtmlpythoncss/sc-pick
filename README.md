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
sc-pick "my track name"          # search tracks
sc-pick -p "my playlist"         # search playlists (downloads every track)
sc-pick -d ~/Music/mine "query"  # choose download folder
sc-pick -l                       # show what you've downloaded
```

At the prompt:

| Input   | Action |
|---------|--------|
| `1 3`   | download results 1 and 3 |
| `t2`    | temporary download of result 2 (deleted when you quit) |
| `s`     | new search |
| `p`     | switch between tracks and playlists |
| `f`     | change download folder |
| `l`     | show download log |
| `q`     | quit |

Results you've already downloaded are marked `✓`. Tracks are never downloaded twice,
even inside playlists, thanks to the yt-dlp archive.

Playlists go into their own subfolder. Log and archive live in `~/.local/share/sc-pick/`.

Env vars: `SC_PICK_DIR` (default `~/Music/soundcloud`), `SC_PICK_LIMIT` (default 15).
