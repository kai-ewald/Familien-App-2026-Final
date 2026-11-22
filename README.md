# Familien-Einkaufsliste – Neubau 1.0 (Testpaket)

**Keine Verbindung zu alten Projekten.** Die App ist absichtlich ohne Zugangsdaten ausgeliefert.

## Einrichtung

1. Ein **neues** Supabase-Projekt erstellen. Unter Authentication → URL Configuration die neue GitHub-Pages-URL als Redirect-URL zulassen. E-Mail-OTP/Magic-Link aktivieren.
2. `schema.sql` im SQL-Editor **dieses neuen Projekts** einmal ausführen.
3. `config.example.js` kopieren und in `config.js` umbenennen. Ausschließlich die neue Projekt-URL und den **öffentlichen anon/publishable Key** eintragen. Niemals `service_role` oder geheime Keys in die App schreiben.
4. Alle Dateien außer `schema.sql`, `README.md`, `config.example.js` gemeinsam in **ein neues GitHub-Repository** hochladen, GitHub Pages aus `main`/`root` aktivieren.
5. Die App öffnen, per E-Mail anmelden, neue Familie anlegen, mit zwei Geräten testen, erst dann Familienmitglieder einladen.

## Funktionsumfang dieses Testpakets

- Sechs vereinbarte Startseitenbereiche, mobile Oberfläche, installierbare Web-App (PWA-Manifest)
- Anmeldung mit E-Mail, Familiengruppen, einmalige Einladungslinks, Admin-Rechte
- Rezepte mit Zutaten, Anleitung und genau einem Gerichtefoto, getrennte Familienbildspeicherung
- PDF-Textimport und OCR für Rezeptfotos (manuelle Kontrolle notwendig); **kein automatischer Fotozuschnitt aus PDF**
- Wunschgerichte, Freigabe nach Portionenzahl, Zutatenübernahme nur bei Freigabe
- EL/TL/Vorratszutaten bleiben im Rezept, werden nicht eingekauft
- Wochenplan ohne erneute Zutatenübernahme, als gekocht markieren, Freigabe widerrufen
- Gemeinsame Einkaufsliste, Warengruppen, gleiche Artikel summiert, abhaken und Einkauf abschließen

## Bekannte Grenzen vor Freigabe

- Das Paket ist ein **ungetesteter Integrationsstand**, nicht als fertig abgenommen.
- Automatische strukturierte Zutatenextraktion aus beliebigen Fotos/PDFs ist noch nicht umgesetzt. PDF/OCR übernehmen zunächst Rohtext zur manuellen Prüfung.
- Offline-Bearbeitung und automatische Konfliktauflösung sind nicht enthalten; Aktualisierung erfolgt bei Navigation/Änderungen, nicht als laufende Realtime-Subscription.
- Rezeptbildauswahl aus mehrseitigen PDFs ist nicht implementiert; Bild wird separat hochgeladen.
- Einkaufsmengen werden für gleiche Einheit summiert, jedoch nicht automatisch zwischen g/kg oder ml/l umgerechnet.
- Die Sicherheitspolicies und RPCs müssen im neuen Supabase-Projekt mit mehreren Konten getestet und vor echtem Betrieb gehärtet werden.
