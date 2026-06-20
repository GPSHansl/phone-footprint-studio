# Smartphone Größenvergleich

Ein kleines, browserbasiertes Tool zum Vergleichen von Smartphone-Abmessungen auf einer A4-Vorschau.

Die Anwendung läuft ohne Build-Schritt direkt im Browser. Smartphone-Daten können lokal bearbeitet, aus Beispieldaten geladen oder aus einer JSON-Liste synchronisiert werden.

## Funktionen

- Vergleich von zwei Smartphones in einer A4-SVG-Vorschau
- Suche und Auswahl über Eingabefelder mit Vorschlagsliste
- Editierbare, scrollbare Tabelle für Smartphone-Daten
- Lokale Speicherung im Browser per `localStorage`
- Laden von Beispieldaten oder Synchronisierung aus einer JSON-Datei
- SVG-Export und Druckansicht

## Dateien

- `index.html`: komplette Anwendung inklusive eingebetteter Beispieldaten
- `smartphones-db.json`: externe JSON-Liste mit Beispielgeräten
- `LICENSE`: Lizenztext

## Verwendung

### Direkt lokal

`index.html` kann direkt im Browser geöffnet werden.

Hinweis: Einige Browser blockieren `fetch` auf lokale `file://`-Dateien. Deshalb nutzt die App für die integrierten Beispieldaten eine eingebettete Fallback-Liste.

### Mit lokalem Webserver

Für das Laden von `smartphones-db.json` per URL ist ein kleiner lokaler Webserver sinnvoll.

Beispiel mit Python:

```powershell
python -m http.server 8123
```

Danach im Browser öffnen:

```text
http://127.0.0.1:8123/
```

## JSON-Format

Die Smartphone-Liste kann entweder direkt ein Array sein oder ein Objekt mit dem Feld `smartphones`.

Beispiel:

```json
{
  "smartphones": [
    {
      "id": "a55",
      "name": "Samsung Galaxy A55",
      "width": 77.4,
      "height": 161.1,
      "depth": 8.2
    }
  ]
}
```

## Datenhaltung

Änderungen an Geräten und die letzte Synchronisierung werden lokal im Browser gespeichert. Wenn bereits Daten im `localStorage` liegen, überschreiben diese den ursprünglichen Startzustand.

## Lizenz

Dieses Projekt steht unter der Unlicense und wird "AS IS" ohne Gewähr bereitgestellt. Details stehen in `LICENSE`.
