---
title: Vorlagen-SDKs
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 3a9bfcd1bf8f87959a747997e04f5c5ad2a79980
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "72163614"
---
# <a name="adaptive-card-templating-sdks"></a><span data-ttu-id="e0401-102">Vorlagen-SDKs für adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="e0401-102">Adaptive Card Templating SDKs</span></span>

<span data-ttu-id="e0401-103">Die Vorlagen-SDKs für adaptive Karten vereinfachen das Auffüllen einer [Kartenvorlage](language.md) mit echten Daten auf unterstützten Plattformen.</span><span class="sxs-lookup"><span data-stu-id="e0401-103">The Adaptive Card Templating SDKs make it easy to populate a [card template](language.md) with real data on any supported platform.</span></span>

> <span data-ttu-id="e0401-104">Hier finden Sie einen [Überblick über Vorlagen für adaptive Karten](index.md).</span><span class="sxs-lookup"><span data-stu-id="e0401-104">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="e0401-105">Diese Features befinden sich **in der Vorschauphase und können geändert werden**.</span><span class="sxs-lookup"><span data-stu-id="e0401-105">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="e0401-106">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.</span><span class="sxs-lookup"><span data-stu-id="e0401-106">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>
> 
> <span data-ttu-id="e0401-107">Während der ersten Vorschauversion ist nur das JavaScript SDK verfügbar, aber in Kürze sollte auch ein .NET SDK bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e0401-107">During the initial preview only the JavaScript SDK is available, but a .NET SDK should arrive shortly.</span></span>

## <a name="javascript"></a><span data-ttu-id="e0401-108">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e0401-108">JavaScript</span></span>

<span data-ttu-id="e0401-109">Die [adaptivecards-templating](https://www.npmjs.com/package/adaptivecards-templating)-Bibliothek ist auf npm und über das CDN verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0401-109">The [adaptivecards-templating](https://www.npmjs.com/package/adaptivecards-templating) library is available on npm and via CDN.</span></span> <span data-ttu-id="e0401-110">Die vollständige Dokumentation finden Sie unter dem Paketlink.</span><span class="sxs-lookup"><span data-stu-id="e0401-110">See the package link for full documentation.</span></span>

### <a name="npm"></a><span data-ttu-id="e0401-111">npm</span><span class="sxs-lookup"><span data-stu-id="e0401-111">npm</span></span>

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a><span data-ttu-id="e0401-112">CDN</span><span class="sxs-lookup"><span data-stu-id="e0401-112">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a><span data-ttu-id="e0401-113">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="e0401-113">Usage</span></span>

<span data-ttu-id="e0401-114">Im folgenden Beispiel wird davon ausgegangen, dass Sie auch die [adaptivecards](https://www.npmjs.com/package/adaptivecards)-Bibliothek installiert haben, um die Karte zu rendern.</span><span class="sxs-lookup"><span data-stu-id="e0401-114">The sample below assumes you've also installed the [adaptivecards](https://www.npmjs.com/package/adaptivecards) library in order to render the card.</span></span> 

<span data-ttu-id="e0401-115">Wenn Sie nicht beabsichtigen, die Karte zu rendern, können Sie den `parse`- und `render`-Code entfernen.</span><span class="sxs-lookup"><span data-stu-id="e0401-115">If you don't plan on rendering the card then you can remove the `parse` and `render` code.</span></span> 

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

## <a name="net"></a><span data-ttu-id="e0401-116">.NET</span><span class="sxs-lookup"><span data-stu-id="e0401-116">.NET</span></span> 

```console
dotnet add package AdaptiveCards.Templating --version 0.1.0-alpha1
```

> [!NOTE]
>
> <span data-ttu-id="e0401-117">Ändern Sie ggf. die obige Version in die neueste veröffentlichte Version.</span><span class="sxs-lookup"><span data-stu-id="e0401-117">Consider changing the version above to the latest published version</span></span>

<span data-ttu-id="e0401-118">Importieren der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="e0401-118">Import the library</span></span> 

```cs
using AdaptiveCards.Templating
```

<span data-ttu-id="e0401-119">Verwenden Sie das Vorlagen-Engine, indem Sie Vorlagen-JSON und Daten-JSON übergeben.</span><span class="sxs-lookup"><span data-stu-id="e0401-119">Use the templating engine by passing in your template JSON and data JSON.</span></span>

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
