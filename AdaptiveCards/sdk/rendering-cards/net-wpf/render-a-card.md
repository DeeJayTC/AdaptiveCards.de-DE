---
title: Rendern einer Karte – .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: f847b83a17456dbf80f869ef8ef0df699e57f50e
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134297"
---
# <a name="render-a-card---net-wpf"></a>Rendern einer Karte – .NET WPF

Hier findest zu Informationen zum Rendern einer Karte mit dem .NET WPF SDK.

> [!NOTE]
> **`Media` mit HTTPS-URLs funktioniert nicht in WPF.**
> 
> Aufgrund eines [Fehlers im WPF-MediaElement-Steuerelement](https://stackoverflow.com/questions/30702505/playing-media-from-https-site-in-media-element-throwing-null-reference-exception) ist das Rendern von Medien, die über HTTPS übermittelt werden, nicht möglich. Verwende daher HTTP-URLs im `Media`-Element, bis dieses Problem behoben ist.  

## <a name="instantiate-a-renderer"></a>Instanziieren eines Renderers

Erstelle eine Instanz der Rendererbibliothek. 

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

## <a name="render-a-card-to-xaml"></a>Rendern einer Karte in XAML

```csharp
// Build a simple card
// In the real world this would probably be provided as JSON
AdaptiveCard card = new AdaptiveCard("1.0")
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
    // Or the card exceeded the maximum number of supported actions, etc
    IList<AdaptiveWarning> warnings = renderedCard.Warnings;
}
catch(AdaptiveException ex)
{
    // Failed rendering
}
```

