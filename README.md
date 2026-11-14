# Her Wanderlust Path Flight Monitor

A Malaysia-focused flight monitoring dashboard for routes from Kuala Lumpur (KUL) and Singapore (SIN), with MYR currency display.

## Current dashboard build

- Screenshot-inspired pink interface with Overview, Deal Radar, Route Monitoring, Price Calendar, Price Trend and Price Alerts.
- Retains the existing 44 destination airports, 2 origins (KUL/SIN), 88 origin-destination combinations and 11-airline directory.
- Responsive layout for desktop and mobile.
- Route watchlist and target budgets can be saved in the current browser.

## Strict fare-data policy

**The dashboard must not invent, estimate, randomize or display sample fares.** It only accepts fare records that are explicitly marked verified and include a source, MYR currency and checked timestamp.

- When no verified feed is available, price fields remain blank/“暂无真实报价”.
- Price charts and calendars remain empty until real historical/date-specific data exists.
- A locally saved watchlist is not the same as an active automatic price alert.
- Telegram notifications and scheduled collection are not enabled in this v2 frontend yet.

## Verified fare feed contract

The frontend looks for `data/verified-fares.json`. The file currently starts empty. A future scheduled collector must populate it only with real provider responses, for example:

```json
{
  "updated_at": "2026-11-14T10:00:00+08:00",
  "fares": [
    {
      "origin": "KUL",
      "destination": "NRT",
      "trip_type": "round_trip",
      "price": 1800,
      "currency": "MYR",
      "source": "Provider name",
      "checked_at": "2026-11-14T10:00:00+08:00",
      "verified": true
    }
  ]
}
```

The example above documents the data shape only; it is not a fare quote and is not included as live data.

## Live collection status

The previous repository `Jerserry/her-wanderlust-flight-monitor` contains a SerpApi Google Flights collector and Telegram workflow. That collector is not automatically connected to this v2 repository. It must be adapted to v2's two origins, 44 destinations, airline policy, date rotation and API quota before scheduled collection is enabled. The SerpApi key and Telegram credentials are repository-specific GitHub Actions secrets and must be configured in this repository separately.

## Run locally

Serve this folder with a static web server, for example:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Reference and attribution

The interface structure is informed by the open-source project [dengmeiluan/ticket-monitoring](https://github.com/dengmeiluan/ticket-monitoring), licensed under Apache License 2.0. This repository is an independent adaptation for KUL/SIN routes, MYR display and a different airline/destination configuration. See [LICENSE](LICENSE). Original project authors retain their respective rights.
