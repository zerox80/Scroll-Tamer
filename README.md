# Scroll Tamer (Minimal 0.2×)

Ultraleichtes Content‑Script, das die vertikale Scroll‑Geschwindigkeit global verlangsamt. Keine UI, kein Hintergrund‑Service‑Worker, keine Speicherung – nur ein einziges Skript, das früh auf allen Seiten läuft.


## Funktionen
 - Globales Verlangsamen auf 0.2× (20% der nativen Geschwindigkeit).
 - Läuft sehr früh in allen Seiten und Frames (`run_at: document_start`, `all_frames: true`).
 - Automatische Zielwahl: wählt das nächste vertikal scrollbare Element oder das Dokument (inkl. Shadow DOM).
 - Sanfte Korrektur: setzt temporär `scroll-behavior: auto` und `scroll-snap-type: none`; automatische Rücknahme nach ~320 ms.
 - Bypass: Alt gedrückt halten = nativ scrollen; Pinch‑Zoom (Ctrl) bleibt nativ; horizontales Scrollen per Shift+Wheel bleibt nativ.
 - Ressourcen‑schonend: Koalesziert pro Animation‑Frame und quantisiert auf ganze Pixel, um Mikro‑Jitter zu vermeiden.


 ## Installation (aus Quellcode)
 1. Öffne `chrome://extensions` (oder Pendant im Chromium‑Browser).
 2. Aktiviere den **Entwicklermodus**.
 3. Klicke **Entpackte Erweiterung laden** und wähle den Ordner dieses Projekts.
 4. Prüfe, dass die Erweiterung aktiviert ist, und lade betroffene Tabs neu.


 ## Verhalten & Steuerung
 - **Standard‑Faktor**: `FACTOR = 0.2` in `content.min.js` (≈ 20 % der nativen Geschwindigkeit).
 - **Moduswahl automatisch**:
   - `FACTOR < 0.75`: aktives Abfangen (`passive: false`) und Koaleszierung pro RAF, um Zwei‑Schritt‑Jitter zu vermeiden.
   - sonst: nachträgliche, passive Korrektur.
 - **Bypass/Shortcuts**:
   - **Alt** gedrückt halten: temporär natives Scrollen.
   - **Ctrl** (Pinch‑Zoom): bleibt nativ.
   - **Shift + Mausrad** (horizontal): bleibt nativ und wird nicht beeinflusst.


 ## Berechtigungen & Datenschutz
 - Content‑Script auf `<all_urls>`, sehr früh (`document_start`) und in allen Frames (`all_frames: true`).
 - Kein Storage, kein Tracking, keine Netzwerkanfragen, kein Remote‑Code.
 - Alle Verarbeitung bleibt lokal im Tab. Details: siehe [PRIVACY.md](./PRIVACY.md).


 ## Technische Details (Kurzüberblick)
 - Datei: `content.min.js`
   - Zielauswahl mit `closestScrollableY()` (inkl. Shadow‑DOM‑Aufstieg).
   - Passive Korrektur: misst die native Bewegung und addiert `moved * (FACTOR - 1)` auf das jeweilige Ziel.
   - Aktiver Abfang: normalisiert Deltas (`deltaMode`), verhindert Standard‑Scrollen, koalesziert pro `requestAnimationFrame` und quantisiert auf ganze Pixel (inkl. Rest‑Akkumulator).
   - Temporär `scroll-behavior: auto` und `scroll-snap-type: none` zur Vermeidung von Snap/Jitter (automatische Rücknahme nach ~320 ms).
 - Manifest: `manifest.json`
   - `content_scripts` auf `<all_urls>`, `run_at: document_start`, `all_frames: true`.


 ## Projektstruktur
 - `manifest.json` – MV3‑Konfiguration (nur Content‑Script)
 - `content.min.js` – Minimales Scroll‑Tuning (FACTOR = 0.2)
 - `PRIVACY.md` – Datenschutzerklärung
 - `icons/` – Icons (16/48/128)


 ## Entwicklung
 - Kein Build‑Schritt nötig. Dateien ändern und die Erweiterung auf `chrome://extensions` **neu laden**.
 - Den Faktor anpassen: In `content.min.js` die Zeile `const FACTOR = ...` editieren und Tabs neu laden.


 ## Bekannte Grenzen & Tipps
 - Web‑Apps mit eigenem Scrolling (virtuelle Listen, Canvas) können sich anders verhalten; nutze bei Bedarf den **Alt‑Bypass**.
 - An Kanten (Top/Bottom) wird die Korrektur automatisch gedämpft.
 - Bei komplett abgefangenen Containern greift die Dokument‑Ebene als Fallback.


 ## Version
 - Aktuelle `manifest.json`‑Version: `1.3.0`.


## Support & Kontakt
 - Probleme oder Vorschläge? Bitte Browser‑Version, Seite/Host, reproduzierbare Schritte und erwartetes vs. tatsächliches Scroll‑Verhalten angeben.
 - Maintainer: zerox80
 - E‑Mail: rujbin@proton.me
