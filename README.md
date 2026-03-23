# Prayer of the Church — PWA
## Ukrainian Greek-Catholic Church

### Project Files

| File | Size | Purpose |
|------|------|---------|
| `index.html` | ~68 KB | Complete PWA — all UI, logic, and English vespers text |
| `manifest.json` | 0.5 KB | PWA manifest (installable on iOS/Android) |
| `sw.js` | 1 KB | Service Worker for offline support |
| `data/calendar2026.json` | 62 KB | Saints, tones, fasting for all 365 days |
| `data/vespers-moveable-uk.json` | 2.7 MB | Ukrainian Vespers moveable parts (Jan–Mar 2026) |

### Serving Locally (Development)

Requires a local HTTP server (not just file:// due to fetch API):

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .

# PHP
php -S localhost:8080
```

Then open `http://localhost:8080`

### Features Built (v0.5)
- [x] Calendar navigation with ‹ › day navigation
- [x] Month strip calendar with feast/Lent indicators
- [x] Full month calendar view
- [x] Liturgical day info (saint, tone, fasting, period)
- [x] English Vespers — full text for March 11, 2026
  - All fixed parts (Opening, Psalm 103, Litany, Psalm 140, O Gladsome Light, Vouchsafe, Litany of Supplication, Prayer of Simeon, Trisagion, Prayer of St. Ephrem, Psalm 33)
  - Moveable placeholders for other dates
  - Sunday prokeimena by tone (all 8 tones)
- [x] Ukrainian Vespers — fixed opening + full moveable parts for Jan 1–Mar 31, 2026
- [x] Dark / Light mode (preference saved)
- [x] Font size A− / A+ (preference saved)
- [x] Language toggle EN ↔ UA
- [x] Print layout (CSS)
- [x] Service Worker (offline caching)
- [x] PWA Manifest (installable)

### Next Steps
- [ ] English moveable parts for Jan–Feb + rest of March
- [ ] Add icons (192×192, 512×512 PNG in `icons/` folder)
- [ ] Great Compline (Ukrainian data available in prayer_data_2026.json)
- [ ] Matins, Hours, Presanctified Liturgy
- [ ] Remaining months as prayer-service.pp.ua publishes them

### Data Notes
- Source: prayer-service.pp.ua (Молитва Церкви)
- Calendar metadata covers full 2026 (feast ranks, tones, fasting)
- Ukrainian Vespers HTML covers Jan–Mar 2026 (90 days)
- Architecture: fixed opening (embedded) + moveable parts (JSON) = complete service
