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
# <a name="text-features"></a><span data-ttu-id="786ea-102">Text-features</span><span class="sxs-lookup"><span data-stu-id="786ea-102">Text features</span></span>

<span data-ttu-id="786ea-103">`TextBlock` bietet einige erweiterten Funktionen zum Formatieren und den Text lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="786ea-103">`TextBlock` offers some advanced features for formatting and localizing the text.</span></span>

## <a name="markdown"></a><span data-ttu-id="786ea-104">Markdown</span><span class="sxs-lookup"><span data-stu-id="786ea-104">Markdown</span></span>
<span data-ttu-id="786ea-105">Zur Unterstützung von Inline-Markup mit Adaptive Cards unterstützen eine **Teilmenge** von Markdown-Syntax.</span><span class="sxs-lookup"><span data-stu-id="786ea-105">To support inline markup, Adaptive Cards support a **subset** of Markdown syntax.</span></span>

<span data-ttu-id="786ea-106">_Unterstützt_</span><span class="sxs-lookup"><span data-stu-id="786ea-106">_Supported_</span></span>

| <span data-ttu-id="786ea-107">Textstil</span><span class="sxs-lookup"><span data-stu-id="786ea-107">Text Style</span></span>      | <span data-ttu-id="786ea-108">Markdown</span><span class="sxs-lookup"><span data-stu-id="786ea-108">Markdown</span></span> |
|-----------------|-----|
| <span data-ttu-id="786ea-109">**Fett**</span><span class="sxs-lookup"><span data-stu-id="786ea-109">**Bold**</span></span>        | ```**Bold**``` |
| <span data-ttu-id="786ea-110">_Kursiv_</span><span class="sxs-lookup"><span data-stu-id="786ea-110">_Italic_</span></span>        | ```_Italic_``` |
| <span data-ttu-id="786ea-111">Liste mit Aufzählungszeichen</span><span class="sxs-lookup"><span data-stu-id="786ea-111">Bullet list</span></span>     | ```- Item 1\r- Item 2\r- Item 3``` | 
| <span data-ttu-id="786ea-112">Nummerierte Liste</span><span class="sxs-lookup"><span data-stu-id="786ea-112">Numbered list</span></span>   | ```1. Green\r2. Orange\r3. Blue``` |
| <span data-ttu-id="786ea-113">Hyperlinks</span><span class="sxs-lookup"><span data-stu-id="786ea-113">Hyperlinks</span></span>      | ```[Title](url)``` |

<span data-ttu-id="786ea-114">_Nicht unterstützt_</span><span class="sxs-lookup"><span data-stu-id="786ea-114">_Not supported_</span></span>

* <span data-ttu-id="786ea-115">Header</span><span class="sxs-lookup"><span data-stu-id="786ea-115">Headers</span></span>
* <span data-ttu-id="786ea-116">Tabellen</span><span class="sxs-lookup"><span data-stu-id="786ea-116">Tables</span></span>
* <span data-ttu-id="786ea-117">Abbilder</span><span class="sxs-lookup"><span data-stu-id="786ea-117">Images</span></span>
* <span data-ttu-id="786ea-118">Alle Elemente nicht in der obigen Tabelle</span><span class="sxs-lookup"><span data-stu-id="786ea-118">Anything not in the table above</span></span>

### <a name="markdown-example"></a><span data-ttu-id="786ea-119">Markdown-Beispiel</span><span class="sxs-lookup"><span data-stu-id="786ea-119">Markdown Example</span></span>

<span data-ttu-id="786ea-120">Die folgenden Nutzlast würde etwa wie folgt gerendert:</span><span class="sxs-lookup"><span data-stu-id="786ea-120">The below payload would render something like this:</span></span>

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

## <a name="datetime-formatting-and-localization"></a><span data-ttu-id="786ea-122">Formatieren von Datum/Uhrzeit und Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="786ea-122">Date/Time formatting and localization</span></span>

<span data-ttu-id="786ea-123">Manchmal wird nicht man die Zeitzone des Benutzers empfangen von der Karte daher mit Adaptive Cards bietet `DATE()` und `TIME()` Formatierungsfunktionen, um die Uhrzeit auf dem Zielgerät automatisch zu lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="786ea-123">Sometimes you won't know the timezone of the user receiving the card, so Adaptive Cards offers `DATE()` and `TIME()` formatting functions to automatically localize the time on the target device.</span></span>

