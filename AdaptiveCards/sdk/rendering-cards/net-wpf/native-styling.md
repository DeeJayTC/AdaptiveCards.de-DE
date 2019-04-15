---
title: Native Stil - WPF-SDK für .NET
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: ee5bec1a11f39ad69d40e57410c105b50ba45981
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552722"
---
# <a name="native-styling---net-wpf"></a><span data-ttu-id="9a943-102">Native formatieren – WPF für .NET</span><span class="sxs-lookup"><span data-stu-id="9a943-102">Native styling - .NET WPF</span></span>

<span data-ttu-id="9a943-103">Während der Host-Konfiguration die meisten haben, erhalten Sie die Art und Weise gibt es auf jeder Plattform, ist es wahrscheinlich, dass Sie einige native Formatierungen auf jeder Plattform zu tun hat.</span><span class="sxs-lookup"><span data-stu-id="9a943-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="9a943-104">WPF vereinfacht, sodass Sie einem ResourceDictionary für detaillierte Formatierung, Verhalten, Animationen usw. zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="9a943-104">WPF makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="9a943-105">Element</span><span class="sxs-lookup"><span data-stu-id="9a943-105">Element</span></span> | <span data-ttu-id="9a943-106">Namen</span><span class="sxs-lookup"><span data-stu-id="9a943-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="9a943-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="9a943-107">AdaptiveCard</span></span> | <span data-ttu-id="9a943-108">Adaptive.Card</span><span class="sxs-lookup"><span data-stu-id="9a943-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="9a943-109">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="9a943-109">Action.OpenUrl</span></span>  | <span data-ttu-id="9a943-110">Adaptive.Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="9a943-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="9a943-111">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="9a943-111">Action.ShowCard</span></span> | <span data-ttu-id="9a943-112">Adaptive.Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="9a943-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="9a943-113">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="9a943-113">Action.Submit</span></span>  | <span data-ttu-id="9a943-114">Adaptive.Action.Submit</span><span class="sxs-lookup"><span data-stu-id="9a943-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="9a943-115">Column</span><span class="sxs-lookup"><span data-stu-id="9a943-115">Column</span></span> | <span data-ttu-id="9a943-116">Adaptive.Column, Adaptive.Action.Tap</span><span class="sxs-lookup"><span data-stu-id="9a943-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="9a943-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="9a943-117">ColumnSet</span></span> | <span data-ttu-id="9a943-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="9a943-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="9a943-119">Container</span><span class="sxs-lookup"><span data-stu-id="9a943-119">Container</span></span> | <span data-ttu-id="9a943-120">Adaptive.Container</span><span class="sxs-lookup"><span data-stu-id="9a943-120">Adaptive.Container</span></span>|
| <span data-ttu-id="9a943-121">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="9a943-121">Input.ChoiceSet</span></span> | <span data-ttu-id="9a943-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span><span class="sxs-lookup"><span data-stu-id="9a943-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="9a943-123">Input.Date</span><span class="sxs-lookup"><span data-stu-id="9a943-123">Input.Date</span></span> | <span data-ttu-id="9a943-124">Adaptive.Input.Text.Date</span><span class="sxs-lookup"><span data-stu-id="9a943-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="9a943-125">Input.Number</span><span class="sxs-lookup"><span data-stu-id="9a943-125">Input.Number</span></span> | <span data-ttu-id="9a943-126">Adaptive.Input.Text.Number</span><span class="sxs-lookup"><span data-stu-id="9a943-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="9a943-127">Input.Text</span><span class="sxs-lookup"><span data-stu-id="9a943-127">Input.Text</span></span> | <span data-ttu-id="9a943-128">Adaptive.Input.Text</span><span class="sxs-lookup"><span data-stu-id="9a943-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="9a943-129">Input.Time</span><span class="sxs-lookup"><span data-stu-id="9a943-129">Input.Time</span></span> | <span data-ttu-id="9a943-130">Adaptive.Input.Text.Time</span><span class="sxs-lookup"><span data-stu-id="9a943-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="9a943-131">Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="9a943-131">Input.Toggle</span></span>| <span data-ttu-id="9a943-132">Adaptive.Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="9a943-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="9a943-133">Bild</span><span class="sxs-lookup"><span data-stu-id="9a943-133">Image</span></span>  | <span data-ttu-id="9a943-134">Adaptive.Image</span><span class="sxs-lookup"><span data-stu-id="9a943-134">Adaptive.Image</span></span> |
| <span data-ttu-id="9a943-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="9a943-135">ImageSet</span></span>  | <span data-ttu-id="9a943-136">Adaptive.ImageSet</span><span class="sxs-lookup"><span data-stu-id="9a943-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="9a943-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="9a943-137">FactSet</span></span> | <span data-ttu-id="9a943-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span><span class="sxs-lookup"><span data-stu-id="9a943-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="9a943-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="9a943-139">TextBlock</span></span>  | <span data-ttu-id="9a943-140">Adaptive.TextBlock</span><span class="sxs-lookup"><span data-stu-id="9a943-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="9a943-141">Dieses Beispiel XAML Ressourcenverzeichnis, das den Hintergrund des TextBlocks mit allen auf Hellblau festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9a943-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="9a943-142">Es ist sinnvoll, dass als dieser fortgeschrittene 😁</span><span class="sxs-lookup"><span data-stu-id="9a943-142">You will probably want something more advanced than this 😁</span></span>

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
> <span data-ttu-id="9a943-143">**Ein Hinweis zum serverseitigen imagegenerierung** der WPF-Renderer stellt eine `RenderCardToImageAsync` -Methode, die für die Generierung von serverseitigen Images verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a943-143">**A note about server-side image generation** The WPF renderer provides a `RenderCardToImageAsync` method that can be used for server-side image generation.</span></span> <span data-ttu-id="9a943-144">Sie müssen nur verwenden, die `ResourcesPath` Eigenschaft, wenn in dieser Umgebung verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a943-144">You must only use the `ResourcesPath` property if used in this environment.</span></span> <span data-ttu-id="9a943-145">Finden Sie unter den [Image Rendering](../net-image/getting-started.md) Weitere Dokumentation</span><span class="sxs-lookup"><span data-stu-id="9a943-145">See the [Image Rendering](../net-image/getting-started.md) docs for more</span></span>