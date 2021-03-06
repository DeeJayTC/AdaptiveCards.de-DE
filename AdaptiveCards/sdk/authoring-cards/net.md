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
# <a name="net-sdk-for-authoring-cards"></a>.NET SDK zum Erstellen von Karten

Wie auf der Seite " [Getting Started](../../authoring-cards/getting-started.md) " beschrieben, ist eine Adaptive Karte ein JSON-Objektmodell. Die .NET-Bibliothek vereinfacht das Arbeiten mit diesem JSON-Code erheblich.


## <a name="nuget-install"></a>Nuget-Installation
Das `AdaptiveCards` nuget-Paket bietet Typen für die Arbeit mit adaptiven Karten in .net.

[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)

```console
Install-Package AdaptiveCards
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a>Beispiel: Erstellen einer adaptivecard und Serialisieren in JSON

In diesem Beispiel wird veranschaulicht, wie eine Adaptive Karte mithilfe C# von Standardobjekten erstellt und anschließend für den Transport über das Netzwerk in JSON serialisiert wird.

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

## <a name="example-parse-an-adaptivecard-from-json"></a>Beispiel: Analysieren einer adaptivecard aus JSON

In diesem Beispiel wird veranschaulicht, wie Sie eine JSON-Nutzlast in einer adaptiven Karte analysieren. Dies vereinfacht die Bearbeitung des Objektmodells oder sogar das renderingadaptiver Karten in ihrer App mithilfe unserer [Renderer-sdche](../../rendering-cards/getting-started.md).

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
