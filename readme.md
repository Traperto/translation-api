# TranslationTool-API

## Hintergrund

Übersetzungen werden in einer JSON-Datei in nested objects gespeichert (siehe Beispiel [de.json](##Beispiel)). Dabei hat jede Übersetzung einen eindeutigen Pfad/Key der aus der sich aus den Keys des nested objects zusammensetzte.

Beispiel: Der Key für die Translation `Benutzername` lautet `USER.USERNAME`

```json	
"USER": {
    "USERNAME": "Benutzername",
}
```



## Aufgabenstellung

Implementiere eine API für ein TranslationTool. Die Auswahl der Programmiersprache ist dir überlassen.

Die API hat folgende Aufgaben:

- Übersetzen von diversen Sprachschnipseln in unterschiedliche Sprachen mittels GoogleTranslateAPI
- Festschreiben der Übersetzungen in die vorhanden Übersetzung-Dateien (richtige Einsortierung beachten)
- Optional: Übersetzung mittels DeepL API 

Die API benötigt lediglich einen Endpoint um die Übersetzung durchzuführen. Dabei sieht die Payload wie folgt aus:

```json	
{
  "sourcePath": "/Users/yourname/dev/trp/campus/src/client/angular/library/core/assets/i18n/",
  "sourceLanguage": "de",
  "targetLanguages": [ "sl", "bg", "en", "pt","cs","tr","hu","da","ro","de","sv","es","fr","hr","it","sk"],
  "translationItems": [
    { "key": "USER.USERNAME", "value": "Benutzername" },
    { "key": "DATE", "value": "Datum" },
    { "key": "ERROR.PAGE_NOT_FOUND.HEADLINE", "value": "Diese Seite konnten wir nicht finden."}
  ]
}
```

**Erläuterung der Payload**

- sourcePath: Hinter diesem Pfad liegen alle TranslationFiles (de.json, en.json, es.json etc..)
- sourceLanguage: Quellsprache
- targetLanguages: Zielsprache
- translationItems: Alle TranslationKeys die Übersetzt werden sollen, mit den dazugehörigen Sprachschnipseln in der Quellsprache.



## Beispiel 

**de.json**

``` json
{
  "DATE": "Datum",
  "USER": {
    "USERNAME": "Benutzername",
    "EMAIL": "E-Mail Adresse",
    "LOCATION": "Standort"
  },
  "ACTION": {
    "SAVE": "Speichern",
    "CANCEL": "Abbrechen",
    "EDIT": "Bearbeiten",
  },
  "ERROR": {
    "PAGE_NOT_FOUND": {
      "CODE": "404",
      "HEADLINE": "Diese Seite konnten wir nicht finden.",
      "DESCRIPTION": "Wir haben überall nach dieser Seite gesucht, konnten diese aber leider nicht finden. Bitte prüfen Sie die URL der Webseite."
    },
    "CONNECTION_LOST": {
      "HEADLINE": "Keine Internetverbindung",
      "TEXT": "Wir haben festgestellt, das aktuell keine Internertverbindung besteht.<br />Diese ist Voraussetzung für die Verwendung des Systems.<br /><br />Bitte die Internetverbindung prüfen."
    }
  }
}

```



