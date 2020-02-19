---
title: 'Native Formatierung: UWP SDK'
author: matthidinger
ms.author: mahiding
ms.date: 08/15/2018
ms.topic: article
ms.openlocfilehash: 565c61535adc5b316cb8b1f3ad77e511012e7612
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454043"
---
# <a name="native-styling---uwp"></a><span data-ttu-id="db74b-102">Native Formatierung-UWP</span><span class="sxs-lookup"><span data-stu-id="db74b-102">Native styling - UWP</span></span>

<span data-ttu-id="db74b-103">Obwohl die Host Konfiguration den größten Teil der einzelnen Plattformen bietet, ist es wahrscheinlich, dass Sie auf jeder Plattform eine native Formatierung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="db74b-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="db74b-104">UWP vereinfacht dies, indem es Ihnen ermöglicht wird, ein ResourceDictionary für differenzierte Formatierung, Verhalten, Animationen usw. zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="db74b-104">UWP makes this easy by allowing you to pass a ResourceDictionary for fine-grained styling, behavior, animations, etc.</span></span>

| <span data-ttu-id="db74b-105">Element</span><span class="sxs-lookup"><span data-stu-id="db74b-105">Element</span></span> | <span data-ttu-id="db74b-106">Stilnamen</span><span class="sxs-lookup"><span data-stu-id="db74b-106">Style names</span></span> |
|---|---|
| <span data-ttu-id="db74b-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="db74b-107">AdaptiveCard</span></span> | <span data-ttu-id="db74b-108">Adaptive.Card</span><span class="sxs-lookup"><span data-stu-id="db74b-108">Adaptive.Card</span></span>| 
| <span data-ttu-id="db74b-109">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="db74b-109">Action.OpenUrl</span></span>  | <span data-ttu-id="db74b-110">Adaptive.Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="db74b-110">Adaptive.Action.OpenUrl</span></span>  |
| <span data-ttu-id="db74b-111">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="db74b-111">Action.ShowCard</span></span> | <span data-ttu-id="db74b-112">Adaptive.Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="db74b-112">Adaptive.Action.ShowCard</span></span> |
| <span data-ttu-id="db74b-113">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="db74b-113">Action.Submit</span></span>  | <span data-ttu-id="db74b-114">Adaptive.Action.Submit</span><span class="sxs-lookup"><span data-stu-id="db74b-114">Adaptive.Action.Submit</span></span>  |
| <span data-ttu-id="db74b-115">Spalte</span><span class="sxs-lookup"><span data-stu-id="db74b-115">Column</span></span> | <span data-ttu-id="db74b-116">Adaptive. Column, Adaptive. Action. Tap</span><span class="sxs-lookup"><span data-stu-id="db74b-116">Adaptive.Column, Adaptive.Action.Tap</span></span> |
| <span data-ttu-id="db74b-117">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="db74b-117">ColumnSet</span></span> | <span data-ttu-id="db74b-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span><span class="sxs-lookup"><span data-stu-id="db74b-118">Adaptive.ColumnSet, Adaptive.VerticalSeparator</span></span> |
| <span data-ttu-id="db74b-119">Container</span><span class="sxs-lookup"><span data-stu-id="db74b-119">Container</span></span> | <span data-ttu-id="db74b-120">Adaptive. Container</span><span class="sxs-lookup"><span data-stu-id="db74b-120">Adaptive.Container</span></span>|
| <span data-ttu-id="db74b-121">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="db74b-121">Input.ChoiceSet</span></span> | <span data-ttu-id="db74b-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span><span class="sxs-lookup"><span data-stu-id="db74b-122">Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem</span></span> |
| <span data-ttu-id="db74b-123">Input. Date</span><span class="sxs-lookup"><span data-stu-id="db74b-123">Input.Date</span></span> | <span data-ttu-id="db74b-124">Adaptive.Input.Text.Date</span><span class="sxs-lookup"><span data-stu-id="db74b-124">Adaptive.Input.Text.Date</span></span>
| <span data-ttu-id="db74b-125">Eingabe. Zahl</span><span class="sxs-lookup"><span data-stu-id="db74b-125">Input.Number</span></span> | <span data-ttu-id="db74b-126">Adaptive.Input.Text.Number</span><span class="sxs-lookup"><span data-stu-id="db74b-126">Adaptive.Input.Text.Number</span></span> |
| <span data-ttu-id="db74b-127">Input.Text</span><span class="sxs-lookup"><span data-stu-id="db74b-127">Input.Text</span></span> | <span data-ttu-id="db74b-128">Adaptive. Input. Text</span><span class="sxs-lookup"><span data-stu-id="db74b-128">Adaptive.Input.Text</span></span> |
| <span data-ttu-id="db74b-129">Eingabe. Zeit</span><span class="sxs-lookup"><span data-stu-id="db74b-129">Input.Time</span></span> | <span data-ttu-id="db74b-130">Adaptive.Input.Text.Time</span><span class="sxs-lookup"><span data-stu-id="db74b-130">Adaptive.Input.Text.Time</span></span> |
| <span data-ttu-id="db74b-131">Eingabe. Umschalten</span><span class="sxs-lookup"><span data-stu-id="db74b-131">Input.Toggle</span></span>| <span data-ttu-id="db74b-132">Adaptive.Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="db74b-132">Adaptive.Input.Toggle</span></span>|
| <span data-ttu-id="db74b-133">Bild</span><span class="sxs-lookup"><span data-stu-id="db74b-133">Image</span></span>  | <span data-ttu-id="db74b-134">Adaptive. Image</span><span class="sxs-lookup"><span data-stu-id="db74b-134">Adaptive.Image</span></span> |
| <span data-ttu-id="db74b-135">ImageSet</span><span class="sxs-lookup"><span data-stu-id="db74b-135">ImageSet</span></span>  | <span data-ttu-id="db74b-136">Adaptive.ImageSet</span><span class="sxs-lookup"><span data-stu-id="db74b-136">Adaptive.ImageSet</span></span> |
| <span data-ttu-id="db74b-137">FactSet</span><span class="sxs-lookup"><span data-stu-id="db74b-137">FactSet</span></span> | <span data-ttu-id="db74b-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span><span class="sxs-lookup"><span data-stu-id="db74b-138">Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value</span></span> |
| <span data-ttu-id="db74b-139">TextBlock</span><span class="sxs-lookup"><span data-stu-id="db74b-139">TextBlock</span></span>  | <span data-ttu-id="db74b-140">Adaptive.TextBlock</span><span class="sxs-lookup"><span data-stu-id="db74b-140">Adaptive.TextBlock</span></span> |

<span data-ttu-id="db74b-141">Dieses Beispiel-XAML-Ressourcen Wörterbuch, das den Hintergrund aller Textblöcke auf Aqua festlegt.</span><span class="sxs-lookup"><span data-stu-id="db74b-141">This sample XAML Resource dictionary that sets the background of all TextBlocks to Aqua.</span></span> <span data-ttu-id="db74b-142">Wahrscheinlich möchten Sie etwas höher als dieses 😁</span><span class="sxs-lookup"><span data-stu-id="db74b-142">You will probably want something more advanced than this 😁</span></span>

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
```
