---
title: Mit Adaptive Cards-Roadmap
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: f879c164b3471347ba8fa058827b3d79b09be4cd
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138003"
---
# <a name="future-work"></a><span data-ttu-id="2124b-102">Zukünftige Arbeit</span><span class="sxs-lookup"><span data-stu-id="2124b-102">Future work</span></span>

<span data-ttu-id="2124b-103">Während wir hervorragende Bearbeitung mit adaptive Cards definieren vorgenommen haben, ist immer noch viel zu tun.</span><span class="sxs-lookup"><span data-stu-id="2124b-103">While we have made excellent progress defining adaptive cards, there is still lots of work to do.</span></span> <span data-ttu-id="2124b-104">Unser Anliegen ist es, über aktive entwicklercommunitys wie Botness, und hervorragende Partner Wie Slack und Kik, wir eine hervorragende Ökosystem von Cross-Platform-Karten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="2124b-104">Our hope is that through active developer communities like botness, and great partners like Slack and Kik, we can create a great ecosystem of cross-platform cards.</span></span>

## <a name="roadmap"></a><span data-ttu-id="2124b-105">Roadmap</span><span class="sxs-lookup"><span data-stu-id="2124b-105">Roadmap</span></span>

<span data-ttu-id="2124b-106">Sehen Sie unsere [aktuellen (nicht endgültige) Roadmap für die hier](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog).</span><span class="sxs-lookup"><span data-stu-id="2124b-106">You can see our [current (non-final) roadmap here](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog).</span></span> <span data-ttu-id="2124b-107">Beachten Sie, dass alles hier unterliegt ist keine Garantie der Lieferung.</span><span class="sxs-lookup"><span data-stu-id="2124b-107">Note that anything on here is subject to change, and is not a guarantee of shipping.</span></span>

## <a name="future-ideas"></a><span data-ttu-id="2124b-108">Zukünftige Ideen</span><span class="sxs-lookup"><span data-stu-id="2124b-108">Future ideas</span></span>

<span data-ttu-id="2124b-109">Im folgenden werden einige zukünftigen Ideen, die wir erhalten haben, die einfach in der Phase Brainstorming sind.</span><span class="sxs-lookup"><span data-stu-id="2124b-109">The following are some future ideas we have, which are simply in the brainstorm stage.</span></span> <span data-ttu-id="2124b-110">Wenn Sie eines dieser interessiert sind, informieren Sie uns in einem Kommentar.</span><span class="sxs-lookup"><span data-stu-id="2124b-110">If you're interested in any of these, let us know in a comment.</span></span>

### <a name="great-looking-cards-from-data"></a><span data-ttu-id="2124b-111">Hervorragende aussehende Karten aus Daten</span><span class="sxs-lookup"><span data-stu-id="2124b-111">Great looking Cards from Data</span></span>

<span data-ttu-id="2124b-112">Wir wissen viele Karte-Autoren, die bereits über gut definierte Daten hinter ihren Karten verfügen.</span><span class="sxs-lookup"><span data-stu-id="2124b-112">We know many card authors already have well-defined data behind their cards.</span></span> <span data-ttu-id="2124b-113">Ist unsere Absicht, die eine Vorlagenmodell zu durchsuchen, die ermöglichen Karten generiert werden (serverseitige oder clientseitige) anhand der Daten und ein Repository mit klar definierten und anpassbare Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="2124b-113">Our plan is to explore a templating model that would allow cards to be generated (server side or client side) based on the data and a repository of well-defined and customizable templates.</span></span>

### <a name="make-cards-responsive"></a><span data-ttu-id="2124b-114">Stellen Sie Karten reagiert</span><span class="sxs-lookup"><span data-stu-id="2124b-114">Make cards responsive</span></span>

