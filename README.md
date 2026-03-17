# yt-proxy

GitHub Actions proxy for GP Attendance YouTube audio.

## How it works
1. Script triggers `repository_dispatch` with `video_id`
2. Workflow fetches stream URL from Invidious (server-side, no corporate proxy)
3. Commits `data/stream.json` with the audio URL
4. Script polls `raw.githubusercontent.com/.../data/stream.json` until `request_id` matches
5. `<audio>` plays the stream URL

## Setup
- Add a GitHub PAT (with `repo` scope) as repo secret: `GH_PAT`
jsdhsjdh
- Set in console: `localStorage.yt_gh_token = 'YOUR_PAT'`
- Set in console: `localStorage.yt_gh_repo = 'YOUR_USERNAME/yt-proxy'`
