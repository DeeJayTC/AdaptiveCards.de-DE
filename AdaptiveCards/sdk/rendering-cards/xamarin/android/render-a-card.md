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
# <a name="render-a-card---xamarinandroid"></a><span data-ttu-id="23486-102">Rendering einer Karte: xamarin. Android</span><span class="sxs-lookup"><span data-stu-id="23486-102">Render a card - Xamarin.Android</span></span>

<span data-ttu-id="23486-103">Im folgenden wird beschrieben, wie Sie eine Karte mithilfe von xamarin. Android SDK Rendering.</span><span class="sxs-lookup"><span data-stu-id="23486-103">Here's how to render a card using the Xamarin.Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="23486-104">Erstellen einer Objektinstanz für die adaptive Karte aus JSON-Text</span><span class="sxs-lookup"><span data-stu-id="23486-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
AdaptiveCard adaptiveCard = parseResult.AdaptiveCard;
```

<span data-ttu-id="23486-105">oder Sie können ein ```ParseContext```-Objekt verwenden, um benutzerdefinierte Elemente, die in ihrer adaptiven Karte enthalten sind, wie folgt zu deserialisieren:</span><span class="sxs-lookup"><span data-stu-id="23486-105">or you can also use a ```ParseContext``` object to be able to deserialize custom elements that are included in your adaptive card like this:</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

<span data-ttu-id="23486-106">oder</span><span class="sxs-lookup"><span data-stu-id="23486-106">or</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, context);
```

## <a name="render-a-card"></a><span data-ttu-id="23486-107">Rendern einer Karte</span><span class="sxs-lookup"><span data-stu-id="23486-107">Render a card</span></span>

<span data-ttu-id="23486-108">Um eine Karte zu erstellen, benötigen Sie einige Informationen</span><span class="sxs-lookup"><span data-stu-id="23486-108">To be able to render a card you'll need some information</span></span>
* <span data-ttu-id="23486-109">Kontext: ist aus der Aktivität, in der die Karte gehostet wird, zugänglich.</span><span class="sxs-lookup"><span data-stu-id="23486-109">context: Obtainable from the Activity the card is hosted in</span></span>
* <span data-ttu-id="23486-110">fragmentmanager: kann auch aus der hostingaktivität abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="23486-110">fragmentManager: can also be retrieved from the hosting activity</span></span>
* <span data-ttu-id="23486-111">cardaction Handler: Instanz von [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) zum Verwalten des Aktions Verhaltens</span><span class="sxs-lookup"><span data-stu-id="23486-111">cardActionHandler: instance of [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) to manage the action behaviour</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer;
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;
// ...

var renderedCard = AdaptiveCardRenderer.Instance.Render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.View;
```
