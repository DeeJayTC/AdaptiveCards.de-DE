---
title: .NET SDK für Adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 10/01/2017
ms.topic: article
ms.openlocfilehash: 10400d5db3aac8ea60e5f03f5ab5d9b013211954
ms.sourcegitcommit: 4dd40521cd39313657f1dab642f49ff04098ba35
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71343737"
---
# <a name="net-sdk-for-authoring-cards"></a><span data-ttu-id="76c23-102">.NET SDK zum Erstellen von Karten</span><span class="sxs-lookup"><span data-stu-id="76c23-102">.NET SDK for Authoring Cards</span></span>

<span data-ttu-id="76c23-103">Wie auf der Seite " [Getting Started](../../authoring-cards/getting-started.md) " beschrieben, ist eine Adaptive Karte ein JSON-Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="76c23-103">As we described in the [Getting Started](../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON object model.</span></span> <span data-ttu-id="76c23-104">Die .NET-Bibliothek vereinfacht das Arbeiten mit diesem JSON-Code erheblich.</span><span class="sxs-lookup"><span data-stu-id="76c23-104">The .NET library makes working with that JSON much easier.</span></span>


## <a name="nuget-install"></a><span data-ttu-id="76c23-105">Nuget-Installation</span><span class="sxs-lookup"><span data-stu-id="76c23-105">NuGet Install</span></span>
<span data-ttu-id="76c23-106">Das `AdaptiveCards` nuget-Paket bietet Typen für die Arbeit mit adaptiven Karten in .net.</span><span class="sxs-lookup"><span data-stu-id="76c23-106">The `AdaptiveCards` NuGet package provides types for working with adaptive cards in .NET</span></span>

<span data-ttu-id="76c23-107">[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span><span class="sxs-lookup"><span data-stu-id="76c23-107">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span></span>

```console
Install-Package AdaptiveCards
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a><span data-ttu-id="76c23-108">Beispiel: Erstellen einer adaptivecard und Serialisieren in JSON</span><span class="sxs-lookup"><span data-stu-id="76c23-108">Example: Create an AdaptiveCard and serialize to JSON</span></span>

<span data-ttu-id="76c23-109">In diesem Beispiel wird veranschaulicht, wie eine Adaptive Karte mithilfe C# von Standardobjekten erstellt und anschließend für den Transport über das Netzwerk in JSON serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="76c23-109">This example demonstrates how to build an Adaptive Card using standard C# objects and then serialize it to JSON for transport over the wire.</span></span>

```csharp
using AdaptiveCards;
// ...

AdaptiveCard card = new AdaptiveCard(new AdaptiveSchemaVersion(1, 0));

card.Body.Add(new AdaptiveTextBlock() 
{
    Text = "Hello",
    Size = AdaptiveTextSize.ExtraLarge
});

card.Body.Add(new AdaptiveImage() 
{
    Url = new Uri("http://adaptivecards.io/content/cats/1.png")
});

// serialize the card to JSON
string json = card.ToJson();
```

## <a name="example-parse-an-adaptivecard-from-json"></a><span data-ttu-id="76c23-110">Beispiel: Analysieren einer adaptivecard aus JSON</span><span class="sxs-lookup"><span data-stu-id="76c23-110">Example: Parse an AdaptiveCard from JSON</span></span>

<span data-ttu-id="76c23-111">In diesem Beispiel wird veranschaulicht, wie Sie eine JSON-Nutzlast in einer adaptiven Karte analysieren.</span><span class="sxs-lookup"><span data-stu-id="76c23-111">This example demonstrates how to parse a JSON payload into an Adaptive Card.</span></span> <span data-ttu-id="76c23-112">Dies vereinfacht die Bearbeitung des Objektmodells oder sogar das renderingadaptiver Karten in ihrer App mithilfe unserer [Renderer-sdche](../../rendering-cards/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="76c23-112">This makes it easy to manipulate the object model or even render Adaptive Cards inside your app by using our [renderer SDKs](../../rendering-cards/getting-started.md).</span></span>

```csharp
try
{
    // Get a JSON-serialized payload
    // Your app will probably get cards from somewhere else :)
    var client = new HttpClient();
    var response = await client.GetAsync("http://adaptivecards.io/payloads/ActivityUpdate.json");
    var json = await response.Content.ReadAsStringAsync();

    // Parse the JSON 
    AdaptiveCardParseResult result = AdaptiveCard.FromJson(json);

    // Get card from result
    AdaptiveCard card = result.Card;

    // Optional: check for any parse warnings
    // This includes things like unknown element "type"
    // or unknown properties on element
    IList<AdaptiveWarning> warnings = result.Warnings;
}
catch(AdaptiveSerializationException ex)
{
    // Failed to deserialize card 
    // This occurs from malformed JSON
    // or schema violations like required properties missing 
}
```
