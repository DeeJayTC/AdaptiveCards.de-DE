---
title: Erweiterbarkeit – .NET WPF-SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: af301ec4d73b6791c1d132b9df7040d71cf70d7b
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552622"
---
# <a name="extensibility---net-wpf"></a>Erweiterbarkeit – WPF für .NET

## <a name="custom-element-rendering"></a>Benutzerdefiniertes Element-Textrendering

Für die vollständige Kontrolle über den Renderer können Sie die `ElementRenderers` Eigenschaft **hinzufügen**, **entfernen**, oder **außer Kraft setzen** Standard Renderer.

Das folgende Beispiel zeigt, wie Sie ein benutzerdefiniertes konnte `"type": "Rating"` Element und zu rendern.

```csharp
// Register the new type with the JSON parser
AdaptiveTypedElementConverter.RegisterTypedElement<MyCustomRating>();

// Add the new type to the element renderer registry
renderer.ElementRenderers.Set<MyCustomRating>(MyCustomRating.Render);

// Define a custom Rating element type
public class MyCustomRating : AdaptiveElement
{
    public override string Type => "Rating";

    public double Rating { get; set; }

    public AdaptiveTextSize Size { get; set; }

    public AdaptiveTextColor Color { get; set; }

    public static FrameworkElement Render(MyCustomRating rating, AdaptiveRenderContext context)
    {
        var textBlock = new AdaptiveTextBlock
        {
            Size = rating.Size,
            Color = rating.Color
        };
        for (int i = 0; i < rating.Rating; i++)
        {
            textBlock.Text += "\u2605";
        }
        textBlock.Text += $" ({rating.Rating})";
        return context.Render(textBlock);
    }
}
```
