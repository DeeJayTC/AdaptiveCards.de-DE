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
# <a name="render-a-card---uwp"></a><span data-ttu-id="8b34a-102">Rendern einer Karte – UWP</span><span class="sxs-lookup"><span data-stu-id="8b34a-102">Render a card - UWP</span></span>

<span data-ttu-id="8b34a-103">Hier ist eine Karte mit dem UWP-SDK darstellen.</span><span class="sxs-lookup"><span data-stu-id="8b34a-103">Here's how to render a card using the UWP SDK.</span></span>

## <a name="create-an-instance-of-your-renderer"></a><span data-ttu-id="8b34a-104">Erstellen Sie eine Instanz von Ihrem renderer</span><span class="sxs-lookup"><span data-stu-id="8b34a-104">Create an instance of your renderer</span></span>

<span data-ttu-id="8b34a-105">Erstellen Sie eine Instanz der Renderer-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="8b34a-105">Create an instance of the renderer library.</span></span> 

```csharp
using AdaptiveCards.Rendering.Uwp;
// ...

var renderer = new AdaptiveCardRenderer();
```

## <a name="create-a-card-from-a-json-string"></a><span data-ttu-id="8b34a-106">Erstellen Sie eine Karte aus einem JSON-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b34a-106">Create a card from a JSON string</span></span>

```csharp
var card = AdaptiveCard.FromJsonString(jsonString);
```

## <a name="create-a-card-from-a-json-object"></a><span data-ttu-id="8b34a-107">Erstellen Sie eine Karte aus einem jsonobjekt</span><span class="sxs-lookup"><span data-stu-id="8b34a-107">Create a card from a JSON object</span></span>

```csharp
var card = AdaptiveCard.FromJson(jsonObject);
```

## <a name="render-a-card"></a><span data-ttu-id="8b34a-108">Rendern einer Karte</span><span class="sxs-lookup"><span data-stu-id="8b34a-108">Render a card</span></span>

<span data-ttu-id="8b34a-109">Eine Karte aus einer Datenquelle abrufen und rendern.</span><span class="sxs-lookup"><span data-stu-id="8b34a-109">Acquire a card from a source and render it.</span></span>

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

## <a name="example"></a><span data-ttu-id="8b34a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b34a-110">Example</span></span>

<span data-ttu-id="8b34a-111">Hier ist ein Beispiel aus der UWP-Renderer.</span><span class="sxs-lookup"><span data-stu-id="8b34a-111">Here is an example from the UWP renderer.</span></span>

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