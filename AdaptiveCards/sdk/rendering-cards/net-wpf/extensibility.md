---
title: Erweiterbarkeit – .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 3e5bb9239d4b4200262648350d67d6494eed9724
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454323"
---
# <a name="extensibility---net-wpf"></a><span data-ttu-id="3a595-102">Erweiterbarkeit – .NET WPF</span><span class="sxs-lookup"><span data-stu-id="3a595-102">Extensibility - .NET WPF</span></span>

## <a name="custom-element-rendering"></a><span data-ttu-id="3a595-103">Benutzerdefiniertes Rendering von Elementen</span><span class="sxs-lookup"><span data-stu-id="3a595-103">Custom Element Rendering</span></span>

<span data-ttu-id="3a595-104">Für die vollständige Kontrolle über den Renderer kannst du die `ElementRenderers`-Eigenschaft verwenden, um Standardrenderer **hinzuzufügen**, **zu entfernen** oder **außer Kraft zu setzen**.</span><span class="sxs-lookup"><span data-stu-id="3a595-104">For full control of the renderer you can use the `ElementRenderers` property to **add**, **remove**, or **override** default renderers.</span></span>

<span data-ttu-id="3a595-105">Das folgende Beispiel zeigt, wie du ein benutzerdefiniertes `"type": "Rating"`-Element definieren und rendern kannst.</span><span class="sxs-lookup"><span data-stu-id="3a595-105">The following example shows how you could define a custom `"type": "Rating"` element and render it.</span></span>

```csharp
// Register the new type with the JSON parser
AdaptiveTypedElementConverter.RegisterTypedElement<MyCustomRating>();

// Add the new type to the element renderer registry
renderer.ElementRenderers.Set<MyCustomRating>(MyCustomRating.Render);

// Define a custom Rating element type
public class MyCustomRating : AdaptiveElement
{
    public MyCustomRating() { Type = "Rating"; }

    public override string Type { get; set; }

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