### <a name="datetime-example"></a><span data-ttu-id="786ea-124">Datum/Uhrzeit-Beispiel</span><span class="sxs-lookup"><span data-stu-id="786ea-124">Date/Time Example</span></span>

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

<span data-ttu-id="786ea-125">Die oben genannten Karte wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="786ea-125">The above card will display:</span></span> 

> <span data-ttu-id="786ea-126">**Das Paket wird am Dienstag, 14. Februar 2017 um 06:00 Uhr angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="786ea-126">**Your package will arrive on Tue, Feb 14th, 2017 at 6:00 AM**</span></span>

### <a name="datetime-function-rules"></a><span data-ttu-id="786ea-127">Datum/Uhrzeit – Funktionsregeln</span><span class="sxs-lookup"><span data-stu-id="786ea-127">Date/Time function rules</span></span>

<span data-ttu-id="786ea-128">Es gibt einige Regeln ordnungsgemäß interpretieren die der Datums-/Uhrzeitfunktionen auf jeder Plattform.</span><span class="sxs-lookup"><span data-stu-id="786ea-128">There are some rules to properly interpret the the date/time functions on every platform.</span></span> <span data-ttu-id="786ea-129">Klicken Sie dann die unformatierte Zeichenfolge für den Benutzer angezeigt wird, und niemand möchte, die, wenn die Regeln nicht erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="786ea-129">If the rules aren't met then the raw string will be displayed to the user, and no one wants that.</span></span>

1. <span data-ttu-id="786ea-130">**Groß-/ KLEINSCHREIBUNG** (muss Großbuchstaben)</span><span class="sxs-lookup"><span data-stu-id="786ea-130">**CASE SENSITIVE** (must be all caps)</span></span>
1. <span data-ttu-id="786ea-131">**KEINE Leerzeichen** zwischen der `{{`, `}}`, oder runden Klammern</span><span class="sxs-lookup"><span data-stu-id="786ea-131">**NO SPACES** between the `{{`, `}}`, or parentheses</span></span>
1. <span data-ttu-id="786ea-132">**STRENGE [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATIERUNG** (Siehe Beispiele unten)</span><span class="sxs-lookup"><span data-stu-id="786ea-132">**STRICT [RFC 3389](https://tools.ietf.org/html/rfc3339) FORMATTING** (See examples below)</span></span>
1. <span data-ttu-id="786ea-133">**MUSS** ein gültiges Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="786ea-133">**MUST BE** a valid date and time</span></span>

### <a name="valid-formats"></a><span data-ttu-id="786ea-134">Gültige Formate</span><span class="sxs-lookup"><span data-stu-id="786ea-134">Valid formats</span></span>

* `2017-02-14T06:08:00Z`
* `2017-02-14T06:08:00-07:00`
* `2017-02-14T06:08:00+07:00`

### <a name="date-formatting-param"></a><span data-ttu-id="786ea-135">Param-datumsformatierung</span><span class="sxs-lookup"><span data-stu-id="786ea-135">Date formatting param</span></span>

<span data-ttu-id="786ea-136">Für Daten kann ein optionaler Parameter zum Formatieren der Ausgabe angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="786ea-136">For dates, an optional param may be specified to format the output.</span></span>


|       <span data-ttu-id="786ea-137">Format</span><span class="sxs-lookup"><span data-stu-id="786ea-137">Format</span></span>        |            <span data-ttu-id="786ea-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="786ea-138">Example</span></span>            |
|---------------------|-------------------------------|
| <span data-ttu-id="786ea-139">`COMPACT` (Standard)</span><span class="sxs-lookup"><span data-stu-id="786ea-139">`COMPACT` (Default)</span></span> |          <span data-ttu-id="786ea-140">"2/13/2017"</span><span class="sxs-lookup"><span data-stu-id="786ea-140">"2/13/2017"</span></span>          |
|       `SHORT`       |     <span data-ttu-id="786ea-141">"Mon, 13. Februar 2017"</span><span class="sxs-lookup"><span data-stu-id="786ea-141">"Mon, Feb 13th, 2017"</span></span>     |
|       `LONG`        | <span data-ttu-id="786ea-142">"Montag, 13. Februar 2017"</span><span class="sxs-lookup"><span data-stu-id="786ea-142">"Monday, February 13th, 2017"</span></span> |

