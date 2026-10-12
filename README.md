# sc-pick

Search SoundCloud from the terminal, pick results from a numbered list, and download them.

Only download tracks you own or have permission/licence to download.

## Requirements

Just `bash` and `curl`. On first run, sc-pick installs everything it needs into `~/.local/share/sc-pick/` — no sudo
required: the search helper ([soundcloud-cli](https://github.com/tamnd/soundcloud-cli), built with Go, which it also
installs if missing), [yt-dlp](https://github.com/yt-dlp/yt-dlp), and its own bundled `sdownload` (a yt-dlp wrapper for
downloads). If you already have a richer `sdownload` on your `PATH` that supports `--output-dir` and `--archive-file`,
sc-pick uses that one instead.

## Install

```bash
git clone https://github.com/Codemanhtmlpythoncss/sc-pick && sudo install sc-pick/sc-pick /usr/local/bin/
```

## Usage

```bash
sc-pick                          # main menu
sc-pick "my track name"          # jump straight to track results
sc-pick -p "my playlist"         # playlist results (downloads every track)
sc-pick -k                       # open your liked list
sc-pick -d ~/Music/mine          # choose download folder
sc-pick -l                       # print download log
```

Move with the arrow keys (or `j`/`k`), press Enter to choose, `q` or Esc to go back.
Pick a song, then choose **Play**, **Download**, **Temporary download** (deleted when you quit),
**Like**/**Unlike**. The liked list has **Play all** and **Download all** options. Playing uses
[mpv](https://mpv.io), which sc-pick installs on first play (asks for your sudo password on Linux). Change the download
folder from the main menu.

Tracks SoundCloud only streams with DRM can't be downloaded. For your own tracks,
turn on direct downloads in the track settings on soundcloud.com and sc-pick will
fetch the original file.

Results you've downloaded are marked `✓`, liked ones `♥`. Tracks are never downloaded twice,
even inside playlists, thanks to the shared archive passed to sdownload.

Playlists go into their own subfolder. Liked list, log and archive live in `~/.local/share/sc-pick/`.

Env vars: `SC_PICK_DIR` (default `~/Music/soundcloud`), `SC_PICK_LIMIT` (default 15).
