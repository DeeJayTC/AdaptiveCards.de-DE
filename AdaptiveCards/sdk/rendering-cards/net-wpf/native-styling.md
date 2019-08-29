---
title: 'Native Formatierung: .net WPF SDK'
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
# <a name="native-styling---net-wpf"></a><span data-ttu-id="df9ea-102">Native Formatierung: .net WPF</span><span class="sxs-lookup"><span data-stu-id="df9ea-102">Native styling - .NET WPF</span></span>

<span data-ttu-id="df9ea-103">Obwohl die Host Konfiguration den größten Teil der einzelnen Plattformen bietet, ist es wahrscheinlich, dass Sie auf jeder Plattform eine native Formatierung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="df9ea-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="df9ea-104">WPF vereinfacht dies, indem es Ihnen ermöglicht wird, ein ResourceDictionary für differenzierte Formatierung, Verhalten, Animationen usw. zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="df9ea-104">WPF makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="df9ea-105">Element</span><span class="sxs-lookup"><span data-stu-id="df9ea-105">Element</span></span> | <span data-ttu-id="df9ea-106">Stilnamen</span><span class="sxs-lookup"><span data-stu-id="df9ea-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="df9ea-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="df9ea-107">AdaptiveCard</span></span> | <span data-ttu-id="df9ea-108">Adaptive.Card</span><span class="sxs-lookup"><span data-stu-id="df9ea-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="df9ea-109">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="df9ea-109">Action.OpenUrl</span></span>  | <span data-ttu-id="df9ea-110">Adaptive.Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="df9ea-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="df9ea-111">Action. showcard</span><span class="sxs-lookup"><span data-stu-id="df9ea-111">Action.ShowCard</span></span> | <span data-ttu-id="df9ea-112">Adaptive.Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="df9ea-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="df9ea-113">Aktion. übermitteln</span><span class="sxs-lookup"><span data-stu-id="df9ea-113">Action.Submit</span></span>  | <span data-ttu-id="df9ea-114">Adaptive.Action.Submit</span><span class="sxs-lookup"><span data-stu-id="df9ea-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="df9ea-115">Spalte</span><span class="sxs-lookup"><span data-stu-id="df9ea-115">Column</span></span> | <span data-ttu-id="df9ea-116">Adaptive. Column, Adaptive. Action. Tap</span><span class="sxs-lookup"><span data-stu-id="df9ea-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="df9ea-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="df9ea-117">ColumnSet</span></span> | <span data-ttu-id="df9ea-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="df9ea-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="df9ea-119">Container</span><span class="sxs-lookup"><span data-stu-id="df9ea-119">Container</span></span> | <span data-ttu-id="df9ea-120">Adaptive. Container</span><span class="sxs-lookup"><span data-stu-id="df9ea-120">Adaptive.Container</span></span>|
| <span data-ttu-id="df9ea-121">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="df9ea-121">Input.ChoiceSet</span></span> | <span data-ttu-id="df9ea-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span><span class="sxs-lookup"><span data-stu-id="df9ea-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="df9ea-123">Input. Date</span><span class="sxs-lookup"><span data-stu-id="df9ea-123">Input.Date</span></span> | <span data-ttu-id="df9ea-124">Adaptive.Input.Text.Date</span><span class="sxs-lookup"><span data-stu-id="df9ea-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="df9ea-125">Eingabe. Zahl</span><span class="sxs-lookup"><span data-stu-id="df9ea-125">Input.Number</span></span> | <span data-ttu-id="df9ea-126">Adaptive.Input.Text.Number</span><span class="sxs-lookup"><span data-stu-id="df9ea-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="df9ea-127">Input.Text</span><span class="sxs-lookup"><span data-stu-id="df9ea-127">Input.Text</span></span> | <span data-ttu-id="df9ea-128">Adaptive. Input. Text</span><span class="sxs-lookup"><span data-stu-id="df9ea-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="df9ea-129">Eingabe. Zeit</span><span class="sxs-lookup"><span data-stu-id="df9ea-129">Input.Time</span></span> | <span data-ttu-id="df9ea-130">Adaptive.Input.Text.Time</span><span class="sxs-lookup"><span data-stu-id="df9ea-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="df9ea-131">Eingabe. Umschalten</span><span class="sxs-lookup"><span data-stu-id="df9ea-131">Input.Toggle</span></span>| <span data-ttu-id="df9ea-132">Adaptive.Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="df9ea-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="df9ea-133">Bild</span><span class="sxs-lookup"><span data-stu-id="df9ea-133">Image</span></span>  | <span data-ttu-id="df9ea-134">Adaptive. Image</span><span class="sxs-lookup"><span data-stu-id="df9ea-134">Adaptive.Image</span></span> |
| <span data-ttu-id="df9ea-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="df9ea-135">ImageSet</span></span>  | <span data-ttu-id="df9ea-136">Adaptive.ImageSet</span><span class="sxs-lookup"><span data-stu-id="df9ea-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="df9ea-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="df9ea-137">FactSet</span></span> | <span data-ttu-id="df9ea-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span><span class="sxs-lookup"><span data-stu-id="df9ea-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="df9ea-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="df9ea-139">TextBlock</span></span>  | <span data-ttu-id="df9ea-140">Adaptive.TextBlock</span><span class="sxs-lookup"><span data-stu-id="df9ea-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="df9ea-141">Dieses Beispiel-XAML-Ressourcen Wörterbuch, das den Hintergrund aller Textblöcke auf Aqua festlegt.</span><span class="sxs-lookup"><span data-stu-id="df9ea-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="df9ea-142">Wahrscheinlich möchten Sie etwas höher als dieses😁</span><span class="sxs-lookup"><span data-stu-id="df9ea-142">You will probably want something more advanced than this 😁</span></span>

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
> <span data-ttu-id="df9ea-143">**Hinweis zur serverseitigen Bildgenerierung** Der WPF-Renderer stellt `RenderCardToImageAsync` eine Methode bereit, die für die serverseitige Bildgenerierung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="df9ea-143">**A note about server-side image generation** The WPF renderer provides a `RenderCardToImageAsync` method that can be used for server-side image generation.</span></span> <span data-ttu-id="df9ea-144">Sie müssen die `ResourcesPath` -Eigenschaft nur verwenden, wenn Sie in dieser Umgebung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="df9ea-144">You must only use the `ResourcesPath` property if used in this environment.</span></span> <span data-ttu-id="df9ea-145">Weitere Informationen finden Sie in den [Bild Rendering](../net-image/getting-started.md) -Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="df9ea-145">See the [Image Rendering](../net-image/getting-started.md) docs for more</span></span>