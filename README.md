# Find Your Team

Team roster page for ameristarperimeter.com, plus the admin app that edits it
and the territory map without touching code.

| File | What it is |
|---|---|
| `index.html` | The page. Reads `data/team.json` at load. Never needs editing for a roster change. |
| `data/team.json` | Sections and people. Edit with `admin.html` or directly on GitHub. |
| `images/` | Headshots, 457×687 JPG. `placeholder.jpg` shows for anyone whose file is missing. |
| `admin.html` | Editor for this page **and** the territory map. Open it at `…/find-your-team/admin.html`. |
| `aem-embed-snippet.html` | Iframe + auto-resize script for the AEM embed. |

`index.html?team=<slug>` renders one section (for per-section AEM embeds).

## Admin app — one-time setup

1. GitHub → profile photo → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Resource owner **AmeristarWebDev** · expiration up to 1 year · Repository access **Only select repositories** → `find-your-team` and `territorymap`.
3. Repository permissions → **Contents: Read and write**. Nothing else.
4. Generate, copy the `github_pat_…` token, open `admin.html`, paste it on the Settings tab, tick *Remember*, click **Connect & load**.

## Day-to-day

- **Team Page tab** — pick a section, edit names/labels, drag in photos, reorder, add/remove people or sections.
- **Territory Map tab** — *States*: territory, Market Developer(s) and Project Manager per state. *Territories*: color, DCM, roster, Territory Sales list, email, phone. *People & Photos*: everyone the map can show; rename here and every reference updates.
- Every change waits until **Save to GitHub**, which commits the data files and any new headshots. GitHub Pages republishes in about a minute; AEM-embedded pages follow after the usual cache window.
- Uploaded photos are cropped to 457×687 automatically and (by default) saved to both repos so the two pages stay in sync.

Every save is a normal commit — if something looks wrong, revert it on GitHub.
