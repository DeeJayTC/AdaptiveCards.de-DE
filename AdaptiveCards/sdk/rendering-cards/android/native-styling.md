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
# <a name="native-styling---android"></a><span data-ttu-id="65ba8-102">Native Formatierung – Android</span><span class="sxs-lookup"><span data-stu-id="65ba8-102">Native styling - Android</span></span>

<span data-ttu-id="65ba8-103">Die native Formatierung wird für den Android-Renderer nicht unterstützt, v1.2 führt die Unterstützung für die Formatierung einiger Eigenschaften ein:</span><span class="sxs-lookup"><span data-stu-id="65ba8-103">Native styling is not supported on the android renderer, v1.2 introduces the support for styling some properties:</span></span>

## <a name="action-sentiment"></a><span data-ttu-id="65ba8-104">Aktionsstimmung</span><span class="sxs-lookup"><span data-stu-id="65ba8-104">Action Sentiment</span></span>

<span data-ttu-id="65ba8-105">Die Aktionsstimmung ist in **v1. 2** integriert. Es werden zwar nicht so viele Formate unterstützt wie in anderen Versionen, Aktionen mit der Stimmung *destructive* oder *positive* können jedoch formatiert werden, indem eine gültige Formatierung implementiert und die folgende Zeile in „styles.xml“ für dein Projekt eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="65ba8-105">Action sentiment is included in **v1.2** and while not supporting as many styles as other versions, actions with *destructive* or *positive* sentiment can be styled by implementing a valid style and adding the following line into the styles.xml for your project</span></span>

```styles.xml
 <item name="adaptiveActionDestructive">@style/adaptiveActionDestructive</item>
 <item name="adaptiveActionPositive">@style/adaptiveActionPositive</item>
```

## <a name="inline-action"></a><span data-ttu-id="65ba8-106">Inlineaktion</span><span class="sxs-lookup"><span data-stu-id="65ba8-106">Inline Action</span></span>

<span data-ttu-id="65ba8-107">Texteingaben mit einer Inlineaktion ermöglichen das Formatieren der Aktion, die gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="65ba8-107">Text inputs with an inline action allows styling for the action being rendered.</span></span> <span data-ttu-id="65ba8-108">Dadurch kann die Aktion als Schaltfläche (adaptiveInlineAction) oder als Bild (adaptiveInlineActionImage) formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="65ba8-108">This allows styling the action as a button (adaptiveInlineAction) or as an image (adaptiveInlineActionImage)</span></span>

```styles.xml
 <item name="adaptiveInlineAction">@style/adaptiveInlineAction</item>
 <item name="adaptiveInlineActionImage">@style/adaptiveInlineActionImage</item>
```

> [!IMPORTANT]
> <span data-ttu-id="65ba8-109">Alle Elementnamen müssen wie hier gezeigt beibehalten werden, da der Renderer nach genau diesen Namen sucht.</span><span class="sxs-lookup"><span data-stu-id="65ba8-109">All item names must be kept as shown here as the renderer looks for those exact names</span></span>
