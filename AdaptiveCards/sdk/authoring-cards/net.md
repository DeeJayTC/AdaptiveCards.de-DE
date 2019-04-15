---
title: .NET SDK für mit Adaptive Cards
author: matthidinger
ms.author: mahiding
ms.date: 10/01/2017
ms.topic: article
ms.openlocfilehash: 37dec7651a574194eb00d46014431dfb5764f9b7
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553742"
---
# <a name="net-sdk-for-authoring-cards"></a><span data-ttu-id="32edd-102">.NET SDK zum Erstellen von Karten</span><span class="sxs-lookup"><span data-stu-id="32edd-102">.NET SDK for Authoring Cards</span></span>

<span data-ttu-id="32edd-103">Wie wir unter den [Einstieg](../../authoring-cards/getting-started.md) Seite eine Adaptive Card ist ein JSON-Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="32edd-103">As we described in the [Getting Started](../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON object model.</span></span> <span data-ttu-id="32edd-104">Die Bibliothek für .NET kann die Arbeit mit diesen JSON-Code viel einfacher.</span><span class="sxs-lookup"><span data-stu-id="32edd-104">The .NET library makes working with that JSON much easier.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32edd-105">**Wichtige Änderungen gegenüber v0.5**</span><span class="sxs-lookup"><span data-stu-id="32edd-105">**Breaking changes from v0.5**</span></span>
> 
> 1. <span data-ttu-id="32edd-106">Paket umbenannt `Microsoft.AdaptiveCards` auf `AdaptiveCards`</span><span class="sxs-lookup"><span data-stu-id="32edd-106">Package renamed from `Microsoft.AdaptiveCards` to `AdaptiveCards`</span></span>
> 1. <span data-ttu-id="32edd-107">Aufgrund der häufigen Namenskonflikte mit Framework-Typen haben alle Modellklassen "Adaptive" als Präfix vorangestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="32edd-107">Due to frequent name collisions with framework types, all model classes have been prefixed with "Adaptive".</span></span> <span data-ttu-id="32edd-108">Z. B. `TextBlock` ist jetzt `AdaptiveTextBlock`</span><span class="sxs-lookup"><span data-stu-id="32edd-108">E.g., `TextBlock` is now `AdaptiveTextBlock`</span></span>
> 1. <span data-ttu-id="32edd-109">Alle Eigenschaften von "Uri" wurden vom Typ `string` auf `Uri`</span><span class="sxs-lookup"><span data-stu-id="32edd-109">All "uri" properties were changed from type `string` to `Uri`</span></span>
> 1. <span data-ttu-id="32edd-110">Es wurden außerdem einige schemaänderungen in der Vorschau v0.5 sind [die nachfolgend beschrieben](https://github.com/Microsoft/AdaptiveCards/pull/633)</span><span class="sxs-lookup"><span data-stu-id="32edd-110">There have also been some schema changes from the v0.5 preview, which are [outlined here](https://github.com/Microsoft/AdaptiveCards/pull/633)</span></span>


## <a name="nuget-install"></a><span data-ttu-id="32edd-111">Installieren von NuGet</span><span class="sxs-lookup"><span data-stu-id="32edd-111">NuGet Install</span></span>
<span data-ttu-id="32edd-112">Die `AdaptiveCards` NuGet-Paket stellt Typen bereit, für den Umgang mit adaptive Cards in .NET</span><span class="sxs-lookup"><span data-stu-id="32edd-112">The `AdaptiveCards` NuGet package provides types for working with adaptive cards in .NET</span></span>

<span data-ttu-id="32edd-113">[![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span><span class="sxs-lookup"><span data-stu-id="32edd-113">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)</span></span>

```console
Install-Package AdaptiveCards -IncludePrerelease
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a><span data-ttu-id="32edd-114">Beispiel: Erstellen Sie eine AdaptiveCard und Serialisieren in JSON</span><span class="sxs-lookup"><span data-stu-id="32edd-114">Example: Create an AdaptiveCard and serialize to JSON</span></span>

<span data-ttu-id="32edd-115">In diesem Beispiel wird veranschaulicht, wie erstellen Sie eine Adaptive Card mit standardmäßigen C# Objekte und serialisiert sie anschließend in JSON für den Transport über das Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="32edd-115">This example demonstrates how to build an Adaptive Card using standard C# objects and then serialize it to JSON for transport over the wire.</span></span>

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

## <a name="example-parse-an-adaptivecard-from-json"></a><span data-ttu-id="32edd-116">Beispiel: Ein AdaptiveCard aus JSON analysieren</span><span class="sxs-lookup"><span data-stu-id="32edd-116">Example: Parse an AdaptiveCard from JSON</span></span>

<span data-ttu-id="32edd-117">Dieses Beispiel zeigt, wie Sie eine JSON-Nutzlast in eine Adaptive Card zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="32edd-117">This example demonstrates how to parse a JSON payload into an Adaptive Card.</span></span> <span data-ttu-id="32edd-118">Dies erleichtert es auf das Objektmodell oder sogar Rendering mit Adaptive Cards in Ihrer app mit unseren [Renderer SDKs](../../rendering-cards/getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="32edd-118">This makes it easy to manipulate the object model or even render Adaptive Cards inside your app by using our [renderer SDKs](../../rendering-cards/getting-started.md).</span></span>

```csharp
try
{
    // Get a JSON-serialized payload
    // Your app will probably get cards from somewhere else :)
    var client = new HttpClient("http://adaptivecards.io/payloads/ActivityUpdate.json");
    var response = await client.GetAsync(cardUrl);
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