<span data-ttu-id="2124b-115">Kartenlayouts sollte auf den verfügbaren Platz reagieren.</span><span class="sxs-lookup"><span data-stu-id="2124b-115">Card layouts should be reactive to available space.</span></span> <span data-ttu-id="2124b-116">Mit Adaptive Cards sind anwendbar, die auf verschiedenen Geräten, Ux-Stile und und Benutzeroberflächen-Frameworks, aber sie sind reaktiv noch nicht.</span><span class="sxs-lookup"><span data-stu-id="2124b-116">Adaptive cards are adaptable to different devices, ux styles and and ui frameworks, but they are not reactive yet.</span></span> <span data-ttu-id="2124b-117">Für Elemente die Producer Karte, um die erforderlichen Hinweise an, der Rendering-Bibliotheken bieten, sodass sie auf intelligente Weise das Layout auf eine Weise ändern können, die und die Absicht der Karte verwaltet zu ermöglichen, müssen zusätzliche Eigenschaften definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2124b-117">Additional properties must be defined on elements which allow card producers to provide the necessary hints to the rendering libraries so that they can intelligently change the layout in a way which maintains the intent of the card.</span></span>

### <a name="responsive-exploration"></a><span data-ttu-id="2124b-118">Reaktionsfähige durchsuchen</span><span class="sxs-lookup"><span data-stu-id="2124b-118">Responsive exploration</span></span>

* <span data-ttu-id="2124b-119">Hinzufügen einer **Wichtigkeit** Eigenschaft, die Wichtigkeit des Inhalts kommentiert.</span><span class="sxs-lookup"><span data-stu-id="2124b-119">Add an **importance** property which annotates importance of content.</span></span> <span data-ttu-id="2124b-120">Weniger wichtig, dass der Inhalt gelöscht werden kann, um den verfügbaren Platz angepasst</span><span class="sxs-lookup"><span data-stu-id="2124b-120">Less important content can be dropped to fit available space</span></span>
* <span data-ttu-id="2124b-121">Hinzufügen **Einschränkungen** und **Richtlinie** Eigenschaften, die beschreibt, wie reagieren, wenn Einschränkungen nicht erfüllt werden können.</span><span class="sxs-lookup"><span data-stu-id="2124b-121">Add **constraints** and **policy** properties describing how to react when constraints can't be met.</span></span> 
  * <span data-ttu-id="2124b-122">Ausblenden von Inhalt, oder Inhalte auf kleinere Größe zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="2124b-122">Hide content or collapse content to smaller size.</span></span>
  * <span data-ttu-id="2124b-123">Fügen Sie einen Schwellenwert, wenn überschritten, ändert sich `columnSet` , Karussell von Spalten.</span><span class="sxs-lookup"><span data-stu-id="2124b-123">Add a threshold that, when exceeded, changes `columnSet` to carousel of columns.</span></span>

### <a name="new-element-types"></a><span data-ttu-id="2124b-124">Neue Elementtypen</span><span class="sxs-lookup"><span data-stu-id="2124b-124">New element types</span></span>

* <span data-ttu-id="2124b-125">Maps?</span><span class="sxs-lookup"><span data-stu-id="2124b-125">Maps?</span></span> <span data-ttu-id="2124b-126">-eine Zuordnung in eine Karte mit Interaktivität oder Fallback auf die Bitmap einbetten</span><span class="sxs-lookup"><span data-stu-id="2124b-126">- embed a map into a card with interactivity or fallback to bitmap</span></span>
* <span data-ttu-id="2124b-127">*Welche Elemente Sie möchten oder müssen*?</span><span class="sxs-lookup"><span data-stu-id="2124b-127">*What elements do you want or need*?</span></span>

### <a name="new-rendering-libraries"></a><span data-ttu-id="2124b-128">Neue Rendering-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="2124b-128">New rendering libraries</span></span>

* <span data-ttu-id="2124b-129">Reagieren?</span><span class="sxs-lookup"><span data-stu-id="2124b-129">React?</span></span>
* <span data-ttu-id="2124b-130">Xamarin?</span><span class="sxs-lookup"><span data-stu-id="2124b-130">Xamarin?</span></span>
* <span data-ttu-id="2124b-131">*Welche Frameworks sollen?*</span><span class="sxs-lookup"><span data-stu-id="2124b-131">*What frameworks do you want?*</span></span>
