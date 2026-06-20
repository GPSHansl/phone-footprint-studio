# Smartphone Größenvergleich

Browserbasiertes Tool zum Vergleichen von Smartphone-Abmessungen auf einer A4-Vorschau.

Die Anwendung läuft ohne Build-Schritt direkt im Browser. Geräte können lokal gepflegt, aus Beispieldaten geladen oder aus einer JSON-Liste synchronisiert werden.

## Überblick

- Vergleich von zwei Smartphones in einer A4-SVG-Vorschau
- Suche und Auswahl über Dropdown-Eingabefelder mit Vorschlagsliste
- Editierbare und scrollbare Gerätetabelle im Einstellungsdialog
- Lokale Speicherung im Browser per `localStorage`
- Laden von Beispieldaten oder Synchronisierung aus einer JSON-Datei
- SVG-Export und Druckansicht

## Projektdateien

- `index.html` enthält die komplette Anwendung inklusive eingebetteter Beispieldaten
- `smartphones-db.json` enthält eine externe JSON-Liste mit Beispielgeräten
- `LICENSE` enthält die Public-Domain-Lizenz mit `AS IS`-Hinweis

## Schnellstart

### Direkt im Browser

`index.html` kann direkt geöffnet werden.

Wichtig: Einige Browser blockieren `fetch` auf lokale `file://`-Dateien. Deshalb nutzt die App für die integrierten Beispieldaten zusätzlich eine eingebettete Fallback-Liste.

### Mit lokalem Webserver

Für das Laden von `smartphones-db.json` per URL ist ein kleiner lokaler Webserver die sauberste Variante.

Beispiel mit Python:

```powershell
python -m http.server 8123
```

Danach im Browser öffnen:

```text
http://127.0.0.1:8123/
```

## JSON-Format

Die Geräteliste kann entweder direkt ein Array sein oder ein Objekt mit dem Feld `smartphones`.

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

Änderungen an Geräten und Informationen zur letzten Synchronisierung werden lokal im Browser gespeichert. Wenn bereits Daten im `localStorage` vorhanden sind, überschreiben sie den ursprünglichen Startzustand.

## Lizenz

Dieses Projekt steht unter der MIT Lizenz und wird `AS IS` ohne Gewähr bereitgestellt. Details stehen in `LICENSE`.
