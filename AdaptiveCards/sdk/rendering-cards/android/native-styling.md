---
title: Native Formatierung – Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: ebb033c68b9aedcaacb1989ffb1bec48707a9026
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134249"
---
# <a name="native-styling---android"></a>Native Formatierung – Android

Die native Formatierung wird für den Android-Renderer nicht unterstützt, v1.2 führt die Unterstützung für die Formatierung einiger Eigenschaften ein:

## <a name="action-sentiment"></a>Aktionsstimmung

Die Aktionsstimmung ist in **v1. 2** integriert. Es werden zwar nicht so viele Formate unterstützt wie in anderen Versionen, Aktionen mit der Stimmung *destructive* oder *positive* können jedoch formatiert werden, indem eine gültige Formatierung implementiert und die folgende Zeile in „styles.xml“ für dein Projekt eingefügt wird.

```styles.xml
 <item name="adaptiveActionDestructive">@style/adaptiveActionDestructive</item>
 <item name="adaptiveActionPositive">@style/adaptiveActionPositive</item>
```

## <a name="inline-action"></a>Inlineaktion

Texteingaben mit einer Inlineaktion ermöglichen das Formatieren der Aktion, die gerendert wird. Dadurch kann die Aktion als Schaltfläche (adaptiveInlineAction) oder als Bild (adaptiveInlineActionImage) formatiert werden.

```styles.xml
 <item name="adaptiveInlineAction">@style/adaptiveInlineAction</item>
 <item name="adaptiveInlineActionImage">@style/adaptiveInlineActionImage</item>
```

> [!IMPORTANT]
> Alle Elementnamen müssen wie hier gezeigt beibehalten werden, da der Renderer nach genau diesen Namen sucht.
