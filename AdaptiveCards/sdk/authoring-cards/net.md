---
title: .NET SDK für Adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 10/01/2017
ms.topic: article
ms.openlocfilehash: fa86d83a8f20490ec286b69653099ac8cd81b8ef
ms.sourcegitcommit: 4d80c553ab574befa8c84706fd85d22077915745
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68387347"
---
# <a name="net-sdk-for-authoring-cards"></a><span data-ttu-id="d2a55-102">.NET SDK zum Erstellen von Karten</span><span class="sxs-lookup"><span data-stu-id="d2a55-102">.NET SDK for Authoring Cards</span></span>

<span data-ttu-id="d2a55-103">Wie auf der Seite " [Getting Started](../../authoring-cards/getting-started.md) " beschrieben, ist eine Adaptive Karte ein JSON-Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="d2a55-103">As we described in the [Getting Started](../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON object model.</span></span> <span data-ttu-id="d2a55-104">Die .NET-Bibliothek vereinfacht das Arbeiten mit diesem JSON-Code erheblich.</span><span class="sxs-lookup"><span data-stu-id="d2a55-104">The .NET library makes working with that JSON much easier.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2a55-105">**Wichtige Änderungen von v 0,5**</span><span class="sxs-lookup"><span data-stu-id="d2a55-105">**Breaking changes from v0.5**</span></span>
> 
> 1. <span data-ttu-id="d2a55-106">Paket umbenannt von `Microsoft.AdaptiveCards` in`AdaptiveCards`</span><span class="sxs-lookup"><span data-stu-id="d2a55-106">Package renamed from `Microsoft.AdaptiveCards` to `AdaptiveCards`</span></span>
> 1. <span data-ttu-id="d2a55-107">Aufgrund häufiger Namenskollisionen mit Frameworktypen haben alle Modellklassen das Präfix "Adaptive".</span><span class="sxs-lookup"><span data-stu-id="d2a55-107">Due to frequent name collisions with framework types, all model classes have been prefixed with "Adaptive".</span></span> <span data-ttu-id="d2a55-108">Beispiel: `TextBlock` ist jetzt`AdaptiveTextBlock`</span><span class="sxs-lookup"><span data-stu-id="d2a55-108">E.g., `TextBlock` is now `AdaptiveTextBlock`</span></span>
> 1. <span data-ttu-id="d2a55-109">Alle "URI"-Eigenschaften wurden von Typ `string` in geändert.`Uri`</span><span class="sxs-lookup"><span data-stu-id="d2a55-109">All "uri" properties were changed from type `string` to `Uri`</span></span>
> 1. <span data-ttu-id="d2a55-110">Es gibt auch einige Schema Änderungen aus der v 0.5-Vorschau, die [hier beschrieben](https://github.com/Microsoft/AdaptiveCards/pull/633) werden.</span><span class="sxs-lookup"><span data-stu-id="d2a55-110">There have also been some schema changes from the v0.5 preview, which are [outlined here](https://github.com/Microsoft/AdaptiveCards/pull/633)</span></span>


## <a name="nuget-install"></a><span data-ttu-id="d2a55-111">Nuget-Installation</span><span class="sxs-lookup"><span data-stu-id="d2a55-111">NuGet Install</span></span>
<span data-ttu-id="d2a55-112">Das `AdaptiveCards` nuget-Paket bietet Typen für die Arbeit mit adaptiven Karten in .net.</span><span class="sxs-lookup"><span data-stu-id="d2a55-112">The `AdaptiveCards` NuGet package provides types for working with adaptive cards in .NET</span></span>

<span data-ttu-id="d2a55-113">[![Nuget-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span><span class="sxs-lookup"><span data-stu-id="d2a55-113">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span></span>

```console
Install-Package AdaptiveCards -IncludePrerelease
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a><span data-ttu-id="d2a55-114">Beispiel: Erstellen einer adaptivecard und Serialisieren in JSON</span><span class="sxs-lookup"><span data-stu-id="d2a55-114">Example: Create an AdaptiveCard and serialize to JSON</span></span>

<span data-ttu-id="d2a55-115">In diesem Beispiel wird veranschaulicht, wie eine Adaptive Karte mithilfe C# von Standardobjekten erstellt und anschließend für den Transport über das Netzwerk in JSON serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d2a55-115">This example demonstrates how to build an Adaptive Card using standard C# objects and then serialize it to JSON for transport over the wire.</span></span>

```csharp
using AdaptiveCards;
// ...

AdaptiveCard card = new AdaptiveCard();

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

## <a name="example-parse-an-adaptivecard-from-json"></a><span data-ttu-id="d2a55-116">Beispiel: Analysieren einer adaptivecard aus JSON</span><span class="sxs-lookup"><span data-stu-id="d2a55-116">Example: Parse an AdaptiveCard from JSON</span></span>

<span data-ttu-id="d2a55-117">In diesem Beispiel wird veranschaulicht, wie Sie eine JSON-Nutzlast in einer adaptiven Karte analysieren.</span><span class="sxs-lookup"><span data-stu-id="d2a55-117">This example demonstrates how to parse a JSON payload into an Adaptive Card.</span></span> <span data-ttu-id="d2a55-118">Dies vereinfacht die Bearbeitung des Objektmodells oder sogar das renderingadaptiver Karten in ihrer App mithilfe unserer [Renderer-sdche](../../rendering-cards/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="d2a55-118">This makes it easy to manipulate the object model or even render Adaptive Cards inside your app by using our [renderer SDKs](../../rendering-cards/getting-started.md).</span></span>

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
