# Project42 — Benutzerhandbuch

Project42 ist ein privater, selbst gehosteter Gruppen-Fitness-Tracker für Gewichtsverlust, Gewohnheiten, Challenges und Aktivitätstracking. Diese Anleitung erklärt alles, was du wissen musst.

> English version: [README.md](README.md)

---

## Inhaltsverzeichnis

1. [Erste Schritte](#erste-schritte)
2. [Dashboard](#dashboard)
3. [Gewichtstracking](#gewichtstracking)
4. [Gewohnheiten (Habits)](#gewohnheiten-habits)
5. [Challenges](#challenges)
6. [Aktivitäts-Feed](#aktivitäts-feed)
7. [Scoreboard](#scoreboard)
8. [Rezepte](#rezepte)
9. [Profil & Einstellungen](#profil--einstellungen)
10. [Home-Assistant-Integration](#home-assistant-integration)
11. [Withings-Integration](#withings-integration)
12. [Share-Seite](#share-seite)

---

## Erste Schritte

1. Du brauchst einen **Einladungscode** vom Gruppen-Admin, um dich zu registrieren. (Der allererste Benutzer registriert sich ohne Code und wird automatisch Admin.)
2. Gehe zur App-URL → **Registrieren** → Namen, E-Mail, Passwort und Einladungscode eingeben.
3. Richte dein Profil ein (Größe, Startgewicht, Zielgewicht), damit Scoreboard und BMI-Berechnungen korrekt funktionieren.

---

## Dashboard

Dein persönlicher Startbildschirm. Er zeigt:

- **Gewicht eintragen** — trage das heutige Gewicht direkt vom Dashboard aus ein
- **Aktuelles Gewicht & Streak** — wie viele aufeinanderfolgende Tage du eingetragen hast
- **Heutige Gewohnheiten** — die für heute geplanten Habits mit Einzelklick-Abhaken
- **Aktive Challenges** — verbleibende Tage in jeder Challenge, der du beigetreten bist
- **Letzte Aktivitäten** — neueste Aktionen der ganzen Gruppe
- **Rangliste** — schneller Blick, wer vorne liegt
- **Zitat des Tages** — tägliches Motivationszitat (kann im Profil deaktiviert werden)

### Dashboard anpassen

Tippe oben rechts auf **Anpassen**, um Widgets ein-/auszublenden und per Drag & Drop in die gewünschte Reihenfolge zu bringen. Tippe auf **Fertig**, um zu speichern.

---

## Gewichtstracking

Wähle **Gewicht** in der Navigation.

### Gewicht eintragen

Fülle aus:
- **Gewicht (kg)** — Pflichtfeld
- **Datum** — Standard: heute
- **Körperfett %** — optional
- **Notiz** — optional (z. B. „nach dem Training")

Tippe auf **Eintrag hinzufügen**.

### Diagramme & Statistiken

Die Seite zeigt dein Gewicht als Verlaufsdiagramm sowie aktuelles Gewicht, Gesamtverlust, Streak und Anzahl der Einträge.

### Einträge bearbeiten & löschen

Jeder Eintrag in der Liste hat Schaltflächen für **Bearbeiten** und **Löschen**. Gelöschte Einträge sind endgültig.

### Import / Export

- **Daten exportieren** — lädt alle deine Gewichtseinträge als CSV herunter
- **Vorlage herunterladen** — leere CSV zum Ausfüllen und Importieren
- **CSV importieren** — lade eine ausgefüllte CSV hoch; die App erkennt Datumsformate automatisch (YYYY-MM-DD, DD.MM.YYYY, MM/DD/YYYY usw.)

---

## Gewohnheiten (Habits)

Wähle **Gewohnheiten** in der Navigation.

### Gewohnheit erstellen

Tippe auf **+ Gewohnheit hinzufügen** und fülle aus:
- **Name** — z. B. „Wasser trinken", „Morgenrunde"
- **Farbe** — für die Kalenderansicht
- **Häufigkeit** — wähle eine:
  - *Täglich* — erscheint jeden Tag
  - *Bestimmte Tage* — wähle Wochentage aus
  - *X-mal pro Woche* — erscheint täglich, erfordert aber nur N Abhakungen pro Woche

### Gewohnheiten abhaken

Die für heute geplanten Gewohnheiten erscheinen unter **Heutige Gewohnheiten**. Tippe auf die Checkbox, um eine zu erledigen. Dein aktueller Streak wird als Badge angezeigt.

### Wochenübersicht

Das Kalenderraster zeigt die letzten 7 Tage — grün = erledigt, grau = verpasst, leer = nicht geplant.

### Gewohnheiten verwalten

Unter **Gewohnheiten verwalten** kannst du Habits bearbeiten, archivieren oder löschen. Archivierte Gewohnheiten behalten ihre Geschichte, erscheinen aber nicht mehr in der Tagesansicht. Du kannst sie später wiederherstellen.

---

## Challenges

Wähle **Challenges** in der Navigation.

Challenges gibt es in zwei Typen:

### Check-in-Challenges (täglich)

Jeder Teilnehmer tippt einmal pro Tag auf **Heute einchecken**. Ideal für Streaks, Konsistenzziele oder Gruppengewohnheiten (z. B. „30-Tage-Plank-Challenge").

### Mengen-Challenges (km, Min., Wiederholungen…)

Jeder Teilnehmer trägt einen Zahlenwert ein (z. B. 20 km Radfahren). Mehrere Einträge pro Tag sind erlaubt. Das Leaderboard sortiert nach dem kumulierten Gesamtwert. Ideal für Distanzziele, zeitbasierte Challenges oder Wiederholungszähler.

### Challenge erstellen

Tippe auf **+ Neue Challenge** und fülle aus:
- **Name** — z. B. „100-km-Radchallenge"
- **Beschreibung** — optionales Ziel
- **Start- / Enddatum**
- **Typ** — Check-in oder Menge
- *(Nur Menge)* **Ziel** und **Einheit** — z. B. 100 km

### Beitreten & Verlassen

Challenge-Karte öffnen → **Beitreten** tippen. Du kannst jederzeit austreten.

### Aktivität eintragen (Mengen-Challenges)

In der Challenge: **Menge** eingeben, optional **Datum** (Standard: heute) und **Notiz**, dann auf **Eintragen** tippen. Deine Einträge erscheinen im Aktivitätslog und dein Gesamtwert aktualisiert sich im Leaderboard.

### Leaderboard

Zeigt alle Teilnehmer sortiert nach Gesamtwert (Mengen-Typ) oder Anzahl der Check-ins (Check-in-Typ).

---

## Aktivitäts-Feed

Wähle **Feed** in der Navigation.

Zeigt eine chronologische Liste der neuesten Aktivitäten aller — Gewichtseinträge, erledigte Gewohnheiten, neue Rezepte und Challenge-Check-ins. Mit dem Dropdown kannst du nach den letzten 3, 7, 14 oder 30 Tagen filtern.

---

## Scoreboard

Wähle **Scoreboard** in der Navigation.

Rangliste nach **gesamtem Gewichtsverlust** (Startgewicht minus aktuelles Gewicht). Zeigt außerdem BMI, FFMI, Streak und Anzahl der Einträge pro Nutzer.

Wechsle zwischen **Alle** (Gruppenansicht) und **Nur ich** (deine eigene Entwicklung).

---

## Rezepte

Wähle **Rezepte** in der Navigation. Teile Lieblingsgerichte mit der Gruppe — Zutaten, Zubereitung, Makros und Fotos.

---

## Profil & Einstellungen

Wähle **Profil** in der Navigation.

### Persönliche Daten

- **Name, E-Mail** — grundlegende Kontodaten
- **Größe, Startgewicht, Zielgewicht** — für BMI, FFMI und Scoreboard-Berechnungen
- **Geburtsdatum, Geschlecht** — für FFMI-Berechnung
- **Telegram-Nutzername** — optional; der Bot nutzt das, um dich in Gruppennachrichten zu markieren

### Darstellung

- **Tägliches Zitat anzeigen** — Motivationszitat auf dem Dashboard ein-/ausschalten
- **Bannerfarbe** — Akzentfarbe für deine öffentliche Profilseite
- **Bio** — Kurztext auf deiner öffentlichen Profilseite

### Passwort zurücksetzen

Falls du dein Passwort vergessen hast, bitte den Admin, im Admin-Panel einen Reset-Token für dich zu erstellen. Du erhältst dann einen Token, den du unter `/reset-password` verwenden kannst.

---

## Home-Assistant-Integration

Verbinde die **Home Assistant Companion App** (iOS oder Android), um deine täglichen Gesundheitsdaten — Schritte, Distanz, Stockwerke, aktive Kalorien und Herzfrequenz — direkt in Project42 zu übertragen.

### Funktionsweise

1. Dein Smartphone oder Smartwatch synchronisiert Gesundheitsdaten mit der Home-Assistant-Companion-App
2. Eine HA-Automation läuft zweimal täglich (standard: 12:00 + 22:00 Uhr)
3. Die Automation ruft den Webhook von Project42 mit deinen aktuellen Sensorwerten auf
4. Project42 speichert die Daten und zeigt sie in deinem Profil an

### Einrichtung — 4 Schritte

#### Schritt 1 — Einmalige Änderung in configuration.yaml

Füge Folgendes **einmalig** zu deiner HA-`configuration.yaml` hinzu (gilt für alle Nutzer der gleichen HA-Instanz):

```yaml
rest_command:
  http_post:
    url: "{{ url }}"
    method: POST
    content_type: "application/json"
    payload: "{{ payload }}"
```

> **Hast du bereits einen `rest_command:`-Block?** Füge **keinen zweiten** hinzu — YAML erlaubt keine doppelten Schlüssel und HA wirft einen Fehler. Füge stattdessen nur den `http_post:`-Eintrag in deinen bestehenden Block ein:
>
> ```yaml
> rest_command:
>   mein_bestehender_befehl:   # was bereits vorhanden war
>     ...
>   http_post:                 # nur das hier hinzufügen
>     url: "{{ url }}"
>     method: POST
>     content_type: "application/json"
>     payload: "{{ payload }}"
> ```

Danach: **Entwicklerwerkzeuge → Schnell neu laden → REST-Befehl**.

#### Schritt 2 — Blueprint importieren

In HA: **Einstellungen → Automatisierungen → Blueprints → Blueprint importieren**

Diese URL einfügen:
```
https://raw.githubusercontent.com/dhuuk42/Project42Pub/main/project42_blueprint.yaml
```

#### Schritt 3 — Webhook-URL holen

1. Project42 öffnen → **Profil** → **Home Assistant**
2. Auf **Webhook-Token generieren** tippen
3. Die angezeigte vollständige URL kopieren — sie sieht aus wie `https://huukdev.de/api/webhooks/ha/abc123...`

Halte diese URL geheim — sie erlaubt Schreibzugriff auf deine Gesundheitsdaten.

#### Schritt 4 — Automation erstellen

1. In HA: **Einstellungen → Automatisierungen → Automatisierung erstellen → Aus Blueprint**
2. **Project42 Daily Sync** auswählen
3. Ausfüllen:
   - **Webhook-URL** — deine persönliche URL aus Schritt 3
   - **Schritte-Sensor** — nach deinem Gerätenamen suchen (z. B. `iphone_16pro_deinname`)
   - **Distanz-Sensor** — optional
   - **Stockwerk-Sensor** — optional
   - **Aktive Kalorien** — optional (nur Apple Watch)
   - **Herzfrequenz-Sensor** — optional (nur Apple Watch)
   - **Synchronisierungsintervall** — wie oft innerhalb des aktiven Zeitfensters synchronisiert wird (min. 15 Min., Standard 30 Min.)
   - **Aktives Zeitfenster Start / Ende** — Synchronisierung läuft nur in diesem Zeitraum (Standard: 08:00–22:00 Uhr)
4. Speichern

Jede Person erstellt **ihre eigene Automation** aus demselben Blueprint mit ihrer eigenen Webhook-URL und ihren eigenen Sensoren.

### Gesundheitssensoren in der Companion App aktivieren

#### iOS

1. HA Companion App → **Einstellungen** → **Companion App** → **Gesundheit**
2. Aktivieren: Schritte, Distanz (Gehen + Laufen), Zurückgelegte Treppen
3. Apple-Watch-Nutzer: zusätzlich Aktiv verbrauchte Energie und Herzfrequenz aktivieren
4. Die iOS-Berechtigungen bestätigen

#### Android

1. HA Companion App → **Einstellungen** → **Companion App** → **Sensoren verwalten**
2. Nach „Schritt" suchen → **Schrittzähler** aktivieren
3. Health-Connect-Berechtigungen bestätigen

### Verfügbare Sensoren nach Gerät

| Sensor | Nur iPhone | iPhone + Apple Watch |
|--------|------------|----------------------|
| Schritte | ✓ | ✓ |
| Distanz | ✓ (Meter) | ✓ (Meter) |
| Zurückgelegte Stockwerke | ✓ | ✓ |
| Aktive Kalorien | — | ✓ |
| Herzfrequenz | — | ✓ |

> iOS meldet Distanz in **Metern** — der Blueprint verarbeitet das automatisch.

### Sensor-Entity-IDs finden

1. HA → **Entwicklerwerkzeuge → Zustände**
2. Nach deinem Gerätenamen filtern (z. B. `iphone_16pro_mirco`)

Typische Muster:
```
sensor.{gerätename}_steps
sensor.{gerätename}_distance
sensor.{gerätename}_floors_ascended
sensor.{gerätename}_active_energy     ← nur Apple Watch
sensor.{gerätename}_heart_rate        ← nur Apple Watch
```

### Fehlerbehebung

| Problem | Lösung |
|---------|--------|
| Sensoren zeigen „unavailable" | Gesundheitsberechtigungen in der Companion App erteilen; Sensoren aus- und wieder einschalten |
| Kalorien/Herzfrequenz fehlen | Erfordert Apple Watch, die mit Apple Health synchronisiert |
| Webhook gibt 401 zurück | Token wurde neu generiert — neue URL unter Profil → Home Assistant holen |
| Schritte sind 0 | iOS-Sensoren aktualisieren nach Plan; Wert zuerst in Entwicklerwerkzeuge → Zustände prüfen |
| Automation-Trace zeigt Template-Fehler | Sicherstellen, dass REST-Befehl nach dem Bearbeiten der configuration.yaml neu geladen wurde |

---

## Withings-Integration

Verbinde eine **Withings-Waage** (Body+, Body Comp usw.), um Gewicht, Körperfett, Blutdruck, Herzfrequenz, Aktivität und Schlafdaten automatisch zu importieren.

1. Profil → **Withings** → **Withings-Konto verbinden**
2. Im Withings-Konto anmelden und Zugriff gewähren
3. Auf **Jetzt synchronisieren** tippen, um Daten zu importieren

Importierte Gewichtseinträge erscheinen in deiner Gewichtshistorie und werden im Scoreboard berücksichtigt.

---

## Share-Seite

Erstelle einen **öffentlichen Nur-Lese-Link**, um deine Fortschritte mit Familie oder Freunden zu teilen — kein Konto erforderlich.

1. Profil → **Familienfreigabe-Link** → **Link generieren**
2. Link kopieren und teilen
3. Der Empfänger sieht aktuelles Gewicht, Gesamtverlust, Streak und Zielfortschritt
4. **Link widerrufen** tippen, um den Link jederzeit zu deaktivieren

---

*Project42 ist selbst gehostet und privat — deine Daten verlassen niemals den Server der Gruppe.*
