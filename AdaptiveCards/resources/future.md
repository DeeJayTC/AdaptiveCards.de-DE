---
title: Roadmap für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: f879c164b3471347ba8fa058827b3d79b09be4cd
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138003"
---
# <a name="future-work"></a><span data-ttu-id="db509-102">Die Zukunft</span><span class="sxs-lookup"><span data-stu-id="db509-102">Future work</span></span>

<span data-ttu-id="db509-103">Wir haben zwar bereits großartige Fortschritte beim Definieren von adaptiven Karten erzielt, aber es ist immer noch sehr viel zu tun.</span><span class="sxs-lookup"><span data-stu-id="db509-103">While we have made excellent progress defining adaptive cards, there is still lots of work to do.</span></span> <span data-ttu-id="db509-104">Wir hoffen, dass wir durch die Unterstützung aktiver Entwicklercommunitys wie Botness und toller Partner wie Slack und Kik ein herausragendes Ökosystem aus plattformübergreifenden Karten aufbauen können.</span><span class="sxs-lookup"><span data-stu-id="db509-104">Our hope is that through active developer communities like botness, and great partners like Slack and Kik, we can create a great ecosystem of cross-platform cards.</span></span>

## <a name="roadmap"></a><span data-ttu-id="db509-105">Roadmap</span><span class="sxs-lookup"><span data-stu-id="db509-105">Roadmap</span></span>

<span data-ttu-id="db509-106">[Hier](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog) findest du unsere aktuelle (nicht endgültige) Roadmap.</span><span class="sxs-lookup"><span data-stu-id="db509-106">You can see our [current (non-final) roadmap here](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog).</span></span> <span data-ttu-id="db509-107">Beachte bitte, dass sich alle Elemente dieser Roadmap ändern können und dass für kein Element garantiert werden kann, dass es tatsächlich ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="db509-107">Note that anything on here is subject to change, and is not a guarantee of shipping.</span></span>

## <a name="future-ideas"></a><span data-ttu-id="db509-108">Ideen für die Zukunft</span><span class="sxs-lookup"><span data-stu-id="db509-108">Future ideas</span></span>

<span data-ttu-id="db509-109">Im Folgenden findest du einige unserer Ideen für die Zukunft – alles noch in der Brainstormingphase.</span><span class="sxs-lookup"><span data-stu-id="db509-109">The following are some future ideas we have, which are simply in the brainstorm stage.</span></span> <span data-ttu-id="db509-110">Wenn dich eine dieser Ideen interessiert, freuen wir uns über einen Kommentar.</span><span class="sxs-lookup"><span data-stu-id="db509-110">If you're interested in any of these, let us know in a comment.</span></span>

### <a name="great-looking-cards-from-data"></a><span data-ttu-id="db509-111">Optimal entworfene Karten aus Daten</span><span class="sxs-lookup"><span data-stu-id="db509-111">Great looking Cards from Data</span></span>

<span data-ttu-id="db509-112">Wir wissen, dass viele Kartenersteller bereits über klar definierte Daten hinter ihren Karten verfügen.</span><span class="sxs-lookup"><span data-stu-id="db509-112">We know many card authors already have well-defined data behind their cards.</span></span> <span data-ttu-id="db509-113">Wir möchten ein Vorlagenmodell erkunden, das es ermöglicht, Karten (server- oder clientseitig) basierend auf solchen Daten und einem Repository mit klar definierten und anpassbaren Vorlagen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="db509-113">Our plan is to explore a templating model that would allow cards to be generated (server side or client side) based on the data and a repository of well-defined and customizable templates.</span></span>

### <a name="make-cards-responsive"></a><span data-ttu-id="db509-114">Reaktionsfähiges Layout für Karten</span><span class="sxs-lookup"><span data-stu-id="db509-114">Make cards responsive</span></span>

