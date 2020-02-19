---
title: 'Native Formatierung: .net WPF SDK'
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 204845f942be4e7d04e20e9cd64d826daef26e93
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454023"
---
# <a name="native-styling---net-wpf"></a><span data-ttu-id="e6ac2-102">Native Formatierung: .net WPF</span><span class="sxs-lookup"><span data-stu-id="e6ac2-102">Native styling - .NET WPF</span></span>

<span data-ttu-id="e6ac2-103">Obwohl die Host Konfiguration den größten Teil der einzelnen Plattformen bietet, ist es wahrscheinlich, dass Sie auf jeder Plattform eine native Formatierung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="e6ac2-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="e6ac2-104">WPF vereinfacht dies, indem es Ihnen ermöglicht wird, ein ResourceDictionary für differenzierte Formatierung, Verhalten, Animationen usw. zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="e6ac2-104">WPF makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="e6ac2-105">Element</span><span class="sxs-lookup"><span data-stu-id="e6ac2-105">Element</span></span> | <span data-ttu-id="e6ac2-106">Stilnamen</span><span class="sxs-lookup"><span data-stu-id="e6ac2-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="e6ac2-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="e6ac2-107">AdaptiveCard</span></span> | <span data-ttu-id="e6ac2-108">Adaptive.Card</span><span class="sxs-lookup"><span data-stu-id="e6ac2-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="e6ac2-109">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="e6ac2-109">Action.OpenUrl</span></span>  | <span data-ttu-id="e6ac2-110">Adaptive.Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="e6ac2-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="e6ac2-111">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="e6ac2-111">Action.ShowCard</span></span> | <span data-ttu-id="e6ac2-112">Adaptive.Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="e6ac2-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="e6ac2-113">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="e6ac2-113">Action.Submit</span></span>  | <span data-ttu-id="e6ac2-114">Adaptive.Action.Submit</span><span class="sxs-lookup"><span data-stu-id="e6ac2-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="e6ac2-115">Spalte</span><span class="sxs-lookup"><span data-stu-id="e6ac2-115">Column</span></span> | <span data-ttu-id="e6ac2-116">Adaptive. Column, Adaptive. Action. Tap</span><span class="sxs-lookup"><span data-stu-id="e6ac2-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="e6ac2-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="e6ac2-117">ColumnSet</span></span> | <span data-ttu-id="e6ac2-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="e6ac2-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="e6ac2-119">Container</span><span class="sxs-lookup"><span data-stu-id="e6ac2-119">Container</span></span> | <span data-ttu-id="e6ac2-120">Adaptive. Container</span><span class="sxs-lookup"><span data-stu-id="e6ac2-120">Adaptive.Container</span></span>|
| <span data-ttu-id="e6ac2-121">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="e6ac2-121">Input.ChoiceSet</span></span> | <span data-ttu-id="e6ac2-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span><span class="sxs-lookup"><span data-stu-id="e6ac2-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="e6ac2-123">Input. Date</span><span class="sxs-lookup"><span data-stu-id="e6ac2-123">Input.Date</span></span> | <span data-ttu-id="e6ac2-124">Adaptive.Input.Text.Date</span><span class="sxs-lookup"><span data-stu-id="e6ac2-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="e6ac2-125">Eingabe. Zahl</span><span class="sxs-lookup"><span data-stu-id="e6ac2-125">Input.Number</span></span> | <span data-ttu-id="e6ac2-126">Adaptive.Input.Text.Number</span><span class="sxs-lookup"><span data-stu-id="e6ac2-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="e6ac2-127">Input.Text</span><span class="sxs-lookup"><span data-stu-id="e6ac2-127">Input.Text</span></span> | <span data-ttu-id="e6ac2-128">Adaptive. Input. Text</span><span class="sxs-lookup"><span data-stu-id="e6ac2-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="e6ac2-129">Eingabe. Zeit</span><span class="sxs-lookup"><span data-stu-id="e6ac2-129">Input.Time</span></span> | <span data-ttu-id="e6ac2-130">Adaptive.Input.Text.Time</span><span class="sxs-lookup"><span data-stu-id="e6ac2-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="e6ac2-131">Eingabe. Umschalten</span><span class="sxs-lookup"><span data-stu-id="e6ac2-131">Input.Toggle</span></span>| <span data-ttu-id="e6ac2-132">Adaptive.Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="e6ac2-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="e6ac2-133">Bild</span><span class="sxs-lookup"><span data-stu-id="e6ac2-133">Image</span></span>  | <span data-ttu-id="e6ac2-134">Adaptive. Image</span><span class="sxs-lookup"><span data-stu-id="e6ac2-134">Adaptive.Image</span></span> |
| <span data-ttu-id="e6ac2-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="e6ac2-135">ImageSet</span></span>  | <span data-ttu-id="e6ac2-136">Adaptive.ImageSet</span><span class="sxs-lookup"><span data-stu-id="e6ac2-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="e6ac2-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="e6ac2-137">FactSet</span></span> | <span data-ttu-id="e6ac2-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span><span class="sxs-lookup"><span data-stu-id="e6ac2-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="e6ac2-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="e6ac2-139">TextBlock</span></span>  | <span data-ttu-id="e6ac2-140">Adaptive.TextBlock</span><span class="sxs-lookup"><span data-stu-id="e6ac2-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="e6ac2-141">Dieses Beispiel-XAML-Ressourcen Wörterbuch, das den Hintergrund aller Textblöcke auf Aqua festlegt.</span><span class="sxs-lookup"><span data-stu-id="e6ac2-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="e6ac2-142">Wahrscheinlich möchten Sie etwas höher als dieses 😁</span><span class="sxs-lookup"><span data-stu-id="e6ac2-142">You will probably want something more advanced than this 😁</span></span>

```xml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Style x:Key="Adaptive.TextBlock" TargetType="TextBlock">
        <Setter Property="Background" Value="Aqua"></Setter>
    </Style>
</ResourceDictionary>
```
```csharp
// Use a ResourceDictionary instance
// DON'T use this property if rendering from a server
renderer.Resources = myResourceDictionary;

// ... or load it from a file path
// USE this if rendering from a server
renderer.ResourcesPath = <path-to-my-resource-dictionary.xaml>;
```

> [!IMPORTANT]
> <span data-ttu-id="e6ac2-143">**Hinweis zur serverseitigen Bildgenerierung** Der WPF-Renderer stellt eine `RenderCardToImageAsync`-Methode bereit, die für die serverseitige Bildgenerierung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6ac2-143">**A note about server-side image generation** The WPF renderer provides a `RenderCardToImageAsync` method that can be used for server-side image generation.</span></span> <span data-ttu-id="e6ac2-144">Sie dürfen die `ResourcesPath`-Eigenschaft nur verwenden, wenn Sie in dieser Umgebung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6ac2-144">You must only use the `ResourcesPath` property if used in this environment.</span></span> <span data-ttu-id="e6ac2-145">Weitere Informationen finden Sie in den [Bild Rendering](../net-image/getting-started.md) -Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="e6ac2-145">See the [Image Rendering](../net-image/getting-started.md) docs for more</span></span>