---
title: Icardaktionhandler-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 8b526ccb66be3a261384d6c4f68a850558e2549e
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146154"
---
# <a name="icardactionhandler"></a><span data-ttu-id="17086-102">Icardaktionshandler</span><span class="sxs-lookup"><span data-stu-id="17086-102">ICardActionHandler</span></span>

```csharp
public interface ICardActionHandler : IJavaObject 
```

<span data-ttu-id="17086-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="17086-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler
```

### <a name="summary"></a><span data-ttu-id="17086-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="17086-104">Summary</span></span>

| <span data-ttu-id="17086-105">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="17086-105">Public methods</span></span> | |
| --- | ---- |
| ```abstract void``` | [```OnAction (BaseActionElement p0, RenderedAdaptiveCard p1)```](#onaction) |
| ```abstract void``` | [```OnMediaPlay (BaseCardElement p0, RenderedAdaptiveCard p1)```](#onmediaplay) |
| ```abstract void``` | [```OnMediaStop (BaseCardElement p0, RenderedAdaptiveCard p1)```](#onmediastop) |

## <a name="public-methods"></a><span data-ttu-id="17086-106">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="17086-106">Public Methods</span></span>
--- 
### <a id="onaction"></a><span data-ttu-id="17086-107">OnAction</span><span class="sxs-lookup"><span data-stu-id="17086-107">OnAction</span></span>
<p style='text-align:right'><span data-ttu-id="17086-108">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="17086-108">Added in version 0.1.0</span></span></p>

```csharp
void OnAction (BaseActionElement p0, RenderedAdaptiveCard p1)
```

<span data-ttu-id="17086-109">Der Listener wird aufgerufen, wenn auf eine openurlaction-, submitAction-oder showcardaction-Aktion (wenn nicht Inline) geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="17086-109">Listener called when a OpenUrlAction, SubmitAction or ShowCardAction (if not inline) are clicked.</span></span>

| <span data-ttu-id="17086-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="17086-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="17086-111">P0</span><span class="sxs-lookup"><span data-stu-id="17086-111">p0</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElement``` |
| <span data-ttu-id="17086-112">p1</span><span class="sxs-lookup"><span data-stu-id="17086-112">p1</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) |

#### <a name="sample"></a><span data-ttu-id="17086-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17086-113">Sample</span></span>

```csharp
public class MyCardActionHandler : ICardActionHandler
{

    public void OnAction(BaseActionElement element, RenderedAdaptiveCard renderedCard)
    {
        ActionType actionType = element.ElementType;
        if (actionType == ActionType.Submit)
        {
            var inputs = renderedCard.Inputs;
            string inputValues = string.Empty;
            foreach (var inputString in inputs)
            {
                inputValues += $"{{{inputString.Key} : {inputString.Value}}}\n";
            }
            submitData(inputValues);
        }
        else if (actionType == ActionType.ShowCard)
        {
            var showcardAction = ShowCardAction.Dynamic_cast(element);
            showCard(showcardAction.Card)
        }
        else if (actionType == ActionType.OpenUrl)
        {
            var openUrlAction = OpenUrlAction.Dynamic_cast(element);
            openUrl(openUrlAction.Url);
        }
    }
}
```

---
### <a id="onmediaplay"></a><span data-ttu-id="17086-114">Onmediaplay</span><span class="sxs-lookup"><span data-stu-id="17086-114">OnMediaPlay</span></span>
<p style='text-align:right'><span data-ttu-id="17086-115">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="17086-115">Added in version 0.1</span></span></p>

```csharp
void OnMediaPlay (BaseCardElement p0, RenderedAdaptiveCard p1)
```

<span data-ttu-id="17086-116">Der Listener wird aufgerufen, wenn das Medien Element gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="17086-116">Listener called when the media element starts playing.</span></span>

| <span data-ttu-id="17086-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="17086-117">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="17086-118">P0</span><span class="sxs-lookup"><span data-stu-id="17086-118">p0</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElement``` |
| <span data-ttu-id="17086-119">p1</span><span class="sxs-lookup"><span data-stu-id="17086-119">p1</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) |

#### <a name="sample"></a><span data-ttu-id="17086-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17086-120">Sample</span></span>

```csharp
public class MyCardActionHandler : ICardActionHandler
{
    public void OnMediaPlay(BaseCardElement element, RenderedAdaptiveCard renderedCard)
    {
    }
}
```

--- 

### <a id="onmediastop"></a><span data-ttu-id="17086-121">Onmediastop</span><span class="sxs-lookup"><span data-stu-id="17086-121">OnMediaStop</span></span>
<p style='text-align:right'><span data-ttu-id="17086-122">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="17086-122">Added in version 0.1</span></span></p>

```csharp
void OnMediaStop (BaseCardElement p0, RenderedAdaptiveCard p1)
```

<span data-ttu-id="17086-123">Der Listener wird aufgerufen, wenn das Medien Element beendet wird.</span><span class="sxs-lookup"><span data-stu-id="17086-123">Listener called when the media element stops playing.</span></span>

| <span data-ttu-id="17086-124">Parameter</span><span class="sxs-lookup"><span data-stu-id="17086-124">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="17086-125">P0</span><span class="sxs-lookup"><span data-stu-id="17086-125">p0</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElement``` |
| <span data-ttu-id="17086-126">p1</span><span class="sxs-lookup"><span data-stu-id="17086-126">p1</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) |

#### <a name="sample"></a><span data-ttu-id="17086-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17086-127">Sample</span></span>

```csharp
public class MyCardActionHandler : ICardActionHandler
{
    public void OnMediaStop(BaseCardElement element, RenderedAdaptiveCard renderedCard)
    {
    }
}
```