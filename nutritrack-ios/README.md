# NutriTrack — Instalare pe iPhone

## Ce este acesta?

Un **PWA (Progressive Web App)** — se instalează pe home screen din Safari, rulează
full-screen fără bara browserului și funcționează offline. Din punct de vedere vizual
și funcțional se comportă ca o aplicație nativă. Nu necesită App Store sau cont Apple Developer.

---

## Instalare — 3 pași

### Pasul 1 — Găzduire gratuită pe GitHub Pages

> Trebuie să faci asta o singură dată. Dacă nu ai cont GitHub, creează-l gratis pe github.com.

1. Mergi pe **[github.com](https://github.com)** → **New repository**
2. Nume: `nutritrack` · Bifează **"Add a README file"** · Apasă **Create repository**
3. În repository, apasă **"uploading an existing file"**
4. Trage și adaugă **toate fișierele** din acest ZIP (dezarhivează-l mai întâi)
5. Apasă **"Commit changes"**
6. Mergi la **Settings → Pages → Source: "Deploy from a branch"**,
   Branch: `main`, Folder: `/ (root)` → **Save**
7. Așteaptă ~1 minut → vei primi link-ul:
   `https://USERUL-TAU.github.io/nutritrack/`

### Pasul 2 — Deschide în Safari pe iPhone

- Deschide **Safari** (nu Chrome, nu Firefox — obligatoriu Safari pentru instalare)
- Navighează la `https://USERUL-TAU.github.io/nutritrack/`

### Pasul 3 — Adaugă pe Home Screen

1. Apasă iconița **Partajare** (pătrat cu săgeată în sus) din bara Safari
2. Derulează în jos și apasă **"Adaugă la ecran de pornire"**
3. Lasă numele `NutriTrack` și apasă **Adaugă**

**Gata.** NutriTrack apare pe home screen cu iconița ei. La deschidere
rulează full-screen, exact ca o aplicație nativă.

---

## Note importante

| Funcție | Status pe iPhone |
|---|---|
| Jurnal nutrițional zilnic | ✅ Funcționează complet |
| Căutare alimente (Open Food Facts) | ✅ Necesită internet |
| Scanare cod de bare (cameră) | ✅ Necesită internet + permisiune cameră |
| Navigare între zile | ✅ Funcționează complet |
| Date salvate local (persistente) | ✅ localStorage |
| Funcționare offline | ✅ După prima vizită |
| Export Obsidian (scriere directă în vault) | ⚠️ Nu pe iOS Safari — folosești descărcarea .md |
| Reminder stretching | ✅ Funcționează complet |

### Export în Obsidian pe iPhone
File System Access API nu este disponibil în Safari iOS. Apasă **📤** →
**"Descarcă .md"** — fișierul se descarcă în Fișiere (Files). Apoi îl poți
muta manual în vault-ul Obsidian (dacă ai Obsidian pe iPhone, sau via iCloud/Sync).

### Backup date
Datele sunt în `localStorage` al Safari. Dacă ștergi "Safari → Setări → Sterge istoricul și datele",
datele se pierd. Fă export periodic via butonul 📤 din aplicație.

### Actualizări
Când actualizezi fișierele pe GitHub, iPhone-ul descarcă noua versiune automat la
următoarea deschidere a aplicației (service worker face update în background).

---

## Structura fișierelor

```
index.html        aplicația principală (CSS + JS inline)
sw.js             service worker (offline, caching)
manifest.json     configurare PWA (icon, culori, display)
icons/
  icon-120.png   iPhone (non-Retina)
  icon-152.png   iPad
  icon-180.png   iPhone (@3x, home screen icon)
  icon-192.png   Android / generic
  icon-512.png   splash screen / store
README.md         acest fișier
```
