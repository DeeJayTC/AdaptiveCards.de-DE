---
title: Text-Features
author: matthidinger
ms.author: mahiding
ms.date: 11/09/2017
ms.topic: article
ms.openlocfilehash: ac8ec0c48e06377ebd17f1b31abe463c48809fe3
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553612"
---
# <a name="text-features"></a>Text-features

`TextBlock` bietet einige erweiterten Funktionen zum Formatieren und den Text lokalisieren.

## <a name="markdown"></a>Markdown
Zur Unterstützung von Inline-Markup mit Adaptive Cards unterstützen eine **Teilmenge** von Markdown-Syntax.

_Unterstützt_

| Textstil      | Markdown |
|-----------------|-----|
| **Fett**        | ```**Bold**``` |
| _Kursiv_        | ```_Italic_``` |
| Liste mit Aufzählungszeichen     | ```- Item 1\r- Item 2\r- Item 3``` | 
| Nummerierte Liste   | ```1. Green\r2. Orange\r3. Blue``` |
| Hyperlinks      | ```[Title](url)``` |

_Nicht unterstützt_

* Header
* Tabellen
* Abbilder
* Alle Elemente nicht in der obigen Tabelle

### <a name="markdown-example"></a>Markdown-Beispiel

Die folgenden Nutzlast würde etwa wie folgt gerendert:

![bildschirmabbildung von markdown](media/text-features/markdown.png)

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "This is some **bold** text"
        },
        {
            "type": "TextBlock",
            "text": "This is some _italic_ text"
        },
        {
            "type": "TextBlock",
            "text": "- Bullet \r- List \r",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "1. Numbered\r2. List\r",
            "wrap": true
        },
        {
            "type": "TextBlock",
            "text": "Check out [Adaptive Cards](http://adaptivecards.io)"
        }
    ]
}
```

## <a name="datetime-formatting-and-localization"></a>Formatieren von Datum/Uhrzeit und Lokalisierung

Manchmal wird nicht man die Zeitzone des Benutzers empfangen von der Karte daher mit Adaptive Cards bietet `DATE()` und `TIME()` Formatierungsfunktionen, um die Uhrzeit auf dem Zielgerät automatisch zu lokalisieren.

### <a name="datetime-example"></a>Datum/Uhrzeit-Beispiel

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Your package will arrive on {{DATE(2017-02-14T06:00:00Z, SHORT)}} at {{TIME(2017-02-14T06:00:00Z)}}",
            "wrap": true
        }
    ]
}
```

Die oben genannten Karte wird angezeigt: 

> **Das Paket wird am Dienstag, 14. Februar 2017 um 06:00 Uhr angezeigt.**

### <a name="datetime-function-rules"></a>Datum/Uhrzeit – Funktionsregeln

Es gibt einige Regeln ordnungsgemäß interpretieren die der Datums-/Uhrzeitfunktionen auf jeder Plattform. Klicken Sie dann die unformatierte Zeichenfolge für den Benutzer angezeigt wird, und niemand möchte, die, wenn die Regeln nicht erfüllt sind.

1. **Groß-/ KLEINSCHREIBUNG** (muss Großbuchstaben)
1. **KEINE Leerzeichen** zwischen der `{{`, `}}`, oder runden Klammern
1. **STRENGE [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATIERUNG** (Siehe Beispiele unten)
1. **MUSS** ein gültiges Datum und Uhrzeit

### <a name="valid-formats"></a>Gültige Formate

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a>Param-datumsformatierung

Für Daten kann ein optionaler Parameter zum Formatieren der Ausgabe angegeben werden.


|       Format        |            Beispiel            |
|---------------------|-------------------------------|
| `COMPACT` (Standard) |          "2/13/2017"          |
|       `SHORT`       |     "Mon, 13. Februar 2017"     |
|       `LONG`        | "Montag, 13. Februar 2017" |

