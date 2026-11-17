# gta6-twitch-forecast

[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/HisyamMahfuDz/gta6-twitch-forecast/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/HisyamMahfuDz/gta6-twitch-forecast/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

A forecaster for Grand Theft Auto VI's launch-day Twitch viewers, hour by hour. Given the first hour's viewer count, the pre-release history, and the hourly curves of past comparable launches, it writes five quantiles (5/25/50/75/95%) of the viewer count for each of hours 2–24 of the release day.

How it works: every comparable launch contributes its release-day curve as log-ratios to its own hour-1 count. Comparables are weighted by two pre-forecast signals — the shape of their pre-release ramp (which reflects how the launch unlocked) and how close their hour-1 count is to this case's — and each hour's quantiles are the similarity-weighted quantiles of those ratios, with a slightly shrunk, floored spread. Standard library only, no network, deterministic; any unexpected input falls back to a persistence forecast rather than failing.

## Run it

```sh
MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=0a6j83jv&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
