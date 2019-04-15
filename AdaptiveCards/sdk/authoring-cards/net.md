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
# <a name="net-sdk-for-authoring-cards"></a>.NET SDK zum Erstellen von Karten

Wie wir unter den [Einstieg](../../authoring-cards/getting-started.md) Seite eine Adaptive Card ist ein JSON-Objektmodell. Die Bibliothek für .NET kann die Arbeit mit diesen JSON-Code viel einfacher.

> [!IMPORTANT]
> **Wichtige Änderungen gegenüber v0.5**
> 
> 1. Paket umbenannt `Microsoft.AdaptiveCards` auf `AdaptiveCards`
> 1. Aufgrund der häufigen Namenskonflikte mit Framework-Typen haben alle Modellklassen "Adaptive" als Präfix vorangestellt wurde. Z. B. `TextBlock` ist jetzt `AdaptiveTextBlock`
> 1. Alle Eigenschaften von "Uri" wurden vom Typ `string` auf `Uri`
> 1. Es wurden außerdem einige schemaänderungen in der Vorschau v0.5 sind [die nachfolgend beschrieben](https://github.com/Microsoft/AdaptiveCards/pull/633)


## <a name="nuget-install"></a>Installieren von NuGet
Die `AdaptiveCards` NuGet-Paket stellt Typen bereit, für den Umgang mit adaptive Cards in .NET

[![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.svg)](https://www.nuget.org/packages/AdaptiveCards)

```console
Install-Package AdaptiveCards -IncludePrerelease
```

## <a name="example-create-an-adaptivecard-and-serialize-to-json"></a>Beispiel: Erstellen Sie eine AdaptiveCard und Serialisieren in JSON

In diesem Beispiel wird veranschaulicht, wie erstellen Sie eine Adaptive Card mit standardmäßigen C# Objekte und serialisiert sie anschließend in JSON für den Transport über das Netzwerk.

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

## <a name="example-parse-an-adaptivecard-from-json"></a>Beispiel: Ein AdaptiveCard aus JSON analysieren

Dieses Beispiel zeigt, wie Sie eine JSON-Nutzlast in eine Adaptive Card zu analysieren. Dies erleichtert es auf das Objektmodell oder sogar Rendering mit Adaptive Cards in Ihrer app mit unseren [Renderer SDKs](../../rendering-cards/getting-started.md).

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
