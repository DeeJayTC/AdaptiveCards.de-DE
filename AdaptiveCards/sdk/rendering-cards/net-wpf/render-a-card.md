---
title: Rendern einer Karte – .NET WPF-SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 6bc476c79c6d06c7ecb770fb1c3e89eb55e81b9a
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553472"
---
# <a name="render-a-card---net-wpf"></a><span data-ttu-id="77869-102">Rendern einer Karte – WPF für .NET</span><span class="sxs-lookup"><span data-stu-id="77869-102">Render a card - .NET WPF</span></span>

<span data-ttu-id="77869-103">Hier ist eine Karte mit dem .NET-SDK für WPF darstellen.</span><span class="sxs-lookup"><span data-stu-id="77869-103">Here's how to render a card using the .NET WPF SDK.</span></span>

> [!NOTE]
> <span data-ttu-id="77869-104">**`Media` mit HTTPS-URLs funktionieren nicht in WPF**</span><span class="sxs-lookup"><span data-stu-id="77869-104">**`Media` with HTTPS URLs will not work in WPF**</span></span>
> 
> <span data-ttu-id="77869-105">Aufgrund einer [Fehler im WPF-MediaElement-Steuerelement](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) wir sind nicht zum Rendern von Medien, die über HTTPS bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="77869-105">Due to a [bug in the WPF MediaElement control](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) we aren't able to render media that is served via HTTPS.</span></span> <span data-ttu-id="77869-106">Verwenden Sie HTTP-URLs in die `Media` Element aus, bis dieser behoben wird.</span><span class="sxs-lookup"><span data-stu-id="77869-106">You should use HTTP URLs in the `Media` element until this is addressed.</span></span>  

## <a name="instantiate-a-renderer"></a><span data-ttu-id="77869-107">Instanziieren Sie einen renderer</span><span class="sxs-lookup"><span data-stu-id="77869-107">Instantiate a renderer</span></span>

<span data-ttu-id="77869-108">Erstellen Sie eine Instanz der Renderer-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="77869-108">Create an instance of the renderer library.</span></span> 

```csharp
using AdaptiveCards;
using AdaptiveCards.Rendering;
using AdaptiveCards.Rendering.Wpf;
// ...

// Create a card renderer
AdaptiveCardRenderer renderer = new AdaptiveCardRenderer();

// If using the Xceed package, enable the enhanced input
renderer.UseXceedElementRenderers();

// For fun, check the schema version this renderer supports
AdaptiveSchemaVersion schemaVersion = renderer.SupportedSchemaVersion;
```

## <a name="render-a-card-to-xaml"></a><span data-ttu-id="77869-109">Eine Karte für XAML rendern</span><span class="sxs-lookup"><span data-stu-id="77869-109">Render a card to XAML</span></span>

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

    // Get the FrameworkElement
    // Add this to your app's UI somewhere
    FrameworkElement fe = renderedCard.FrameworkElement;

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

