---
title: 'Native Formatierung: .net html SDK'
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 620940dee873742898d58979c61827320bc3c202
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552562"
---
# <a name="native-styling---net-html"></a><span data-ttu-id="26d33-102">Native Formatierung: .net-html</span><span class="sxs-lookup"><span data-stu-id="26d33-102">Native styling - .NET HTML</span></span>

<span data-ttu-id="26d33-103">Obwohl die Host Konfiguration den größten Teil der einzelnen Plattformen bietet, ist es wahrscheinlich, dass Sie auf jeder Plattform eine native Formatierung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="26d33-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="26d33-104">Durch HTML werden jedem Element CSS-Klassen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="26d33-104">HTML makes this easy by adding CSS classes to every element.</span></span>

| <span data-ttu-id="26d33-105">Element</span><span class="sxs-lookup"><span data-stu-id="26d33-105">Element</span></span> | <span data-ttu-id="26d33-106">CSS-Klasse</span><span class="sxs-lookup"><span data-stu-id="26d33-106">CSS class</span></span> |
|---|---|
| <span data-ttu-id="26d33-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="26d33-107">AdaptiveCard</span></span> | <span data-ttu-id="26d33-108">AC-adaptivecard</span><span class="sxs-lookup"><span data-stu-id="26d33-108">ac-adaptivecard</span></span> |
| <span data-ttu-id="26d33-109">Alle Aktionen</span><span class="sxs-lookup"><span data-stu-id="26d33-109">All Actions</span></span> | <span data-ttu-id="26d33-110">AC-PUSHBUTTON</span><span class="sxs-lookup"><span data-stu-id="26d33-110">ac-pushButton</span></span> | 
| <span data-ttu-id="26d33-111">Aktionen auswählen</span><span class="sxs-lookup"><span data-stu-id="26d33-111">Select Actions</span></span> | <span data-ttu-id="26d33-112">AC-auswählbar</span><span class="sxs-lookup"><span data-stu-id="26d33-112">ac-selectable</span></span> |
| <span data-ttu-id="26d33-113">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="26d33-113">Action.OpenUrl</span></span>  | <span data-ttu-id="26d33-114">ac-action-openUrl</span><span class="sxs-lookup"><span data-stu-id="26d33-114">ac-action-openUrl</span></span> |
| <span data-ttu-id="26d33-115">Action. showcard</span><span class="sxs-lookup"><span data-stu-id="26d33-115">Action.ShowCard</span></span> | <span data-ttu-id="26d33-116">ac-action-showCard</span><span class="sxs-lookup"><span data-stu-id="26d33-116">ac-action-showCard</span></span> |
| <span data-ttu-id="26d33-117">Aktion. übermitteln</span><span class="sxs-lookup"><span data-stu-id="26d33-117">Action.Submit</span></span>  | <span data-ttu-id="26d33-118">AC-Action-Submit</span><span class="sxs-lookup"><span data-stu-id="26d33-118">ac-action-submit</span></span>  |
| <span data-ttu-id="26d33-119">Aktions Satz</span><span class="sxs-lookup"><span data-stu-id="26d33-119">ActionSet</span></span> | <span data-ttu-id="26d33-120">AC-Aktions Satz</span><span class="sxs-lookup"><span data-stu-id="26d33-120">ac-actionset</span></span> |
| <span data-ttu-id="26d33-121">Spalte</span><span class="sxs-lookup"><span data-stu-id="26d33-121">Column</span></span> | <span data-ttu-id="26d33-122">AC-Column</span><span class="sxs-lookup"><span data-stu-id="26d33-122">ac-column</span></span> |
| <span data-ttu-id="26d33-123">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="26d33-123">ColumnSet</span></span> | <span data-ttu-id="26d33-124">AC-ColumnSet</span><span class="sxs-lookup"><span data-stu-id="26d33-124">ac-columnset</span></span> |
| <span data-ttu-id="26d33-125">Container</span><span class="sxs-lookup"><span data-stu-id="26d33-125">Container</span></span> | <span data-ttu-id="26d33-126">AC-Container</span><span class="sxs-lookup"><span data-stu-id="26d33-126">ac-container</span></span> |
| <span data-ttu-id="26d33-127">Alle Eingaben</span><span class="sxs-lookup"><span data-stu-id="26d33-127">All Inputs</span></span> | <span data-ttu-id="26d33-128">AC-Eingabe</span><span class="sxs-lookup"><span data-stu-id="26d33-128">ac-input</span></span> |
| <span data-ttu-id="26d33-129">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="26d33-129">Input.ChoiceSet</span></span> | <span data-ttu-id="26d33-130">ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="26d33-130">ac-multichoiceInput</span></span>  |
| <span data-ttu-id="26d33-131">Input. Date</span><span class="sxs-lookup"><span data-stu-id="26d33-131">Input.Date</span></span> | <span data-ttu-id="26d33-132">AC-dateinput</span><span class="sxs-lookup"><span data-stu-id="26d33-132">ac-dateInput</span></span> |
| <span data-ttu-id="26d33-133">Eingabe. Zahl</span><span class="sxs-lookup"><span data-stu-id="26d33-133">Input.Number</span></span> | <span data-ttu-id="26d33-134">ac-numberInput</span><span class="sxs-lookup"><span data-stu-id="26d33-134">ac-numberInput</span></span> |
| <span data-ttu-id="26d33-135">Input.Text</span><span class="sxs-lookup"><span data-stu-id="26d33-135">Input.Text</span></span> | <span data-ttu-id="26d33-136">AC-TextInput</span><span class="sxs-lookup"><span data-stu-id="26d33-136">ac-textInput</span></span> |
| <span data-ttu-id="26d33-137">Eingabe. Zeit</span><span class="sxs-lookup"><span data-stu-id="26d33-137">Input.Time</span></span> | <span data-ttu-id="26d33-138">AC-timeinput</span><span class="sxs-lookup"><span data-stu-id="26d33-138">ac-timeInput</span></span> |
| <span data-ttu-id="26d33-139">Eingabe. Umschalten</span><span class="sxs-lookup"><span data-stu-id="26d33-139">Input.Toggle</span></span>| - |
| <span data-ttu-id="26d33-140">Bild</span><span class="sxs-lookup"><span data-stu-id="26d33-140">Image</span></span>  | <span data-ttu-id="26d33-141">AC-Image</span><span class="sxs-lookup"><span data-stu-id="26d33-141">ac-image</span></span> |
| <span data-ttu-id="26d33-142">ImageSet</span><span class="sxs-lookup"><span data-stu-id="26d33-142">ImageSet</span></span>  | <span data-ttu-id="26d33-143">AC-ImageSet</span><span class="sxs-lookup"><span data-stu-id="26d33-143">ac-imageset</span></span> |
| <span data-ttu-id="26d33-144">FactSet</span><span class="sxs-lookup"><span data-stu-id="26d33-144">FactSet</span></span> | <span data-ttu-id="26d33-145">AC-FactSet</span><span class="sxs-lookup"><span data-stu-id="26d33-145">ac-factset</span></span> |
| <span data-ttu-id="26d33-146">TextBlock</span><span class="sxs-lookup"><span data-stu-id="26d33-146">TextBlock</span></span>  | <span data-ttu-id="26d33-147">AC-TextBlock</span><span class="sxs-lookup"><span data-stu-id="26d33-147">ac-textblock</span></span> |