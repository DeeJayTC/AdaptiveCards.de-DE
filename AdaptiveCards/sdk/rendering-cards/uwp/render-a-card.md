---
title: Rendering eines Card-UWP SDK
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
# <a name="render-a-card---uwp"></a>Rendering einer Karte (UWP)

Im folgenden wird beschrieben, wie Sie eine Karte mithilfe des UWP SDK Rendering.

## <a name="create-an-instance-of-your-renderer"></a>Erstellen einer Instanz des Renderers

Erstelle eine Instanz der Rendererbibliothek. 

```csharp
using AdaptiveCards.Rendering.Uwp;
// ...

var renderer = new AdaptiveCardRenderer();
```

## <a name="create-a-card-from-a-json-string"></a>Erstellen einer Karte aus einer JSON-Zeichenfolge

```csharp
var card = AdaptiveCard.FromJsonString(jsonString);
```

## <a name="create-a-card-from-a-json-object"></a>Erstellen einer Karte aus einem JSON-Objekt

```csharp
var card = AdaptiveCard.FromJson(jsonObject);
```

## <a name="render-a-card"></a>Rendern einer Karte

Erwerben Sie eine Karte aus einer Quelle, und rendersie Sie.

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

Im folgenden finden Sie ein Beispiel aus dem UWP-Renderer.

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