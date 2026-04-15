# Podcast Automation Hub

GitHub Actions workflow hub for scheduled podcast generation.

## Active Podcasts

| Podcast | Schedule (JST) | Source Repo |
|---|---|---|
| AIニュースTODAY | 04:30 daily | [`AInewsToday`](https://github.com/EijiAC24/AInewsToday) |
| クリプトトゥデイ | 04:30 daily | [`AInewsToday`](https://github.com/EijiAC24/AInewsToday) |
| 英語ニュース聞き流し | 04:30 daily | [`AInewsToday`](https://github.com/EijiAC24/AInewsToday) |
| Daily Blend Podcast | 06:00 daily | [`DailyBlendPodcast`](https://github.com/EijiAC24/DailyBlendPodcast) |
| Daily Blend Shorts | triggered | [`DailyBlendPodcast`](https://github.com/EijiAC24/DailyBlendPodcast) |

## Architecture

Workflows run on GitHub-hosted `ubuntu-latest`. Each job:

1. Checks out the source repo (podcast code lives there)
2. Runs the podcast pipeline (Gemini → TTS → FFmpeg → FTP → YouTube)
3. Commits generated RSS back to [`podcast-network-rss`](https://github.com/EijiAC24/podcast-network-rss)

## Notes

Scheduled workflows are auto-disabled by GitHub after 60 days of repo inactivity.
Keep this repo active with meaningful commits to avoid the silent shutdown.
