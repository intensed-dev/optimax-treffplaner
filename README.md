# Optimax Treffplaner

Statischer Kalender mit DaisyUI, FullCalendar und GitHub-Milestone-Integration.

## Eigene Termine

Termine werden in `data/events.json` gepflegt:

```json
{
  "events": [
    {
      "id": "teamtreffen-01",
      "title": "Teamtreffen",
      "start": "2026-12-03T18:30:00",
      "end": "2026-12-03T19:30:00",
      "allDay": false,
      "location": "Discord",
      "description": "Themen für das nächste Update besprechen.",
      "url": "https://example.com"
    }
  ]
}
```

Jeder Eintrag braucht eine eindeutige `id`, einen `title` und ein `start`-Datum (ISO 8601). `end`, `allDay`, `location`, `description` und `url` sind optional. Ganztägige Termine verwenden beispielsweise `2026-12-03`; Termine mit Uhrzeit `2026-12-03T18:30:00`.

## GitHub Milestones

Die Seite lädt Milestones öffentlich von `DerAnonymeHans/eFinanzer-v2` über die GitHub REST API. Milestones mit Fälligkeitsdatum erscheinen im Kalender, undatierte Milestones werden separat angezeigt. Kein Token erforderlich, solange das Repository öffentlich ist.

## Kalender

Monats-, Wochen- und Listenansicht; Filter für eigene Termine und Milestones; Details beim Anklicken; manuelle Aktualisierung.

## Hosting

Für GitHub Pages geeignet. Zum lokalen Testen einen lokalen Webserver verwenden, da `fetch()` JSON-Dateien nicht zuverlässig über `file://` laden kann.

## Technologien

DaisyUI 5 · Tailwind CSS Browser CDN · FullCalendar 6 · Vanilla JavaScript