---
title: 'Native Formatierung: IOS SDK'
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: f9ed839a19ac778381fa36361ad37e95b7ab5e08
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727469"
---
# <a name="native-styling---ios"></a><span data-ttu-id="4a4b4-102">Native Formatierung (IOS)</span><span class="sxs-lookup"><span data-stu-id="4a4b4-102">Native styling - iOS</span></span>

<span data-ttu-id="4a4b4-103">Verwenden Sie XIb für differenzierte Formatierungen.</span><span class="sxs-lookup"><span data-stu-id="4a4b4-103">Use XIB for fine-grained styling.</span></span>

<span data-ttu-id="4a4b4-104">Die folgenden xisb sind vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4a4b4-104">The following XIBs exist</span></span>

| <span data-ttu-id="4a4b4-105">XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-105">XIB</span></span> | <span data-ttu-id="4a4b4-106">Verwendung</span><span class="sxs-lookup"><span data-stu-id="4a4b4-106">Usage</span></span> |
|---|---|
| <span data-ttu-id="4a4b4-107">Acrbutton. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-107">ACRButton.xib</span></span> | <span data-ttu-id="4a4b4-108">Parab</span><span class="sxs-lookup"><span data-stu-id="4a4b4-108">buttons</span></span> |
| <span data-ttu-id="4a4b4-109">Acrcellforcompactmode. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-109">ACRCellForCompactMode.xib</span></span>   | <span data-ttu-id="4a4b4-110">Choiceset Compact-Modus</span><span class="sxs-lookup"><span data-stu-id="4a4b4-110">ChoiceSet compact mode</span></span>|
| <span data-ttu-id="4a4b4-111">Acrdatepicker. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-111">ACRDatePicker.xib</span></span> | <span data-ttu-id="4a4b4-112">DatePicker für Input. Date</span><span class="sxs-lookup"><span data-stu-id="4a4b4-112">DatePicker for Input.Date</span></span> |
| <span data-ttu-id="4a4b4-113">Acrdatetextfield. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-113">ACRDateTextField.xib</span></span>  | <span data-ttu-id="4a4b4-114">TextField für Input. Date</span><span class="sxs-lookup"><span data-stu-id="4a4b4-114">TextField for Input.Date</span></span> |
| <span data-ttu-id="4a4b4-115">Acrinputtableview. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-115">ACRInputTableView.xib</span></span>   | <span data-ttu-id="4a4b4-116">Container für Eingaben</span><span class="sxs-lookup"><span data-stu-id="4a4b4-116">Container for Inputs</span></span> |
| <span data-ttu-id="4a4b4-117">Acrlabelview. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-117">ACRLabelView.xib</span></span>  | <span data-ttu-id="4a4b4-118">TextBlock</span><span class="sxs-lookup"><span data-stu-id="4a4b4-118">TextBlock</span></span> |
| <span data-ttu-id="4a4b4-119">Acrpickerview. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-119">ACRPickerView.xib</span></span> | <span data-ttu-id="4a4b4-120">Choiceset</span><span class="sxs-lookup"><span data-stu-id="4a4b4-120">ChoiceSet</span></span> |
| <span data-ttu-id="4a4b4-121">Acrquickaktionmultilineview. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-121">ACRQuickActionMultilineView.xib</span></span>  | <span data-ttu-id="4a4b4-122">Schnelle Aktionen mit mehreren Zeilen</span><span class="sxs-lookup"><span data-stu-id="4a4b4-122">Quick Actions with multilines</span></span> |
| <span data-ttu-id="4a4b4-123">Acrquickaktionview. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-123">ACRQuickActionView.xib</span></span> | <span data-ttu-id="4a4b4-124">Schnelle Aktionen</span><span class="sxs-lookup"><span data-stu-id="4a4b4-124">Quick Actions</span></span> |
| <span data-ttu-id="4a4b4-125">Acrtextfield. XIb</span><span class="sxs-lookup"><span data-stu-id="4a4b4-125">ACRTextField.xib</span></span> | <span data-ttu-id="4a4b4-126">Eingabe</span><span class="sxs-lookup"><span data-stu-id="4a4b4-126">Input</span></span> |

<span data-ttu-id="4a4b4-127">XIb kann über Xcode IB bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="4a4b4-127">XIB can be edited through XCode IB.</span></span>
<span data-ttu-id="4a4b4-128">Nachdem xisb an der Spezifikation bearbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="4a4b4-128">Once XIBs are edited to the specification.</span></span>
<span data-ttu-id="4a4b4-129">Von einem Terminal</span><span class="sxs-lookup"><span data-stu-id="4a4b4-129">From a terminal</span></span>
```
ibtool --compile name.nib name.xib 
```

<span data-ttu-id="4a4b4-130">So formatieren Sie z. b. eine Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="4a4b4-130">For example, to style a button</span></span>
```
ibtool --compile ACRButton.nib ACRButton.xib 
```

<span data-ttu-id="4a4b4-131">Die generierten nib-Dateien können dann in adaptivecards. Framework ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="4a4b4-131">The generated nib files can be then replaced at AdaptiveCards.framework</span></span>
