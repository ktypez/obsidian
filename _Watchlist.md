

## Ongoing
```dataview
TABLE season, episode, status, genre
FROM "DATABASE/Watchlist"
SORT file.mtime desc
WHERE status = "ongoing"
```
---
## Finale
```dataview
TABLE season, episode, status, genre
FROM "DATABASE/Watchlist"
SORT file.mtime desc
WHERE status = "Finale"
LIMIT 5
```