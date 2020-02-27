---
title: Textmerkmale
author: matthidinger
ms.author: mahiding
ms.date: 11/09/2017
ms.topic: article
ms.openlocfilehash: f7ea40b80df4d976c0a8a86b15254018fdf2fac6
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454873"
---
# <a name="text-features"></a><span data-ttu-id="938cc-102">Textmerkmale</span><span class="sxs-lookup"><span data-stu-id="938cc-102">Text features</span></span>

<span data-ttu-id="938cc-103">`TextBlock` bietet einige erweiterte Features zum Formatieren und Lokalisieren von Text.</span><span class="sxs-lookup"><span data-stu-id="938cc-103">`TextBlock` offers some advanced features for formatting and localizing the text.</span></span>

## <a name="markdown"></a><span data-ttu-id="938cc-104">Markdown</span><span class="sxs-lookup"><span data-stu-id="938cc-104">Markdown</span></span>
<span data-ttu-id="938cc-105">Damit Inline-Markup möglich ist, unterstützen adaptive Karten eine **Teilmenge** an Markdown-Syntax.</span><span class="sxs-lookup"><span data-stu-id="938cc-105">To support inline markup, Adaptive Cards support a **subset** of Markdown syntax.</span></span>

<span data-ttu-id="938cc-106">_Unterstützt_</span><span class="sxs-lookup"><span data-stu-id="938cc-106">_Supported_</span></span>

| <span data-ttu-id="938cc-107">Textstil</span><span class="sxs-lookup"><span data-stu-id="938cc-107">Text Style</span></span>      | <span data-ttu-id="938cc-108">Markdown</span><span class="sxs-lookup"><span data-stu-id="938cc-108">Markdown</span></span> |
|-----------------|-----|
| <span data-ttu-id="938cc-109">**Fett**</span><span class="sxs-lookup"><span data-stu-id="938cc-109">**Bold**</span></span>        | ```**Bold**``` |
| <span data-ttu-id="938cc-110">_Kursiv_</span><span class="sxs-lookup"><span data-stu-id="938cc-110">_Italic_</span></span>        | ```_Italic_``` |
| <span data-ttu-id="938cc-111">Aufzählung</span><span class="sxs-lookup"><span data-stu-id="938cc-111">Bullet list</span></span>     | ```- Item 1\r- Item 2\r- Item 3``` | 
| <span data-ttu-id="938cc-112">Nummerierte Liste</span><span class="sxs-lookup"><span data-stu-id="938cc-112">Numbered list</span></span>   | ```1. Green\r2. Orange\r3. Blue``` |
| <span data-ttu-id="938cc-113">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="938cc-113">Hyperlinks</span></span>      | ```[Title](url)``` |

<span data-ttu-id="938cc-114">_Nicht unterstützt_</span><span class="sxs-lookup"><span data-stu-id="938cc-114">_Not supported_</span></span>

* <span data-ttu-id="938cc-115">Header</span><span class="sxs-lookup"><span data-stu-id="938cc-115">Headers</span></span>
* <span data-ttu-id="938cc-116">Tabellen</span><span class="sxs-lookup"><span data-stu-id="938cc-116">Tables</span></span>
* <span data-ttu-id="938cc-117">Abbilder</span><span class="sxs-lookup"><span data-stu-id="938cc-117">Images</span></span>
* <span data-ttu-id="938cc-118">Alle in der obigen Tabelle nicht genannten Elemente</span><span class="sxs-lookup"><span data-stu-id="938cc-118">Anything not in the table above</span></span>

### <a name="markdown-example"></a><span data-ttu-id="938cc-119">Markdown-Beispiel</span><span class="sxs-lookup"><span data-stu-id="938cc-119">Markdown Example</span></span>

<span data-ttu-id="938cc-120">Die folgende Nutzlast rendert etwa Folgendes:</span><span class="sxs-lookup"><span data-stu-id="938cc-120">The below payload would render something like this:</span></span>

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

## <a name="datetime-formatting-and-localization"></a><span data-ttu-id="938cc-122">Datums-/Uhrzeitformat und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="938cc-122">Date/Time formatting and localization</span></span>

