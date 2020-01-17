---
title: Native Formatierung – Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: d0c6b56e0497b78aa149f73dc1d32537689c0386
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145480"
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
