---
title: 'Native Formatierung: JavaScript SDK'
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 687a90dd572ba2df786816fdd9dc313746cca982
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454643"
---
# <a name="native-styling---javascript"></a><span data-ttu-id="7f17d-102">Native Formatierung: JavaScript</span><span class="sxs-lookup"><span data-stu-id="7f17d-102">Native styling - JavaScript</span></span>

<span data-ttu-id="7f17d-103">Verwenden Sie CSS für eine differenzierte Formatierung des Karten-HTML.</span><span class="sxs-lookup"><span data-stu-id="7f17d-103">Use CSS for fine-grained styling of the card HTML.</span></span>

<span data-ttu-id="7f17d-104">Die folgenden CSS-Klassen werden verschiedenen Elementen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7f17d-104">The following CSS classes will be added to various elements.</span></span>

| <span data-ttu-id="7f17d-105">CSS-Klasse</span><span class="sxs-lookup"><span data-stu-id="7f17d-105">CSS class</span></span> | <span data-ttu-id="7f17d-106">Verwendung</span><span class="sxs-lookup"><span data-stu-id="7f17d-106">Usage</span></span> |
|---|---|
| <span data-ttu-id="7f17d-107">. AC-Container</span><span class="sxs-lookup"><span data-stu-id="7f17d-107">.ac-container</span></span> | <span data-ttu-id="7f17d-108">Container</span><span class="sxs-lookup"><span data-stu-id="7f17d-108">containers</span></span> |
| <span data-ttu-id="7f17d-109">. AC-auswählbar</span><span class="sxs-lookup"><span data-stu-id="7f17d-109">.ac-selectable</span></span>  | <span data-ttu-id="7f17d-110">Elemente mit `selectAction`</span><span class="sxs-lookup"><span data-stu-id="7f17d-110">elements with `selectAction`</span></span> |
| <span data-ttu-id="7f17d-111">. AC-Image</span><span class="sxs-lookup"><span data-stu-id="7f17d-111">.ac-image</span></span> | <span data-ttu-id="7f17d-112">image</span><span class="sxs-lookup"><span data-stu-id="7f17d-112">image</span></span> |
| <span data-ttu-id="7f17d-113">. AC-PUSHBUTTON</span><span class="sxs-lookup"><span data-stu-id="7f17d-113">.ac-pushButton</span></span> | <span data-ttu-id="7f17d-114">Aktionen gerendert wie Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="7f17d-114">actions rendered like buttons</span></span> |
| <span data-ttu-id="7f17d-115">. AC-LinkButton</span><span class="sxs-lookup"><span data-stu-id="7f17d-115">.ac-linkButton</span></span>  | <span data-ttu-id="7f17d-116">Aktionen gerendert wie Links</span><span class="sxs-lookup"><span data-stu-id="7f17d-116">actions rendered like links</span></span> |
| <span data-ttu-id="7f17d-117">. AC-Eingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-117">.ac-input</span></span> | <span data-ttu-id="7f17d-118">Eingabesteuerelemente</span><span class="sxs-lookup"><span data-stu-id="7f17d-118">input controls</span></span>|
| <span data-ttu-id="7f17d-119">. AC-TextInput</span><span class="sxs-lookup"><span data-stu-id="7f17d-119">.ac-textInput</span></span>| <span data-ttu-id="7f17d-120">Texteingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-120">text input</span></span> |
| <span data-ttu-id="7f17d-121">. AC-Multiline</span><span class="sxs-lookup"><span data-stu-id="7f17d-121">.ac-multiline</span></span> | <span data-ttu-id="7f17d-122">mehrzeilige Texteingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-122">multiline text input</span></span> |
| <span data-ttu-id="7f17d-123">. AC-anzahleingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-123">.ac-numberInput</span></span> | <span data-ttu-id="7f17d-124">Zahlen Eingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-124">number input</span></span>|
| <span data-ttu-id="7f17d-125">. AC-dateinput</span><span class="sxs-lookup"><span data-stu-id="7f17d-125">.ac-dateInput</span></span> | <span data-ttu-id="7f17d-126">Datums Eingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-126">date input</span></span>|
| <span data-ttu-id="7f17d-127">. AC-timeinput</span><span class="sxs-lookup"><span data-stu-id="7f17d-127">.ac-timeInput</span></span> | <span data-ttu-id="7f17d-128">Uhrzeit Eingabe</span><span class="sxs-lookup"><span data-stu-id="7f17d-128">time input</span></span> |
| <span data-ttu-id="7f17d-129">.ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="7f17d-129">.ac-multichoiceInput</span></span> | <span data-ttu-id="7f17d-130">Eingabe für mehr Wahl</span><span class="sxs-lookup"><span data-stu-id="7f17d-130">multichoice input</span></span>|