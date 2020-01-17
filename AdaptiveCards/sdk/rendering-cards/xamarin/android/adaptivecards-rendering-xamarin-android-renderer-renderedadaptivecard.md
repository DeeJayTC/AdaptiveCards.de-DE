---
title: Renderedadaptivecard-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 608b28638ce6ed0a218cfc8dbbe73f22de1ab8cb
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145994"
---
# <a name="renderedadaptivecard"></a><span data-ttu-id="38053-102">Renderedadaptivecard</span><span class="sxs-lookup"><span data-stu-id="38053-102">RenderedAdaptiveCard</span></span>

```csharp
public class RenderedAdaptiveCard : Java.Lang.Object
```

<span data-ttu-id="38053-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="38053-103">**Namespace**</span></span>

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a><span data-ttu-id="38053-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="38053-104">Summary</span></span>

| <span data-ttu-id="38053-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="38053-105">Attributes</span></span> | |
| ---- | --- |
| <span data-ttu-id="38053-106">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="38053-106">AdaptiveCard</span></span> | <span data-ttu-id="38053-107">Logische Darstellung der gerenderten adaptiven Karte.</span><span class="sxs-lookup"><span data-stu-id="38053-107">Logical representation of the rendered adaptive card.</span></span> |
| <span data-ttu-id="38053-108">Eingaben</span><span class="sxs-lookup"><span data-stu-id="38053-108">Inputs</span></span> | <span data-ttu-id="38053-109">Das Wörterbuch des Eingabe Elements und der vom Benutzer hinzugefügten Informationen.</span><span class="sxs-lookup"><span data-stu-id="38053-109">Dictionary of input element and information added by the user.</span></span> |
| <span data-ttu-id="38053-110">„Ansicht”</span><span class="sxs-lookup"><span data-stu-id="38053-110">View</span></span> | <span data-ttu-id="38053-111">Visuelles Ergebnis aus dem Renderingprozess.</span><span class="sxs-lookup"><span data-stu-id="38053-111">Visual result from the rendering process.</span></span> |
| <span data-ttu-id="38053-112">Warnungen</span><span class="sxs-lookup"><span data-stu-id="38053-112">Warnings</span></span> | <span data-ttu-id="38053-113">Liste der Warnungen, die vom Renderingprozess erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="38053-113">List of warnings produced from the rendering process.</span></span> |

&nbsp;

| <span data-ttu-id="38053-114">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="38053-114">Public methods</span></span> | |
| --- | ---- |
| ```void``` | [```AddWarning AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning warning)```](#addwarning) |

## <a name="public-methods"></a><span data-ttu-id="38053-115">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="38053-115">Public Methods</span></span>

---

### <a id="addwarning"></a><span data-ttu-id="38053-116">Addwarning</span><span class="sxs-lookup"><span data-stu-id="38053-116">AddWarning</span></span>
<p style='text-align:right'><span data-ttu-id="38053-117">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="38053-117">Added in version 0.1</span></span></p>

```csharp
public void AddWarning (AdaptiveWarning warning)

```

<span data-ttu-id="38053-118">Fügt der Warnungs Liste eine Warnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="38053-118">Adds a warning to the warning list.</span></span>

| <span data-ttu-id="38053-119">Parameter</span><span class="sxs-lookup"><span data-stu-id="38053-119">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="38053-120">Warnung</span><span class="sxs-lookup"><span data-stu-id="38053-120">warning</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning``` |
