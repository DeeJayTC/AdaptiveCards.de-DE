---
title: Native Stil - HTML-SDK für .NET
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
# <a name="native-styling---net-html"></a><span data-ttu-id="ef68d-102">Native Stil - HTML für .NET</span><span class="sxs-lookup"><span data-stu-id="ef68d-102">Native styling - .NET HTML</span></span>

<span data-ttu-id="ef68d-103">Während der Host-Konfiguration die meisten haben, erhalten Sie die Art und Weise gibt es auf jeder Plattform, ist es wahrscheinlich, dass Sie einige native Formatierungen auf jeder Plattform zu tun hat.</span><span class="sxs-lookup"><span data-stu-id="ef68d-103">While Host Config will get you most of the way there on each platform, it's likely that you will have to do some native styling on each platform.</span></span> 

<span data-ttu-id="ef68d-104">HTML erleichtert dies, indem Sie jedes Element CSS-Klassen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ef68d-104">HTML makes this easy by adding CSS classes to every element.</span></span>

| <span data-ttu-id="ef68d-105">Element</span><span class="sxs-lookup"><span data-stu-id="ef68d-105">Element</span></span> | <span data-ttu-id="ef68d-106">CSS-Klasse</span><span class="sxs-lookup"><span data-stu-id="ef68d-106">CSS class</span></span> |
|---|---|
| <span data-ttu-id="ef68d-107">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="ef68d-107">AdaptiveCard</span></span> | <span data-ttu-id="ef68d-108">ac-adaptivecard</span><span class="sxs-lookup"><span data-stu-id="ef68d-108">ac-adaptivecard</span></span> |
| <span data-ttu-id="ef68d-109">Alle Aktionen</span><span class="sxs-lookup"><span data-stu-id="ef68d-109">All Actions</span></span> | <span data-ttu-id="ef68d-110">ac-pushButton</span><span class="sxs-lookup"><span data-stu-id="ef68d-110">ac-pushButton</span></span> | 
| <span data-ttu-id="ef68d-111">Wählen Sie Aktionen</span><span class="sxs-lookup"><span data-stu-id="ef68d-111">Select Actions</span></span> | <span data-ttu-id="ef68d-112">ac-selectable</span><span class="sxs-lookup"><span data-stu-id="ef68d-112">ac-selectable</span></span> |
| <span data-ttu-id="ef68d-113">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="ef68d-113">Action.OpenUrl</span></span>  | <span data-ttu-id="ef68d-114">ac-action-openUrl</span><span class="sxs-lookup"><span data-stu-id="ef68d-114">ac-action-openUrl</span></span> |
| <span data-ttu-id="ef68d-115">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="ef68d-115">Action.ShowCard</span></span> | <span data-ttu-id="ef68d-116">ac-action-showCard</span><span class="sxs-lookup"><span data-stu-id="ef68d-116">ac-action-showCard</span></span> |
| <span data-ttu-id="ef68d-117">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="ef68d-117">Action.Submit</span></span>  | <span data-ttu-id="ef68d-118">ac-action-submit</span><span class="sxs-lookup"><span data-stu-id="ef68d-118">ac-action-submit</span></span>  |
| <span data-ttu-id="ef68d-119">ActionSet</span><span class="sxs-lookup"><span data-stu-id="ef68d-119">ActionSet</span></span> | <span data-ttu-id="ef68d-120">ac-actionset</span><span class="sxs-lookup"><span data-stu-id="ef68d-120">ac-actionset</span></span> |
| <span data-ttu-id="ef68d-121">Column</span><span class="sxs-lookup"><span data-stu-id="ef68d-121">Column</span></span> | <span data-ttu-id="ef68d-122">AC-Spalte</span><span class="sxs-lookup"><span data-stu-id="ef68d-122">ac-column</span></span> |
| <span data-ttu-id="ef68d-123">ColumnSet</span><span class="sxs-lookup"><span data-stu-id="ef68d-123">ColumnSet</span></span> | <span data-ttu-id="ef68d-124">ac-columnset</span><span class="sxs-lookup"><span data-stu-id="ef68d-124">ac-columnset</span></span> |
| <span data-ttu-id="ef68d-125">Container</span><span class="sxs-lookup"><span data-stu-id="ef68d-125">Container</span></span> | <span data-ttu-id="ef68d-126">ac-container</span><span class="sxs-lookup"><span data-stu-id="ef68d-126">ac-container</span></span> |
| <span data-ttu-id="ef68d-127">Alle Eingaben</span><span class="sxs-lookup"><span data-stu-id="ef68d-127">All Inputs</span></span> | <span data-ttu-id="ef68d-128">AC-Eingabe</span><span class="sxs-lookup"><span data-stu-id="ef68d-128">ac-input</span></span> |
| <span data-ttu-id="ef68d-129">Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="ef68d-129">Input.ChoiceSet</span></span> | <span data-ttu-id="ef68d-130">ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="ef68d-130">ac-multichoiceInput</span></span>  |
| <span data-ttu-id="ef68d-131">Input.Date</span><span class="sxs-lookup"><span data-stu-id="ef68d-131">Input.Date</span></span> | <span data-ttu-id="ef68d-132">ac-dateInput</span><span class="sxs-lookup"><span data-stu-id="ef68d-132">ac-dateInput</span></span> |
| <span data-ttu-id="ef68d-133">Input.Number</span><span class="sxs-lookup"><span data-stu-id="ef68d-133">Input.Number</span></span> | <span data-ttu-id="ef68d-134">ac-numberInput</span><span class="sxs-lookup"><span data-stu-id="ef68d-134">ac-numberInput</span></span> |
| <span data-ttu-id="ef68d-135">Input.Text</span><span class="sxs-lookup"><span data-stu-id="ef68d-135">Input.Text</span></span> | <span data-ttu-id="ef68d-136">ac-textInput</span><span class="sxs-lookup"><span data-stu-id="ef68d-136">ac-textInput</span></span> |
| <span data-ttu-id="ef68d-137">Input.Time</span><span class="sxs-lookup"><span data-stu-id="ef68d-137">Input.Time</span></span> | <span data-ttu-id="ef68d-138">ac-timeInput</span><span class="sxs-lookup"><span data-stu-id="ef68d-138">ac-timeInput</span></span> |
| <span data-ttu-id="ef68d-139">Input.Toggle</span><span class="sxs-lookup"><span data-stu-id="ef68d-139">Input.Toggle</span></span>| - |
| <span data-ttu-id="ef68d-140">Bild</span><span class="sxs-lookup"><span data-stu-id="ef68d-140">Image</span></span>  | <span data-ttu-id="ef68d-141">AC-image</span><span class="sxs-lookup"><span data-stu-id="ef68d-141">ac-image</span></span> |
| <span data-ttu-id="ef68d-142">ImageSet</span><span class="sxs-lookup"><span data-stu-id="ef68d-142">ImageSet</span></span>  | <span data-ttu-id="ef68d-143">ac-imageset</span><span class="sxs-lookup"><span data-stu-id="ef68d-143">ac-imageset</span></span> |
| <span data-ttu-id="ef68d-144">FactSet</span><span class="sxs-lookup"><span data-stu-id="ef68d-144">FactSet</span></span> | <span data-ttu-id="ef68d-145">ac-factset</span><span class="sxs-lookup"><span data-stu-id="ef68d-145">ac-factset</span></span> |
| <span data-ttu-id="ef68d-146">TextBlock</span><span class="sxs-lookup"><span data-stu-id="ef68d-146">TextBlock</span></span>  | <span data-ttu-id="ef68d-147">AC-TextBlock-Element</span><span class="sxs-lookup"><span data-stu-id="ef68d-147">ac-textblock</span></span> |