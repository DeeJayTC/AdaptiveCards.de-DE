---
title: Rendering einer Karte (xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: dc1d48e05e99d6254b9253efa7145cefeb2ed17c
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145974"
---
# <a name="render-a-card---xamarinandroid"></a>Rendering einer Karte: xamarin. Android

Im folgenden wird beschrieben, wie Sie eine Karte mithilfe von xamarin. Android SDK Rendering.

## <a name="create-adaptive-card-object-instance-from-json-text"></a>Erstellen einer Objektinstanz für die adaptive Karte aus JSON-Text

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
AdaptiveCard adaptiveCard = parseResult.AdaptiveCard;
```

oder Sie können ein ```ParseContext```-Objekt verwenden, um benutzerdefinierte Elemente, die in ihrer adaptiven Karte enthalten sind, wie folgt zu deserialisieren:

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

oder

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

## <a name="render-a-card"></a>Rendern einer Karte

Um eine Karte zu erstellen, benötigen Sie einige Informationen
* Kontext: ist aus der Aktivität, in der die Karte gehostet wird, zugänglich.
* fragmentmanager: kann auch aus der hostingaktivität abgerufen werden.
* cardaction Handler: Instanz von [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) zum Verwalten des Aktions Verhaltens

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;
// ...

var renderedCard = AdaptiveCardRenderer.Instance.Render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.View;
```
