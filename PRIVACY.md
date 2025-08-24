# Datenschutzerklärung – Scroll Tamer (Minimal 0.2×)

Stand: 2025-08-24

## Verantwortlicher
- Name: zerox80
- E‑Mail: rujbin@proton.me

## Kurzfassung
Diese Erweiterung verlangsamt ausschließlich das Scrollen im Browser. Sie sammelt **keine personenbezogenen Daten**, speichert **nichts dauerhaft** und sendet **keine Daten** an Server oder Dritte.

## Geltungsbereich
Diese Erklärung gilt für die Browser‑Erweiterung "Scroll Tamer (Minimal 0.2×)". Sie gilt nicht für die von Ihnen besuchten Websites, deren eigene Datenschutzbestimmungen maßgeblich sind.

## Welche Daten verarbeitet die Erweiterung?
- Die Erweiterung führt clientseitig ein Content‑Script aus, das Maus‑/Touchpad‑Scroll‑Ereignisse abfängt bzw. passiv korrigiert und daraus **nur technische Werte** (z. B. `deltaY`, `scrollTop`) in flüchtigem Arbeitsspeicher verarbeitet.
- Es werden **keine Seiteninhalte gelesen oder gespeichert**. Es erfolgt **keine Persistenz** (kein `storage`, keine Cookies).
- Es gibt **keine Netzwerkanfragen**. Die Erweiterung übermittelt **keine Daten** an Dritte.

## Berechtigungen und Zugriffe
- Das Content‑Script läuft auf `<all_urls>`, sehr früh (`run_at: document_start`) und in **allen Frames** (`all_frames: true`). Dies ist technisch erforderlich, um das Scrollverhalten konsistent zu beeinflussen.
- Es werden **keine zusätzlichen Berechtigungen** (z. B. für Storage, Tabs, Netzwerk) genutzt.

## Protokolle, Telemetrie, Netzwerk
- Es gibt **keine Telemetrie** und **keine** automatischen **Netzwerkzugriffe**. Die Erweiterung arbeitet vollständig **offline**.

## Fehlerberichte und Support
Wenn Sie uns per E‑Mail kontaktieren:
- Verarbeitete Daten: Ihre E‑Mail‑Adresse, der Inhalt Ihrer Nachricht sowie ggf. freiwillig übermittelte Diagnosedaten (z. B. Browser‑Version, URL, Beschreibung des Verhaltens).
- Zweck: Bearbeitung Ihrer Anfrage und Verbesserung der Erweiterung.
- Rechtsgrundlage: Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse an Kommunikation/Support) bzw. lit. b (vorvertragliche Kommunikation), je nach Kontext.
- Speicherdauer: Solange erforderlich zur Bearbeitung und Dokumentation der Anfrage; Löschwunsch per E‑Mail möglich.
- E‑Mail‑Dienst: Der E‑Mail‑Verkehr läuft über Proton (proton.me); deren Datenschutzhinweise sind zusätzlich maßgeblich.

## Weitergabe an Dritte / Drittländer
- Es findet **keine Weitergabe** durch die Erweiterung statt. Eine Übermittlung kann nur im Rahmen Ihrer aktiven Kontaktaufnahme via E‑Mail erfolgen (siehe oben).

## Ihre Rechte
Sie haben nach Maßgabe der DSGVO insbesondere das Recht auf **Auskunft**, **Berichtigung**, **Löschung**, **Einschränkung der Verarbeitung**, **Datenübertragbarkeit** sowie **Widerspruch**. 
Da die Erweiterung selbst keine personenbezogenen Daten verarbeitet oder speichert, beziehen sich diese Rechte im Regelfall nur auf Daten, die Sie uns aktiv (z. B. per E‑Mail) übermitteln. Zur Ausübung Ihrer Rechte kontaktieren Sie uns bitte unter: rujbin@proton.me.

## Änderungen dieser Datenschutzerklärung
Wir können diese Erklärung anpassen, wenn sich technische oder rechtliche Rahmenbedingungen ändern. Die jeweils aktuelle Fassung finden Sie im Repository der Erweiterung. Wesentliche Änderungen werden mit neuem Stand‑Datum kenntlich gemacht.
