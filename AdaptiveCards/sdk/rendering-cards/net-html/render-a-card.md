---
title: Rendern einer Karte - HTML-SDK für .NET
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 8dc1baffb91f0755f1955ee02b8a3e820b0d34e4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553102"
---
# <a name="render-a-card---net-html"></a><span data-ttu-id="ac91d-102">Rendern Sie eine Karte: .NET-HTML.</span><span class="sxs-lookup"><span data-stu-id="ac91d-102">Render a card - .NET HTML</span></span>

<span data-ttu-id="ac91d-103">Hier ist eine Karte mit dem .NET-SDK für HTML zu rendern.</span><span class="sxs-lookup"><span data-stu-id="ac91d-103">Here's how to render a card using the .NET HTML SDK.</span></span>

## <a name="instantiate-a-renderer"></a><span data-ttu-id="ac91d-104">Instanziieren Sie einen renderer</span><span class="sxs-lookup"><span data-stu-id="ac91d-104">Instantiate a renderer</span></span>

<span data-ttu-id="ac91d-105">Der nächste Schritt ist die Erstellung eine Instanz des Renderers.</span><span class="sxs-lookup"><span data-stu-id="ac91d-105">The next step is to create an instance of the renderer.</span></span> 

```csharp
using AdaptiveCards;
using AdaptiveCards.Rendering;
using AdaptiveCards.Rendering.Html;
// ... 

// Create a card renderer
AdaptiveCardRenderer renderer = new AdaptiveCardRenderer();

// For fun, check the schema version this renderer supports
AdaptiveSchemaVersion schemaVersion = renderer.SupportedSchemaVersion; // 1.0
```

## <a name="render-a-card-to-html"></a><span data-ttu-id="ac91d-106">Eine Karte wird in HTML gerendert.</span><span class="sxs-lookup"><span data-stu-id="ac91d-106">Render a card to HTML</span></span>

```csharp
// Build a simple card
// In the real world this would probably be provided as JSON
AdaptiveCard card = new AdaptiveCard()
{
    Body = { new AdaptiveTextBlock() { Text = "Hello World" } }
};

try
{
    // Render the card
    RenderedAdaptiveCard renderedCard = renderer.RenderCard(card);

    // Get the output HTML 
    HtmlTag html = renderedCard.Html;

    // (Optional) Check for any renderer warnings
    // This includes things like an unknown element type found in the card
    // Or the card exceeded the maxmimum number of supported actions, etc
    IList<AdaptiveWarning> warnings = renderedCard.Warnings;
}
catch(AdaptiveException ex)
{
    // Failed rendering
}
```
