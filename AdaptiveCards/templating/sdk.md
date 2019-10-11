---
title: Vorlagen-SDKs
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 3a9bfcd1bf8f87959a747997e04f5c5ad2a79980
ms.sourcegitcommit: 90afb3729931b0e4cae19b17ef9e49453c2d2bf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "72163614"
---
# <a name="adaptive-card-templating-sdks"></a><span data-ttu-id="bf72f-102">Adaptive Smartcardvorlagen-sdche</span><span class="sxs-lookup"><span data-stu-id="bf72f-102">Adaptive Card Templating SDKs</span></span>

<span data-ttu-id="bf72f-103">Mithilfe der Vorlagen für Adaptive Karten-Vorlagen können Sie ganz einfach eine [Karten Vorlage](language.md) mit echten Daten auf allen unterstützten Plattformen auffüllen.</span><span class="sxs-lookup"><span data-stu-id="bf72f-103">The Adaptive Card Templating SDKs make it easy to populate a [card template](language.md) with real data on any supported platform.</span></span>

> <span data-ttu-id="bf72f-104">Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="bf72f-104">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="bf72f-105">Diese Features befinden sich **in der Vorschauphase und können geändert werden**.</span><span class="sxs-lookup"><span data-stu-id="bf72f-105">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="bf72f-106">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.</span><span class="sxs-lookup"><span data-stu-id="bf72f-106">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>
> 
> <span data-ttu-id="bf72f-107">Während der ersten Vorschauversion ist nur das JavaScript SDK verfügbar, aber in Kürze sollte ein .NET SDK eintreffen.</span><span class="sxs-lookup"><span data-stu-id="bf72f-107">During the initial preview only the JavaScript SDK is available, but a .NET SDK should arrive shortly.</span></span>

## <a name="javascript"></a><span data-ttu-id="bf72f-108">JavaScript</span><span class="sxs-lookup"><span data-stu-id="bf72f-108">JavaScript</span></span>

<span data-ttu-id="bf72f-109">Die [adaptivecards-](https://www.npmjs.com/package/adaptivecards-templating) Vorlagen Bibliothek ist auf NPM und über das CDN verfügbar.</span><span class="sxs-lookup"><span data-stu-id="bf72f-109">The [adaptivecards-templating](https://www.npmjs.com/package/adaptivecards-templating) library is available on npm and via CDN.</span></span> <span data-ttu-id="bf72f-110">Die vollständige Dokumentation finden Sie unter dem paketlink.</span><span class="sxs-lookup"><span data-stu-id="bf72f-110">See the package link for full documentation.</span></span>

### <a name="npm"></a><span data-ttu-id="bf72f-111">NPM</span><span class="sxs-lookup"><span data-stu-id="bf72f-111">npm</span></span>

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a><span data-ttu-id="bf72f-112">CDN</span><span class="sxs-lookup"><span data-stu-id="bf72f-112">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a><span data-ttu-id="bf72f-113">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bf72f-113">Usage</span></span>

<span data-ttu-id="bf72f-114">Im folgenden Beispiel wird davon ausgegangen, dass Sie auch die [adaptivecards](https://www.npmjs.com/package/adaptivecards) -Bibliothek installiert haben, um die Karte zu Rendering.</span><span class="sxs-lookup"><span data-stu-id="bf72f-114">The sample below assumes you've also installed the [adaptivecards](https://www.npmjs.com/package/adaptivecards) library in order to render the card.</span></span> 

<span data-ttu-id="bf72f-115">Wenn Sie die Karte nicht rendern möchten, können Sie den Code "`parse`" und "`render`" entfernen.</span><span class="sxs-lookup"><span data-stu-id="bf72f-115">If you don't plan on rendering the card then you can remove the `parse` and `render` code.</span></span> 

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

## <a name="net"></a><span data-ttu-id="bf72f-116">.NET</span><span class="sxs-lookup"><span data-stu-id="bf72f-116">.NET</span></span> 

```console
dotnet add package AdaptiveCards.Templating --version 0.1.0-alpha1
```

> [!NOTE]
>
> <span data-ttu-id="bf72f-117">Ändern Sie ggf. die obige Version in die neueste veröffentlichte Version.</span><span class="sxs-lookup"><span data-stu-id="bf72f-117">Consider changing the version above to the latest published version</span></span>

<span data-ttu-id="bf72f-118">Importieren der Bibliothek</span><span class="sxs-lookup"><span data-stu-id="bf72f-118">Import the library</span></span> 

```cs
using AdaptiveCards.Templating
```

<span data-ttu-id="bf72f-119">Verwenden Sie die Vorlagen-Engine, indem Sie Ihre Vorlagen-JSON und Data JSON übergeben.</span><span class="sxs-lookup"><span data-stu-id="bf72f-119">Use the templating engine by passing in your template JSON and data JSON.</span></span>

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