<span data-ttu-id="db509-115">Das Kartenlayout sollte sich dem verfügbaren Platz anpassen können.</span><span class="sxs-lookup"><span data-stu-id="db509-115">Card layouts should be reactive to available space.</span></span> <span data-ttu-id="db509-116">Adaptive Karten können sich auf viele verschiedene Geräte, Benutzeroberflächen und UI-Frameworks anpassen, sind aber noch nicht reaktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="db509-116">Adaptive cards are adaptable to different devices, ux styles and and ui frameworks, but they are not reactive yet.</span></span> <span data-ttu-id="db509-117">Es müssen zusätzliche Eigenschaften für Elemente definiert werden, die es Kartenerstellern ermöglichen, die notwendigen Hinweise an die Renderingbibliotheken zu übermitteln, sodass diese das Layout auf intelligente Weise anpassen können und die Absicht der Karte erhalten bleibt.</span><span class="sxs-lookup"><span data-stu-id="db509-117">Additional properties must be defined on elements which allow card producers to provide the necessary hints to the rendering libraries so that they can intelligently change the layout in a way which maintains the intent of the card.</span></span>

### <a name="responsive-exploration"></a><span data-ttu-id="db509-118">Reaktionsschnelle Erkundung</span><span class="sxs-lookup"><span data-stu-id="db509-118">Responsive exploration</span></span>

* <span data-ttu-id="db509-119">Eine **importance**-Eigenschaft liefert Hinweise zur Wichtigkeit des Inhalts.</span><span class="sxs-lookup"><span data-stu-id="db509-119">Add an **importance** property which annotates importance of content.</span></span> <span data-ttu-id="db509-120">Weniger wichtige Inhalte können verworfen werden, um den verfügbaren Platz für wichtige Inhalte zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="db509-120">Less important content can be dropped to fit available space</span></span>
* <span data-ttu-id="db509-121">**constraints**- und **policy**-Eigenschaften beschreiben, was passieren soll, wenn Einschränkungen nicht erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="db509-121">Add **constraints** and **policy** properties describing how to react when constraints can't be met.</span></span> 
  * <span data-ttu-id="db509-122">Inhalt kann ausgeblendet oder auf eine kleinere Größe reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="db509-122">Hide content or collapse content to smaller size.</span></span>
  * <span data-ttu-id="db509-123">Bei Überschreitung eines bestimmten Schwellenwerts kann `columnSet` in ein Spaltenkarussell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="db509-123">Add a threshold that, when exceeded, changes `columnSet` to carousel of columns.</span></span>

### <a name="new-element-types"></a><span data-ttu-id="db509-124">Neue Elementtypen</span><span class="sxs-lookup"><span data-stu-id="db509-124">New element types</span></span>

* <span data-ttu-id="db509-125">Landkarten/Stadtpläne</span><span class="sxs-lookup"><span data-stu-id="db509-125">Maps?</span></span> <span data-ttu-id="db509-126">– Einbetten einer Landkarte oder eines Stadtplans mit interaktiven Funktionen oder Fallback auf eine Bitmap</span><span class="sxs-lookup"><span data-stu-id="db509-126">- embed a map into a card with interactivity or fallback to bitmap</span></span>
* <span data-ttu-id="db509-127">*Welche Elemente benötigst du oder hättest du gerne?*</span><span class="sxs-lookup"><span data-stu-id="db509-127">*What elements do you want or need*?</span></span>

### <a name="new-rendering-libraries"></a><span data-ttu-id="db509-128">Neue Renderingbibliotheken</span><span class="sxs-lookup"><span data-stu-id="db509-128">New rendering libraries</span></span>

* <span data-ttu-id="db509-129">React?</span><span class="sxs-lookup"><span data-stu-id="db509-129">React?</span></span>
* <span data-ttu-id="db509-130">Xamarin?</span><span class="sxs-lookup"><span data-stu-id="db509-130">Xamarin?</span></span>
* <span data-ttu-id="db509-131">*Mit welchen Frameworks möchtest du arbeiten?*</span><span class="sxs-lookup"><span data-stu-id="db509-131">*What frameworks do you want?*</span></span>
