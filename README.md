# Optimax Treffplaner

Ein statischer Kalender mit DaisyUI, FullCalendar und einer GitHub-Milestone-Quelle.

## Funktionen

- Eigene Termine aus `data/events.json`
- GitHub Milestones aus `DerAnonymeHans/eFinanzer-v2`
- Monats-, Wochen- und Listenansicht
- Filter für eigene Termine und GitHub-Milestones
- Undatierte Milestones werden separat angezeigt
- Läuft als statische Website, z. B. mit GitHub Pages

## Eigene Termine eintragen

Bearbeite `data/events.json`. Beispiel:

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
      "description": "Themen für das nächste Update besprechen."
    }
  ]
}
```

- `id`: eindeutige Kennung
- `title`: Titel im Kalender
- `start`: Datum oder Datum mit Uhrzeit (ISO 8601)
- `end`: optionales Enddatum bzw. Ende mit Uhrzeit
- `allDay`: `true` für ganztägige Termine, sonst `false`
- `location`, `description`, `url`: optional

## GitHub-Milestones

Die Website fragt beim Laden die öffentliche GitHub-API ab:

`https://api.github.com/repos/DerAnonymeHans/eFinanzer-v2/milestones?state=all&per_page=100`

Milestones mit `due_on` werden als Kalendereinträge dargestellt. Milestones ohne Fälligkeitsdatum erscheinen separat in der Seitenleiste. Die API wird direkt vom Browser aufgerufen; ein Token ist für ein öffentliches Repository nicht erforderlich.

## Lokal testen

Die Seite muss über einen Webserver aufgerufen werden, da Browser `fetch()` auf lokale JSON-Dateien via `file://` blockieren. GitHub Pages eignet sich direkt für das Hosting.

## Technologien

- DaisyUI 5
- Tailwind CSS Browser CDN
- FullCalendar 6
- Vanilla JavaScript
