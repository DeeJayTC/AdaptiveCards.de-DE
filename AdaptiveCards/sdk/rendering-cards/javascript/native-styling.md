---
title: 'Native Formatierung: JavaScript SDK'
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
# <a name="native-styling---javascript"></a><span data-ttu-id="c08e6-102">Native Formatierung: JavaScript</span><span class="sxs-lookup"><span data-stu-id="c08e6-102">Native styling - JavaScript</span></span>

<span data-ttu-id="c08e6-103">Verwenden Sie CSS für eine differenzierte Formatierung des Karten-HTML.</span><span class="sxs-lookup"><span data-stu-id="c08e6-103">Use CSS for fine-grained styling of the card HTML.</span></span>

<span data-ttu-id="c08e6-104">Die folgenden CSS-Klassen werden verschiedenen Elementen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c08e6-104">The following CSS classes will be added to various elements.</span></span>

| <span data-ttu-id="c08e6-105">CSS-Klasse</span><span class="sxs-lookup"><span data-stu-id="c08e6-105">CSS class</span></span> | <span data-ttu-id="c08e6-106">Verwendung</span><span class="sxs-lookup"><span data-stu-id="c08e6-106">Usage</span></span> |
|---|---|
| <span data-ttu-id="c08e6-107">. AC-Container</span><span class="sxs-lookup"><span data-stu-id="c08e6-107">.ac-container</span></span> | <span data-ttu-id="c08e6-108">Schütt</span><span class="sxs-lookup"><span data-stu-id="c08e6-108">containers</span></span> |
| <span data-ttu-id="c08e6-109">. AC-auswählbar</span><span class="sxs-lookup"><span data-stu-id="c08e6-109">.ac-selectable</span></span>  | <span data-ttu-id="c08e6-110">Elemente mit`selectAction`</span><span class="sxs-lookup"><span data-stu-id="c08e6-110">elements with `selectAction`</span></span> |
| <span data-ttu-id="c08e6-111">. AC-Image</span><span class="sxs-lookup"><span data-stu-id="c08e6-111">.ac-image</span></span> | <span data-ttu-id="c08e6-112">image</span><span class="sxs-lookup"><span data-stu-id="c08e6-112">image</span></span> |
| <span data-ttu-id="c08e6-113">. AC-PUSHBUTTON</span><span class="sxs-lookup"><span data-stu-id="c08e6-113">.ac-pushButton</span></span> | <span data-ttu-id="c08e6-114">Aktionen gerendert wie Schaltflächen</span><span class="sxs-lookup"><span data-stu-id="c08e6-114">actions rendered like buttons</span></span> |
| <span data-ttu-id="c08e6-115">. AC-LinkButton</span><span class="sxs-lookup"><span data-stu-id="c08e6-115">.ac-linkButton</span></span>  | <span data-ttu-id="c08e6-116">Aktionen gerendert wie Links</span><span class="sxs-lookup"><span data-stu-id="c08e6-116">actions rendered like links</span></span> |
| <span data-ttu-id="c08e6-117">. AC-Eingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-117">.ac-input</span></span> | <span data-ttu-id="c08e6-118">Eingabe Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c08e6-118">input controls</span></span>|
| <span data-ttu-id="c08e6-119">. AC-TextInput</span><span class="sxs-lookup"><span data-stu-id="c08e6-119">.ac-textInput</span></span>| <span data-ttu-id="c08e6-120">Texteingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-120">text input</span></span> |
| <span data-ttu-id="c08e6-121">. AC-Multiline</span><span class="sxs-lookup"><span data-stu-id="c08e6-121">.ac-multiline</span></span> | <span data-ttu-id="c08e6-122">mehrzeilige Texteingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-122">multiline text input</span></span> |
| <span data-ttu-id="c08e6-123">. AC-anzahleingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-123">.ac-numberInput</span></span> | <span data-ttu-id="c08e6-124">Zahlen Eingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-124">number input</span></span>|
| <span data-ttu-id="c08e6-125">. AC-dateinput</span><span class="sxs-lookup"><span data-stu-id="c08e6-125">.ac-dateInput</span></span> | <span data-ttu-id="c08e6-126">Datums Eingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-126">date input</span></span>|
| <span data-ttu-id="c08e6-127">. AC-timeinput</span><span class="sxs-lookup"><span data-stu-id="c08e6-127">.ac-timeInput</span></span> | <span data-ttu-id="c08e6-128">Uhrzeit Eingabe</span><span class="sxs-lookup"><span data-stu-id="c08e6-128">time input</span></span> |
| <span data-ttu-id="c08e6-129">.ac-multichoiceInput</span><span class="sxs-lookup"><span data-stu-id="c08e6-129">.ac-multichoiceInput</span></span> | <span data-ttu-id="c08e6-130">Eingabe für mehr Wahl</span><span class="sxs-lookup"><span data-stu-id="c08e6-130">multichoice input</span></span>|