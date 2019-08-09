---
title: Vorlagen für sdche
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 5f60a458af99f1b88e8ee428a8f29f1849be9b62
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878877"
---
# <a name="adaptive-card-templating-sdks"></a>Adaptive Smartcardvorlagen-sdche

Mithilfe der Vorlagen für Adaptive Karten-Vorlagen können Sie ganz einfach eine [Karten Vorlage](language.md) mit echten Daten auf allen unterstützten Plattformen auffüllen.

> Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.

> [!IMPORTANT] 
> 
> Diese Features befinden sich **in der Vorschau Phase und können geändert**werden. Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass wir die benötigten Features bereitstellen.
> 
> Während der ersten Vorschauversion ist nur das JavaScript SDK verfügbar, aber in Kürze sollte ein .NET SDK eintreffen.

## <a name="javascript"></a>JavaScript

Die [adaptivecards-](https://www.npmjs.com/package/adaptivecards-templating) Vorlagen Bibliothek ist auf NPM und über das CDN verfügbar. Die vollständige Dokumentation finden Sie unter dem paketlink.

### <a name="npm"></a>NPM

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a>CDN

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a>Verwendung

Im folgenden Beispiel wird davon ausgegangen, dass Sie auch die [adaptivecards](https://www.npmjs.com/package/adaptivecards) -Bibliothek installiert haben, um die Karte zu Rendering. 

Wenn Sie das Rendering der Karte nicht planen, können Sie den- `parse` und `render` den-Code entfernen. 

```js
import * as ACData from "adaptivecards-templating";
import * as AdaptiveCards from "adaptivecards";
 
// Define a template payload
var templatePayload = {
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Hello {name}!"
        }
    ]
};
 
// Create a Template instamce from the template payload
var template = new ACData.Template(templatePayload);
 
// Create a data binding context, and set its $root property to the
// data object to bind the template to
var context = new ACData.EvaluationContext();
context.$root = {
    "name": "Mickey Mouse"
};
 
// "Expand" the template - this generates the final Adaptive Card,
// ready to render
var card = template.expand(context);
 
// Render the card
var adaptiveCard = new AdaptiveCards.AdaptiveCard();
adaptiveCard.parse(card);
 
var htmlElement = adaptiveCard.render();
```

## <a name="net-coming-soon"></a>.Net (*bald*verfügbar)

NOCH NICHT FUNKTIONIERT: 

```console
nuget install AdaptiveCards.Templating
```
