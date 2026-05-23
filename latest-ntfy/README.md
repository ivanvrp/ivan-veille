# latest-ntfy/

3 fichiers écrits par les routines de veille (veille-360, veille-claude-weekly).
Le GitHub Action `.github/workflows/notify-ntfy.yml` détecte les changements et POST vers ntfy.

- `title.txt` — 1 ligne : titre de la notif
- `tags.txt` — 1 ligne : tags ntfy comma-separated (ex: satellite_antenna,fire)
- `body.txt` — multilignes : body markdown ≤ 4 KB
