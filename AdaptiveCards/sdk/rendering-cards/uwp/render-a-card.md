---
title: Rendern einer Karte - UWP-SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 1a72cb9ba72811d4e98a48116fa08245e13a6392
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552432"
---
# <a name="render-a-card---uwp"></a>Rendern einer Karte – UWP

Hier ist eine Karte mit dem UWP-SDK darstellen.

## <a name="create-an-instance-of-your-renderer"></a>Erstellen Sie eine Instanz von Ihrem renderer

Erstellen Sie eine Instanz der Renderer-Bibliothek. 

```csharp
using AdaptiveCards.Rendering.Uwp;
// ...

var renderer = new AdaptiveCardRenderer();
```

## <a name="create-a-card-from-a-json-string"></a>Erstellen Sie eine Karte aus einem JSON-Zeichenfolge

```csharp
var card = AdaptiveCard.FromJsonString(jsonString);
```

## <a name="create-a-card-from-a-json-object"></a>Erstellen Sie eine Karte aus einem jsonobjekt

```csharp
var card = AdaptiveCard.FromJson(jsonObject);
```

## <a name="render-a-card"></a>Rendern einer Karte

Eine Karte aus einer Datenquelle abrufen und rendern.

```csharp
RenderedAdaptiveCard renderedAdaptiveCard =  renderer.RenderAdaptiveCard(card);

// Check if the render was successful
if (renderedAdaptiveCard.FrameworkElement != null)
{
    // Get the framework element
    var uiCard = renderedAdaptiveCard.FrameworkElement;

    // Add it to your UI
    myGrid.Children.Add(uiCard);
}
```

## <a name="example"></a>Beispiel

Hier ist ein Beispiel aus der UWP-Renderer.

```csharp
var renderer = new AdaptiveCardRenderer();
var card = AdaptiveCard.FromJsonString(jsonString);
var renderedAdaptiveCard = renderer.RenderAdaptiveCard(card.AdaptiveCard);
if (renderedAdaptiveCard.FrameworkElement != null)
{
    myGrid.Children.Add(renderedAdaptiveCard.FrameworkElement);
}
...
```