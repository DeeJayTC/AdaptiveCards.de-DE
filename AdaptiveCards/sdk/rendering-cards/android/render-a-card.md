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
# <a name="render-a-card---android"></a>Rendern einer Karte – Android

Hier findest du Informationen zum Rendern einer Karte mit dem Android SDK.

## <a name="create-adaptive-card-object-instance-from-json-text"></a>Erstellen einer Objektinstanz für die adaptive Karte aus JSON-Text

```java
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, elementParserRegistration);
AdaptiveCard adaptiveCard = parseResult.GetAdaptiveCard();
```
> [!IMPORTANT]
> **Wichtige Änderungen für v1.2**
> 
> 1. Der Parameter „ElementParserRegistration“ wurde in „ParseContext“ geändert. Dieses Element enthält ein ElementParserRegistration- und ein ActionRegistration-Objekt.
> ```java
> ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
> ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
> ```

## <a name="render-a-card"></a>Rendern einer Karte

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
View v = renderedCard.getView();
```
