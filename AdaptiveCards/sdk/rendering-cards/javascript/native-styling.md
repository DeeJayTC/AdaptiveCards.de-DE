---
title: Native Stil - JavaScript-SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 6f086d268abcaeb7fa159b74708597e89aafaf53
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552892"
---
# <a name="native-styling---javascript"></a><span data-ttu-id="438f7-102">Native erstellen – JavaScript</span><span class="sxs-lookup"><span data-stu-id="438f7-102">Native styling - JavaScript</span></span>

<span data-ttu-id="438f7-103">Mithilfe von CSS für die eine differenzierte Formatierung der HTML-Karte.</span><span class="sxs-lookup"><span data-stu-id="438f7-103">Use CSS for fine-grained styling of the card HTML.</span></span>

<span data-ttu-id="438f7-104">Die folgenden CSS-Klassen werden verschiedene Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="438f7-104">The following CSS classes will be added to various elements.</span></span>

| <span data-ttu-id="438f7-105">CSS-Klasse</span><span class="sxs-lookup"><span data-stu-id="438f7-105">CSS class</span></span> | <span data-ttu-id="438f7-106">Verwendung</span><span class="sxs-lookup"><span data-stu-id="438f7-106">Usage</span></span> |
|---|---|
| <span data-ttu-id="438f7-107">.ac-container</span><span class="sxs-lookup"><span data-stu-id="438f7-107">.ac-container</span></span> | <span data-ttu-id="438f7-108">Container</span><span class="sxs-lookup"><span data-stu-id="438f7-108">containers</span></span> |
| <span data-ttu-id="438f7-109">.ac-selectable</span><span class="sxs-lookup"><span data-stu-id="438f7-109">.ac-selectable</span></span>  | <span data-ttu-id="438f7-110">Elemente mit `selectAction`</span><span class="sxs-lookup"><span data-stu-id="438f7-110">elements with `selectAction`</span></span> |
| <span data-ttu-id="438f7-111">.AC-image</span><span class="sxs-lookup"><span data-stu-id="438f7-111">.ac-image</span></span> | <span data-ttu-id="438f7-112">image</span><span class="sxs-lookup"><span data-stu-id="438f7-112">image</span></span> |
| <span data-ttu-id="438f7-113">.ac-pushButton</span><span class="sxs-lookup"><span data-stu-id="438f7-113">.ac-pushButton</span></span> | <span data-ttu-id="438f7-114">Aktionen, die gerendert wird, wie Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="438f7-114">actions rendered like buttons</span></span> |
| <span data-ttu-id="438f7-115">.ac-linkButton</span><span class="sxs-lookup"><span data-stu-id="438f7-115">.ac-linkButton</span></span>  | <span data-ttu-id="438f7-116">Aktionen, die gerendert wird, wie links</span><span class="sxs-lookup"><span data-stu-id="438f7-116">actions rendered like links</span></span> |
| <span data-ttu-id="438f7-117">.AC-Eingabe</span><span class="sxs-lookup"><span data-stu-id="438f7-117">.ac-input</span></span> | <span data-ttu-id="438f7-118">Benutzereingabe-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="438f7-118">input controls</span></span>|
| <span data-ttu-id="438f7-119">.AC-textInput</span><span class="sxs-lookup"><span data-stu-id="438f7-119">.ac-textInput</span></span>| <span data-ttu-id="438f7-120">Texteingabe</span><span class="sxs-lookup"><span data-stu-id="438f7-120">text input</span></span> |
| <span data-ttu-id="438f7-121">.AC mehrzeiligen</span><span class="sxs-lookup"><span data-stu-id="438f7-121">.ac-multiline</span></span> | <span data-ttu-id="438f7-122">Mehrzeilige Texteingabe</span><span class="sxs-lookup"><span data-stu-id="438f7-122">multiline text input</span></span> |
| <span data-ttu-id="438f7-123">.ac-numberInput</span><span class="sxs-lookup"><span data-stu-id="438f7-123">.ac-numberInput</span></span> | <span data-ttu-id="438f7-124">eingegebene Wert</span><span class="sxs-lookup"><span data-stu-id="438f7-124">number input</span></span>|
| <span data-ttu-id="438f7-125">.ac-dateInput</span><span class="sxs-lookup"><span data-stu-id="438f7-125">.ac-dateInput</span></span> | <span data-ttu-id="438f7-126">die Datumseingabe</span><span class="sxs-lookup"><span data-stu-id="438f7-126">date input</span></span>|
| <span data-ttu-id="438f7-127">.ac-timeInput</span><span class="sxs-lookup"><span data-stu-id="438f7-127">.ac-timeInput</span></span> | <span data-ttu-id="438f7-128">Time-Eingabe</span><span class="sxs-lookup"><span data-stu-id="438f7-128">time input</span></span> |
| <span data-ttu-id="438f7-129">.ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="438f7-129">.ac-multichoiceInput</span></span> | <span data-ttu-id="438f7-130">Auswahlfelder Eingabe</span><span class="sxs-lookup"><span data-stu-id="438f7-130">multichoice input</span></span>|