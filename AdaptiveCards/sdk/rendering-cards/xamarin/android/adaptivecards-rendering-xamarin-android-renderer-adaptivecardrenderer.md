---
title: Adaptivecardrenderer-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: c90fb22f60fa75a37b6372c2660f8599535fd961
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146064"
---
# <a name="adaptivecardrenderer"></a><span data-ttu-id="40566-102">Adaptivecardrenderer</span><span class="sxs-lookup"><span data-stu-id="40566-102">AdaptiveCardRenderer</span></span>

```csharp
public class AdaptiveCardRenderer : global::Java.Lang.Object
```

<span data-ttu-id="40566-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="40566-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a><span data-ttu-id="40566-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="40566-104">Summary</span></span>

| <span data-ttu-id="40566-105">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="40566-105">Public methods</span></span> | |
| --- | ---- |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler)```](#render0) |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler, HostConfig hostConfig)```](#render1) |

## <a name="public-methods"></a><span data-ttu-id="40566-106">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="40566-106">Public Methods</span></span>

---

### <a id="render0"></a><span data-ttu-id="40566-107">Bieten</span><span class="sxs-lookup"><span data-stu-id="40566-107">Render</span></span>
<p style='text-align:right'><span data-ttu-id="40566-108">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="40566-108">Added in version 0.1.0</span></span></p>

```csharp
public RenderedAdaptiveCard Render (Context context, 
                                    FragmentManager fragmentManager, 
                                    AdaptiveCard adaptiveCard,
                                    ICardActionHandler cardActionHandler)
```

<span data-ttu-id="40566-109">Rendert die angegebene Adaptive Karte mit Standardwerten für die Host Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="40566-109">Renders the specified adaptive card with default values for the host config.</span></span>

| <span data-ttu-id="40566-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="40566-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="40566-111">context</span><span class="sxs-lookup"><span data-stu-id="40566-111">context</span></span> | ```Android.Content.Context``` |
| <span data-ttu-id="40566-112">fragmentmanager</span><span class="sxs-lookup"><span data-stu-id="40566-112">fragmentManager</span></span> | ```Android.Support.V4.App.FragmentManager``` |
| <span data-ttu-id="40566-113">adaptivecard</span><span class="sxs-lookup"><span data-stu-id="40566-113">adaptiveCard</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| <span data-ttu-id="40566-114">cardhandhandler</span><span class="sxs-lookup"><span data-stu-id="40566-114">cardActionHandler</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |

| <span data-ttu-id="40566-115">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="40566-115">Returns</span></span> |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a><span data-ttu-id="40566-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40566-116">Sample</span></span>

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler);
```

---

### <a id="render1"></a><span data-ttu-id="40566-117">Bieten</span><span class="sxs-lookup"><span data-stu-id="40566-117">Render</span></span>
<p style='text-align:right'><span data-ttu-id="40566-118">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="40566-118">Added in version 0.1.0</span></span></p>

```csharp
RenderedAdaptiveCard Render (Context context, 
                            FragmentManager fragmentManager, 
                            AdaptiveCard adaptiveCard, 
                            ICardActionHandler cardActionHandler, 
                            HostConfig hostConfig)
```

<span data-ttu-id="40566-119">Rendert die angegebene Adaptive Karte mithilfe der angegebenen Host Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="40566-119">Renders the specified adaptive card with using the given host config.</span></span>

| <span data-ttu-id="40566-120">Parameter</span><span class="sxs-lookup"><span data-stu-id="40566-120">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="40566-121">context</span><span class="sxs-lookup"><span data-stu-id="40566-121">context</span></span> | ```Android.Content.Context``` |
| <span data-ttu-id="40566-122">fragmentmanager</span><span class="sxs-lookup"><span data-stu-id="40566-122">fragmentManager</span></span> | ```Android.Support.V4.App.FragmentManager``` |
| <span data-ttu-id="40566-123">adaptivecard</span><span class="sxs-lookup"><span data-stu-id="40566-123">adaptiveCard</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| <span data-ttu-id="40566-124">cardhandhandler</span><span class="sxs-lookup"><span data-stu-id="40566-124">cardActionHandler</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |
| <span data-ttu-id="40566-125">hostconfig</span><span class="sxs-lookup"><span data-stu-id="40566-125">hostConfig</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HostConfig``` |

| <span data-ttu-id="40566-126">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="40566-126">Returns</span></span> | |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a><span data-ttu-id="40566-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40566-127">Sample</span></span>

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler, hostConfig);
```