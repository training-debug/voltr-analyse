# VOLTR — Projektion & Diagnose Funnel

Statischer Funnel für GitHub Pages, Domain: `projektion.voltr.at`

## Funnel
Meta Ad → Projektion (Regler-Rechner) → E-Mail-Gate (Kit) → Ergebnis mit Zahlen, Charts, Meilensteinen → Brücke ("Warum stehst du nicht dort?") → Die Diagnose 29 € (Stripe) → Intake-Formular → PDF + Sprachnachricht in 48 h → Upsell 1:1 Coaching 349 €/Monat

## Dateien
- `index.html` — Rechner mit Reglern (Ziel, Gewicht, KFA, Erfahrung, Tage, Zeitraum) + E-Mail-Gate + Projektions-Ergebnis + Brücke zur Diagnose
- `diagnose.html` — Sales Page "Die Diagnose" (29 €), Struktur: Problem → Was/Warum → Lieferung → Coach → Passt das → Social Proof → Preis → Garantie → FAQ
- `intake.html` — Formular nach Zahlung (Projektion hängt automatisch an)
- `danke.html` — Bestätigung, setzt 48h-Erwartung
- `CNAME` — Custom Domain für GitHub Pages

## Deployment (einmalig, ~10 Min)
1. Neues GitHub-Repo anlegen (z. B. `voltr-projektion`), diese Dateien pushen.
2. Repo → Settings → Pages → Source: `main` branch, root. Speichern.
3. Settings → Pages → Custom domain: `projektion.voltr.at` eintragen.
4. Wix DNS: CNAME-Record anlegen: Host `projektion` → Wert `<dein-github-user>.github.io`
5. Sobald das Zertifikat da ist (bis 24 h): "Enforce HTTPS" aktivieren.

## Vor dem Livegang ersetzen
1. **`KIT_FORM_ID`** in `index.html` (1 Stelle): Kit → neues Form "Projektion" → ID aus der Embed-URL.
2. **`STRIPE_PAYMENT_LINK`** in `diagnose.html` (4 Stellen): Stripe → Payment Link, 29 €, Produktname "Die Diagnose". Bestätigungsseite: Weiterleitung zu `https://projektion.voltr.at/intake.html`.
3. **Social Proof** in `diagnose.html`: 3 Platzhalter durch echte Klienten-Zitate ersetzen (Vorname, Alter, Beruf). Keine erfundenen Zitate verwenden.
4. **Coach-Fotos**: 2 Platzhalter-Flächen (index: Motiv "Kalender", diagnose: Motiv "Nach der Session") — Shotlist siehe kampagne.md.
5. **FormSubmit aktivieren**: Intake einmal testweise absenden → Bestätigungslink an training@voltr.at klicken.

## Test-Checkliste
- [ ] Rechner: alle Regler + Segmente, Projektion berechnen
- [ ] E-Mail-Gate: Test-Mail landet in Kit
- [ ] Ergebnis: Zahlen plausibel (Cut + Aufbau je einmal testen), Charts rendern
- [ ] Diagnose-Seite → Stripe (Testmodus) → Redirect auf intake.html
- [ ] Intake absenden → Mail kommt an, Projektion ist angehängt
- [ ] Mobil testen (iPhone Safari), dort kommt der Traffic her
