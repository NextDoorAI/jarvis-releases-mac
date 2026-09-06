# jarvis-releases-mac

macOS release channel for Jarvis.

Kept separate from [`jarvis-releases`](https://github.com/NextDoorAI/jarvis-releases),
which serves Windows. Both platforms resolve their update manifest through
`releases/latest/download/`, and Windows ships far more often — so a shared repo
meant `latest` always pointed at a Windows release carrying `latest.json` but no
`latest-mac.json`, and the macOS updater got a 404 every time. Version tags
collided for the same reason.

Each release here carries three assets:

| asset | purpose |
|---|---|
| `Jarvis.app.tar.gz` | the app bundle the updater installs |
| `Jarvis.app.tar.gz.sig` | its minisign signature |
| `latest-mac.json` | the manifest the app polls |

The app resolves the manifest through
`https://github.com/NextDoorAI/jarvis-releases-mac/releases/latest/download/latest-mac.json`,
so releases must be **published** — not drafts or pre-releases — and the asset
filenames must stay exactly as above.