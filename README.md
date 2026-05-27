# Postman & Proxyman for Mobile Development

## 🏀 NBA GameDay — A Practical Guide

> All examples use a fictional **NBA GameDay** app that displays live scores, player stats, game schedules, and league standings. Everything generated randomly from AI.

### Consistent Data Reference

| Item | Value |
|------|-------|
| **App Name** | NBA GameDay |
| **Prod URL** | `https://api.nbagameday.com` |
| **Alpha URL** | `https://alpha-api.nbagameday.com` |
| **Beta URL** | `https://beta-api.nbagameday.com` |
| **API v1** | `/api/v1/` (current) |
| **API v2** | `/api/v2/` (new features) |
| **Teams** | Los Angeles Lakers, Boston Celtics, Golden State Warriors |
| **Players** | LeBron James (`p-2544`), Jayson Tatum (`p-1628369`), Stephen Curry (`p-201939`) |

---

## 📁 Directory Structure

```
mdevcamp2026/
├── README.md                          ← this file
├── postman/
│   ├── 01-variables.md                ← Variables feature guide
│   ├── 02-environments.md             ← Environments feature guide
│   ├── 03-scripting.md                ← Pre-request scripts guide
│   ├── environments/
│   │   ├── production.json            ← Postman env export: Production
│   │   ├── alpha.json                 ← Postman env export: Alpha
│   │   └── beta.json                  ← Postman env export: Beta
│   ├── responses/
│   │   ├── player-stats.json          ← Sample: player stats response
│   │   ├── game-schedule.json         ← Sample: game schedule response
│   │   ├── standings.json             ← Sample: league standings response
│   │   ├── team-roster-nba.json       ← Sample: NBA team roster
│   │   └── team-roster-wnba.json      ← Sample: WNBA team roster
│   └── scripts/
│       ├── timestamp-rounding.js      ← Pre-request: round to 5min
│       ├── correlation-id.js          ← Pre-request: generate trace ID
│       └── auto-token-refresh.js      ← Pre-request: JWT auto-refresh
├── proxyman/
│   ├── 01-map-local.md                ← Map Local feature guide
│   ├── 02-scripting.md                ← Response scripting guide
│   ├── mocks/
│   │   ├── live-scores.json           ← Mock: live scores (v2 endpoint)
│   │   ├── play-by-play.json          ← Mock: play-by-play (v2 endpoint)
│   │   ├── error-403.json             ← Mock: 403 Forbidden
│   │   ├── error-500.json             ← Mock: 500 Internal Server Error
│   │   └── error-429.json             ← Mock: 429 Rate Limited
│   ├── scripts/
│   │   ├── nfl-to-nba-transform.js    ← Script: transform NFL → NBA
│   │   ├── inject-advanced-stats.js   ← Script: inject PER & advanced stats
│   │   └── simulate-live-game.js      ← Script: scheduled → live transition
│   ├── responses/
│   │   ├── before/
│   │   │   ├── league-summary.json    ← Original NFL response
│   │   │   ├── player-stats.json      ← Original player stats
│   │   │   └── game-schedule.json     ← Original scheduled game
│   │   └── after/
│   │       ├── league-summary.json    ← Modified NBA response
│   │       ├── player-stats.json      ← Modified with advanced stats
│   │       └── game-schedule.json     ← Modified with live data
│   └── openapi/
│       ├── live-scores.yaml           ← OpenAPI spec: live scores
│       └── play-by-play.yaml          ← OpenAPI spec: play-by-play
```

---

## 🔧 Quick Reference — When to Use What

| Scenario | Tool | Feature |
|----------|------|---------|
| Reuse requests with different data | **Postman** | Variables |
| Switch between dev/staging/prod | **Postman** | Environments |
| Auto-generate tokens, timestamps | **Postman** | Pre-request Scripts |
| Test against an API that doesn't exist | **Proxyman** | Map Local |
| Simulate error codes (403, 500, 429) | **Proxyman** | Map Local |
| Modify specific fields in a live response | **Proxyman** | Scripting |
| Inject new fields to test upcoming features | **Proxyman** | Scripting |
| Simulate state transitions (scheduled → live) | **Proxyman** | Scripting |

---

## 📖 Reading Order

1. [Postman: Variables](postman/01-variables.md)
2. [Postman: Environments](postman/02-environments.md)
3. [Postman: Scripting](postman/03-scripting.md)
4. [Proxyman: Map Local](proxyman/01-map-local.md)
5. [Proxyman: Scripting](proxyman/02-scripting.md)

> 📎 All examples are **copy-paste ready** and use consistent data from the NBA GameDay app throughout.
