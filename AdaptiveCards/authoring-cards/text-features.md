---
title: Textmerkmale
author: matthidinger
ms.author: mahiding
ms.date: 11/09/2017
ms.topic: article
ms.openlocfilehash: f7ea40b80df4d976c0a8a86b15254018fdf2fac6
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "77454873"
---
# <a name="text-features"></a>Textmerkmale

`TextBlock` bietet einige erweiterte Features zum Formatieren und Lokalisieren von Text.

## <a name="markdown"></a>Markdown
Damit Inline-Markup möglich ist, unterstützen adaptive Karten eine **Teilmenge** an Markdown-Syntax.

_Unterstützt_

| Textstil      | Markdown |
|-----------------|-----|
| **Fett**        | ```**Bold**``` |
| _Kursiv_        | ```_Italic_``` |
| Aufzählung     | ```- Item 1\r- Item 2\r- Item 3``` | 
| Nummerierte Liste   | ```1. Green\r2. Orange\r3. Blue``` |
| Hyperlinks      | ```[Title](url)``` |

_Nicht unterstützt_

* Header
* Tabellen
* Abbilder
* Alle in der obigen Tabelle nicht genannten Elemente

### <a name="markdown-example"></a>Markdown-Beispiel

Die folgende Nutzlast rendert etwa Folgendes:

![Markdown-Screenshot](media/text-features/markdown.png)

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

## <a name="datetime-formatting-and-localization"></a>Datums-/Uhrzeitformat und Lokalisierung

Es kann vorkommen, dass du die Zeitzone des Benutzers, der die Karte empfängt, nicht kennst. Daher bieten adaptive Karten Formatierungsfunktionen für `DATE()` und `TIME()`, damit die Zeit auf dem Zielgerät automatisch lokalisiert werden kann.

### <a name="datetime-example"></a>Beispiel für Datum/Uhrzeit

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

Obige Karte zeigt Folgendes an: 

> **Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**

### <a name="datetime-function-rules"></a>Funktionsregeln für Datum/Uhrzeit

Es gibt einige Regeln für das korrekte Interpretieren der Datums-/Uhrzeitfunktionen auf jeder Plattform. Wenn die Regeln nicht eingehalten werden, wird dem Benutzer die unformatierte Zeichenfolge anzeigt, was unerwünscht ist.

1. **GROß-/KLEINSCHREIBUNG** (darf nur Großbuchstaben enthalten)
1. **KEINE LEERZEICHEN** zwischen `{{`, `}}` oder runden Klammern
1. **STRIKTE [RFC 3389](https://tools.ietf.org/html/rfc3339)-FORMATIERUNG** (siehe Beispiele unten)
1. **MUSS** gültige Werte für Datum und Uhrzeit aufweisen

### <a name="valid-formats"></a>Gültige Formate

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a>Dateiformatparameter

Für Daten kann ein optionaler Parameter zum Formatieren der Ausgabe angegeben werden.


|       Format        |            Beispiel            |
|---------------------|-------------------------------|
| `COMPACT` (Standard) |          „2/13/2017“          |
|       `SHORT`       |     „Mon, Feb 13th, 2017“     |
|       `LONG`        | „Monday, February 13th, 2017“ |