<span data-ttu-id="938cc-123">Es kann vorkommen, dass du die Zeitzone des Benutzers, der die Karte empfängt, nicht kennst. Daher bieten adaptive Karten Formatierungsfunktionen für `DATE()` und `TIME()`, damit die Zeit auf dem Zielgerät automatisch lokalisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="938cc-123">Sometimes you won't know the timezone of the user receiving the card, so Adaptive Cards offers `DATE()` and `TIME()` formatting functions to automatically localize the time on the target device.</span></span>

### <a name="datetime-example"></a><span data-ttu-id="938cc-124">Beispiel für Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="938cc-124">Date/Time Example</span></span>

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

<span data-ttu-id="938cc-125">Obige Karte zeigt Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="938cc-125">The above card will display:</span></span> 

> <span data-ttu-id="938cc-126">**Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**</span><span class="sxs-lookup"><span data-stu-id="938cc-126">**Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**</span></span>

### <a name="datetime-function-rules"></a><span data-ttu-id="938cc-127">Funktionsregeln für Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="938cc-127">Date/Time function rules</span></span>

<span data-ttu-id="938cc-128">Es gibt einige Regeln für das korrekte Interpretieren der Datums-/Uhrzeitfunktionen auf jeder Plattform.</span><span class="sxs-lookup"><span data-stu-id="938cc-128">There are some rules to properly interpret the the date/time functions on every platform.</span></span> <span data-ttu-id="938cc-129">Wenn die Regeln nicht eingehalten werden, wird dem Benutzer die unformatierte Zeichenfolge anzeigt, was unerwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="938cc-129">If the rules aren't met then the raw string will be displayed to the user, and no one wants that.</span></span>

1. <span data-ttu-id="938cc-130">**GROß-/KLEINSCHREIBUNG** (darf nur Großbuchstaben enthalten)</span><span class="sxs-lookup"><span data-stu-id="938cc-130">**CASE SENSITIVE** (must be all caps)</span></span>
1. <span data-ttu-id="938cc-131">**KEINE LEERZEICHEN** zwischen `{{`, `}}` oder runden Klammern</span><span class="sxs-lookup"><span data-stu-id="938cc-131">**NO SPACES** between the `{{`, `}}`, or parentheses</span></span>
1. <span data-ttu-id="938cc-132">**STRIKTE [RFC 3389](https://tools.ietf.org/html/rfc3339)-FORMATIERUNG** (siehe Beispiele unten)</span><span class="sxs-lookup"><span data-stu-id="938cc-132">**STRICT [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATTING** (See examples below)</span></span>
1. <span data-ttu-id="938cc-133">**MUSS** gültige Werte für Datum und Uhrzeit aufweisen</span><span class="sxs-lookup"><span data-stu-id="938cc-133">**MUST BE** a valid date and time</span></span>

### <a name="valid-formats"></a><span data-ttu-id="938cc-134">Gültige Formate</span><span class="sxs-lookup"><span data-stu-id="938cc-134">Valid formats</span></span>

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a><span data-ttu-id="938cc-135">Dateiformatparameter</span><span class="sxs-lookup"><span data-stu-id="938cc-135">Date formatting param</span></span>

<span data-ttu-id="938cc-136">Für Daten kann ein optionaler Parameter zum Formatieren der Ausgabe angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="938cc-136">For dates, an optional param may be specified to format the output.</span></span>


|       <span data-ttu-id="938cc-137">Format</span><span class="sxs-lookup"><span data-stu-id="938cc-137">Format</span></span>        |            <span data-ttu-id="938cc-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="938cc-138">Example</span></span>            |
|---------------------|-------------------------------|
| <span data-ttu-id="938cc-139">`COMPACT` (Standard)</span><span class="sxs-lookup"><span data-stu-id="938cc-139">`COMPACT` (Default)</span></span> |          <span data-ttu-id="938cc-140">„2/13/2017“</span><span class="sxs-lookup"><span data-stu-id="938cc-140">"2/13/2017"</span></span>          |
|       `SHORT`       |     <span data-ttu-id="938cc-141">„Mon, Feb 13th, 2017“</span><span class="sxs-lookup"><span data-stu-id="938cc-141">"Mon, Feb 13th, 2017"</span></span>     |
|       `LONG`        | <span data-ttu-id="938cc-142">„Monday, February 13th, 2017“</span><span class="sxs-lookup"><span data-stu-id="938cc-142">"Monday, February 13th, 2017"</span></span> |

