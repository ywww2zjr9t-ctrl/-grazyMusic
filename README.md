# grazyMusic – Musikplayer Version 001.1

Eigenständige Progressive Web App, abgeleitet aus der funktionierenden **wir 004.3**. Wiedergabe, kompakte Playlist, Favoriten, Offline-Downloads, Löschbestätigung, Sammeldownload, Pull-to-Refresh und GitHub-Actions-Playlist-Erstellung bleiben in ihrer Bedienlogik unverändert. Name, freundliches Farbschema, Icons, PWA-Identität und getrennte Speicher-/Cache-Namen stammen aus 001.0. Neu in 001.1 ist die große Coveransicht durch Antippen des Covers; erneutes Antippen führt zur Playlist zurück. Die Wiedergabe läuft unverändert weiter.

## Neues Repository einrichten

1. Neues **öffentliches** GitHub-Repository anlegen, empfohlen: `grazyMusic` (nicht das Repository von `wir` verwenden).
2. **Alle Dateien und Ordner aus diesem ZIP** in die Wurzel des neuen Repositories hochladen, einschließlich `.github/workflows/update-playlist.yml` (versteckten Ordner nicht übersehen).
3. In **Settings → Pages** die Veröffentlichung über **Deploy from a branch**, `main`, `/ (root)` aktivieren.
4. In **Settings → Actions → General → Workflow permissions** nötigenfalls **Read and write permissions** aktivieren, damit der Workflow `playlist.json` committen darf.
5. Später Musikdateien in `audio/` hochladen. Der Workflow erstellt `playlist.json` automatisch. Der erste Upload einer Audiodatei legt den Ordner an; `audio/` und `playlist.json` sind daher bewusst noch nicht im Paket.
6. Auf dem Gerät die neue Pages-Adresse aufrufen und als Web-App zum Home-Bildschirm hinzufügen. Die bestehende App `wir` bleibt separat.

## Vollständiger Upload – 12 Dateien

- `index.html`
- `style.css`
- `app.js`
- `sw.js`
- `manifest.webmanifest`
- `version.json`
- `generate_playlist.py` (inhaltlich unverändert)
- `README.md`
- `icons/icon-192.png`
- `icons/icon-512.png`
- `icons/apple-touch-icon.png`
- `.github/workflows/update-playlist.yml` (inhaltlich unverändert)

**Unverändert aus `wir` 004.3:** `generate_playlist.py`, `.github/workflows/update-playlist.yml`; außerdem bleiben HTML-Struktur, Wiedergabesteuerung und Playlist-Logik erhalten. **Gegenüber 001.0 geändert:** `index.html`, `style.css`, `app.js`, `sw.js`, `version.json`, `README.md`. **Unverändert:** `manifest.webmanifest`, `generate_playlist.py`, alle drei Icons und `.github/workflows/update-playlist.yml`.

## Hinweise

- Dieses Paket enthält **keine Musikdateien**; das neue Repository bekommt eine eigene Sammlung.
- Bei neuen App-Versionen `version.json`, die Versionskennung in `app.js`, die Versionsparameter in `index.html` und die Shell-Cachekennung samt Versionsparametern in `sw.js` gemeinsam aktualisieren.
- Beide Apps verwenden eigene Cache- und LocalStorage-Namen. Browserdaten sind dennoch von der jeweiligen Origin und dem Installationskontext abhängig.
- Nach dem Hochladen GitHub Actions und Pages auf erfolgreiche Ausführung prüfen. Die Aktualisierungsfunktion setzt eine erreichbare `version.json` voraus.
- Offline-Audio kann vom Browser bei Speicherdruck entfernt werden.

## Kurze Benutzerhilfe

Cover antippen: große Coveransicht ohne Playlist; erneut tippen: normale Ansicht. Titel antippen: abspielen. Vier Tasten: zurück, Play/Pause, Stop, weiter. Herz: Favorit. Pfeil am Titel: offline speichern; Häkchen: Löschdialog mit „Titel behalten“ und „Titel löschen“. Pfeil in der Playlist-Kopfzeile: fehlende Titel gemeinsam herunterladen. Obere Beschriftungen antippen oder von oben herunterziehen: Musik und App-Version prüfen.

## Update von grazyMusic 001.0 auf 001.1

Ersetze im bestehenden **grazyMusic**-Repository nur `index.html`, `style.css`, `app.js`, `sw.js`, `version.json` und `README.md`. Die anderen sechs Dateien bleiben unverändert; `audio/` und eine bestehende `playlist.json` dürfen nicht gelöscht oder überschrieben werden. Das Originalprojekt **wir** bleibt unangetastet.
