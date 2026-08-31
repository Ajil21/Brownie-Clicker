# 🍫 Brownie Clicking Speed Test

A single-file, no-build recreation of [Riimu's Cookie Clicker Clicking Speed Test](https://cookie.riimu.net/), reskinned as "Brownie Clicker." Click as fast as you can, watch your CPS live, and see what that pace would've earned you during Cookie Clicker's classic golden-cookie buffs.

## Features

- **Live CPS tracking** — a rolling 1-second window shows your current clicks-per-second in real time
- **Sprint detection** — a sprint starts on your first click and automatically ends after 2 seconds of inactivity, no start/stop button needed
- **Speed chart** — a Chart.js line graph plots your CPS over the course of the sprint
- **Brownie Math** — converts your click count into "Brownies earned," plus projections for what that pace would net during:
  - Frenzy (7×)
  - Clicking Frenzy (777×)
  - Elder Wrath (666×)
- **Sprint history table** — every completed sprint is logged with duration, clicks, average CPS, and peak CPS
- **Responsive, dark UI** — clean single-page layout that adapts down to mobile

## Tech Stack

- Plain HTML/CSS/JS — no framework, no build step
- [Chart.js 4](https://www.chartjs.org/) (loaded via CDN) for the live speed chart
- Google Fonts (Inter)

## Usage

Just open `index.html` in a browser — that's it, no server or install required.

1. Click the circle in the center of the page as fast as you can
2. Keep clicking to extend your sprint — it ends automatically 2 seconds after your last click
3. Check your CPS, Brownie earnings, and sprint history once the sprint ends

## How It Works

- Every click is timestamped with `performance.now()` and pushed into an array
- **Current CPS** = number of timestamps within the trailing 1000ms window
- **Sprint end** is debounced with a 2-second idle timer that resets on every click
- **Average CPS** for a completed sprint = total clicks ÷ sprint duration
- The chart samples CPS every 200ms while a sprint is active and plots it against elapsed time

## Credits

- Original concept: [Riimu's Cookie Clicker Clicking Speed Test](https://cookie.riimu.net/)
- Recreation: **ajil21**

## License

For fun / educational purposes — not affiliated with Riimu or Cookie Clicker.
