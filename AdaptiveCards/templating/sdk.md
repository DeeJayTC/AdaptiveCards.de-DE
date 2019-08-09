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
# <a name="adaptive-card-templating-sdks"></a><span data-ttu-id="75e47-102">Adaptive Smartcardvorlagen-sdche</span><span class="sxs-lookup"><span data-stu-id="75e47-102">Adaptive Card Templating SDKs</span></span>

<span data-ttu-id="75e47-103">Mithilfe der Vorlagen für Adaptive Karten-Vorlagen können Sie ganz einfach eine [Karten Vorlage](language.md) mit echten Daten auf allen unterstützten Plattformen auffüllen.</span><span class="sxs-lookup"><span data-stu-id="75e47-103">The Adaptive Card Templating SDKs make it easy to populate a [card template](language.md) with real data on any supported platform.</span></span>

> <span data-ttu-id="75e47-104">Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="75e47-104">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="75e47-105">Diese Features befinden sich **in der Vorschau Phase und können geändert**werden.</span><span class="sxs-lookup"><span data-stu-id="75e47-105">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="75e47-106">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass wir die benötigten Features bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="75e47-106">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>
> 
> <span data-ttu-id="75e47-107">Während der ersten Vorschauversion ist nur das JavaScript SDK verfügbar, aber in Kürze sollte ein .NET SDK eintreffen.</span><span class="sxs-lookup"><span data-stu-id="75e47-107">During the initial preview only the JavaScript SDK is available, but a .NET SDK should arrive shortly.</span></span>

## <a name="javascript"></a><span data-ttu-id="75e47-108">JavaScript</span><span class="sxs-lookup"><span data-stu-id="75e47-108">JavaScript</span></span>

<span data-ttu-id="75e47-109">Die [adaptivecards-](https://www.npmjs.com/package/adaptivecards-templating) Vorlagen Bibliothek ist auf NPM und über das CDN verfügbar.</span><span class="sxs-lookup"><span data-stu-id="75e47-109">The [adaptivecards-templating](https://www.npmjs.com/package/adaptivecards-templating) library is available on npm and via CDN.</span></span> <span data-ttu-id="75e47-110">Die vollständige Dokumentation finden Sie unter dem paketlink.</span><span class="sxs-lookup"><span data-stu-id="75e47-110">See the package link for full documentation.</span></span>

### <a name="npm"></a><span data-ttu-id="75e47-111">NPM</span><span class="sxs-lookup"><span data-stu-id="75e47-111">npm</span></span>

```console
npm install adaptivecards-templating
```

### <a name="cdn"></a><span data-ttu-id="75e47-112">CDN</span><span class="sxs-lookup"><span data-stu-id="75e47-112">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards-templating/dist/adaptivecards-templating.min.js"></script>
``` 

### <a name="usage"></a><span data-ttu-id="75e47-113">Verwendung</span><span class="sxs-lookup"><span data-stu-id="75e47-113">Usage</span></span>

<span data-ttu-id="75e47-114">Im folgenden Beispiel wird davon ausgegangen, dass Sie auch die [adaptivecards](https://www.npmjs.com/package/adaptivecards) -Bibliothek installiert haben, um die Karte zu Rendering.</span><span class="sxs-lookup"><span data-stu-id="75e47-114">The sample below assumes you've also installed the [adaptivecards](https://www.npmjs.com/package/adaptivecards) library in order to render the card.</span></span> 

<span data-ttu-id="75e47-115">Wenn Sie das Rendering der Karte nicht planen, können Sie den- `parse` und `render` den-Code entfernen.</span><span class="sxs-lookup"><span data-stu-id="75e47-115">If you don't plan on rendering the card then you can remove the `parse` and `render` code.</span></span> 

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

## <a name="net-coming-soon"></a><span data-ttu-id="75e47-116">.Net (*bald*verfügbar)</span><span class="sxs-lookup"><span data-stu-id="75e47-116">.NET (*coming soon*)</span></span>

<span data-ttu-id="75e47-117">NOCH NICHT FUNKTIONIERT:</span><span class="sxs-lookup"><span data-stu-id="75e47-117">NOT WORKING YET:</span></span> 

```console
nuget install AdaptiveCards.Templating
```
