---
title: Vorlagen-SDKs
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 3a9bfcd1bf8f87959a747997e04f5c5ad2a79980
ms.sourcegitcommit: 90afb3729931b0e4cae19b17ef9e49453c2d2bf6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "72163614"
---
# <a name="adaptive-card-templating-sdks"></a>Vorlagen-SDKs für adaptive Karten

Die Vorlagen-SDKs für adaptive Karten vereinfachen das Auffüllen einer [Kartenvorlage](language.md) mit echten Daten auf unterstützten Plattformen.

> Hier finden Sie einen [Überblick über Vorlagen für adaptive Karten](index.md).

> [!IMPORTANT] 
> 
> Diese Features befinden sich **in der Vorschauphase und können geändert werden**. Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.
> 
> Während der ersten Vorschauversion ist nur das JavaScript SDK verfügbar, aber in Kürze sollte auch ein .NET SDK bereitgestellt werden.

## <a name="javascript"></a>JavaScript

Die [adaptivecards-templating](https://www.npmjs.com/package/adaptivecards-templating)-Bibliothek ist auf npm und über das CDN verfügbar. Die vollständige Dokumentation finden Sie unter dem Paketlink.

### <a name="npm"></a>npm

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a>CDN

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a>Usage

Im folgenden Beispiel wird davon ausgegangen, dass Sie auch die [adaptivecards](https://www.npmjs.com/package/adaptivecards)-Bibliothek installiert haben, um die Karte zu rendern. 

Wenn Sie nicht beabsichtigen, die Karte zu rendern, können Sie den `parse`- und `render`-Code entfernen. 

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

## <a name="net"></a>.NET 

```console
dotnet add package AdaptiveCards.Templating --version 0.1.0-alpha1
```

> [!NOTE]
>
> Ändern Sie ggf. die obige Version in die neueste veröffentlichte Version.

Importieren der Bibliothek 

```cs
using AdaptiveCards.Templating
```

Verwenden Sie das Vorlagen-Engine, indem Sie Vorlagen-JSON und Daten-JSON übergeben.

```cs
var templateJson = @"
{
    ""type"": ""AdaptiveCard"",
    ""version"": ""1.0"",
    ""body"": [
        {
            ""type"": ""TextBlock"",
            ""text"": ""Hello {name}""
        }
    ]
}";

var dataJson = @"
{
    ""name"": ""Mickey Mouse""
}";

var transformer = new AdaptiveTransformer();
var cardJson = transformer.Transform(templateJson, dataJson);
```
