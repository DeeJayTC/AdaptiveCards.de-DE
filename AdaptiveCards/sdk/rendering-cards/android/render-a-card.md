---
title: Rendern einer Karte – Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: a4eeda54a80c959ff9a1246371240954b4c3fb12
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134290"
---
# <a name="render-a-card---android"></a><span data-ttu-id="09da9-102">Rendern einer Karte – Android</span><span class="sxs-lookup"><span data-stu-id="09da9-102">Render a card - Android</span></span>

<span data-ttu-id="09da9-103">Hier findest du Informationen zum Rendern einer Karte mit dem Android SDK.</span><span class="sxs-lookup"><span data-stu-id="09da9-103">Here's how to render a card using the Android SDK.</span></span>

## <a name="create-adaptive-card-object-instance-from-json-text"></a><span data-ttu-id="09da9-104">Erstellen einer Objektinstanz für die adaptive Karte aus JSON-Text</span><span class="sxs-lookup"><span data-stu-id="09da9-104">Create Adaptive Card Object Instance from JSON Text</span></span>

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> <span data-ttu-id="09da9-105">**Wichtige Änderungen für v1.2**</span><span class="sxs-lookup"><span data-stu-id="09da9-105">**Breaking changes for v1.2**</span></span>
> 
> 1. <span data-ttu-id="09da9-106">Der Parameter „ElementParserRegistration“ wurde in „ParseContext“ geändert. Dieses Element enthält ein ElementParserRegistration- und ein ActionRegistration-Objekt.</span><span class="sxs-lookup"><span data-stu-id="09da9-106">ElementParserRegistration parameter changed to ParseContext which includes an ElementParserRegistration and an ActionRegistration object</span></span>
> ```java
> ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
> ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
> ```

## <a name="render-a-card"></a><span data-ttu-id="09da9-107">Rendern einer Karte</span><span class="sxs-lookup"><span data-stu-id="09da9-107">Render a card</span></span>

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
View v = renderedCard.getView();
```
