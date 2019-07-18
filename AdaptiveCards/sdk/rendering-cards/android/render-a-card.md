---
title: Rendern einer Karte – Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 55e0fa828abf3b9af857d1deb7ecd3744b5a7280
ms.sourcegitcommit: 8c8067206f283d97a5aa4ec65ba23d3fe18962f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299527"
---
# <a name="render-a-card---android"></a><span data-ttu-id="d47b3-102">Rendern einer Karte – Android</span><span class="sxs-lookup"><span data-stu-id="d47b3-102">Render a card - Android</span></span>

<span data-ttu-id="d47b3-103">Hier findest du Informationen zum Rendern einer Karte mit dem Android SDK.</span><span class="sxs-lookup"><span data-stu-id="d47b3-103">Here's how to render a card using the Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="d47b3-104">Erstellen einer Objektinstanz für die adaptive Karte aus JSON-Text</span><span class="sxs-lookup"><span data-stu-id="d47b3-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> <span data-ttu-id="d47b3-105">**Wichtige Änderungen für v1.2**</span><span class="sxs-lookup"><span data-stu-id="d47b3-105">**Breaking changes for v1.2**</span></span>
> 

1. <span data-ttu-id="d47b3-106">Der elementparameserregistration-Parameter wurde in den Parametertext geändert, der ein elementparameserregistration-Objekt und ein aktionseserregistration-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d47b3-106">ElementParserRegistration parameter changed to ParseContext which includes an ElementParserRegistration and an ActionParserRegistration object</span></span>

```java
ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

<span data-ttu-id="d47b3-107">oder</span><span class="sxs-lookup"><span data-stu-id="d47b3-107">or</span></span>

```java
ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

## <a name="render-a-card"></a><span data-ttu-id="d47b3-108">Rendern einer Karte</span><span class="sxs-lookup"><span data-stu-id="d47b3-108">Render a card</span></span>

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.getView();
```
