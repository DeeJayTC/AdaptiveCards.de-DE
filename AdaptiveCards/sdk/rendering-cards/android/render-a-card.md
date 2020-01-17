---
title: Rendern einer Karte – Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: c9fbfa788af0b0c7f16824bf9c369fa59a1b80f5
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145470"
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

1. Der elementparameserregistration-Parameter wurde in den Parametertext geändert, der ein elementparameserregistration-Objekt und ein aktionseserregistration-Objekt enthält.

```java
ParseContext context = new ParseContext(); // Empty parseContext so only known elements up to v1.2 will be parsed
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

oder

```java
ParseContext context = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

## <a name="render-a-card"></a>Rendern einer Karte

```java
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
View v = renderedCard.getView();
```
