---
title: Erste Schritte
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552682"
---
# <a name="getting-started"></a><span data-ttu-id="d3ed8-102">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="d3ed8-102">Getting Started</span></span> 

<span data-ttu-id="d3ed8-103">Eine Adaptive Card handelt es sich um eine JSON-serialisierten Karte-Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-103">An Adaptive Card is a JSON-serialized card object model.</span></span>

## <a name="adaptive-card-structure"></a><span data-ttu-id="d3ed8-104">Adaptive Card-Struktur</span><span class="sxs-lookup"><span data-stu-id="d3ed8-104">Adaptive Card structure</span></span>

<span data-ttu-id="d3ed8-105">Die grundlegende Struktur einer Karte lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d3ed8-105">The basic structure of a card is as follows:</span></span>

* <span data-ttu-id="d3ed8-106">`AdaptiveCard` -Das Stammobjekt beschreibt die AdaptiveCard selbst, wie z.B. die Zusammensetzung des Elements die Aktionen, wie sie gesprochene werden soll und die Schemaversion, die zum Rendern erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-106">`AdaptiveCard` - The root object describes the AdaptiveCard itself, including its element makeup, its actions, how it should be spoken, and the schema version required to render it.</span></span>
* <span data-ttu-id="d3ed8-107">`body` -Der Text der Karte besteht aus Bausteinen – bekannt als `elements`.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-107">`body` - The body of the card is made up of building-blocks known as `elements`.</span></span> <span data-ttu-id="d3ed8-108">Elemente können in nahezu unbegrenzte Anordnungen viele Typen von Karten erstellen zusammengestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-108">Elements can be composed in nearly infinite arrangements to create many types of cards.</span></span> 
* <span data-ttu-id="d3ed8-109">`actions` – Für viele Karten, haben einen Satz von Aktionen, die ein Benutzer darauf ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-109">`actions` - Many cards have a set of actions a user may take on it.</span></span> <span data-ttu-id="d3ed8-110">Diese Eigenschaft beschreibt die Aktionen, die in der Regel in "Aktionsleiste" am unteren Rand gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-110">This property describes those actions which typically get rendered in an "action bar" at the bottom.</span></span>

### <a name="example-card"></a><span data-ttu-id="d3ed8-111">Beispiel-Karte</span><span class="sxs-lookup"><span data-stu-id="d3ed8-111">Example Card</span></span>

<span data-ttu-id="d3ed8-112">Diese Beispiel-Karte eine einzelne Textzeile gefolgt von einem Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-112">This sample card which includes a single line of text followed by an image.</span></span>

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Here is a ninja cat"
        },
        {
            "type": "Image",
            "url": "http://adaptivecards.io/content/cats/1.png"
        }
    ]
}
```

## <a name="type-property"></a><span data-ttu-id="d3ed8-113">`Type` Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d3ed8-113">`Type` property</span></span>

<span data-ttu-id="d3ed8-114">Jedes Element verfügt über eine `type` Eigenschaft, der angibt, welche Art von Objekt ist.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-114">Every element has a `type` property which identifies what kind of object it is.</span></span> <span data-ttu-id="d3ed8-115">Betrachten die oben genannten Karte, sehen Sie haben wir zwei Elementen, die eine `TextBlock` und `Image`.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-115">Looking at the above card, you can see we have two elements, a `TextBlock` and an `Image`.</span></span>

<span data-ttu-id="d3ed8-116">Alle Elemente der Adaptive Card **vertikal gestapelt** und **erweitern, der die Breite des übergeordneten** (denken `display: block` im HTML-Format).</span><span class="sxs-lookup"><span data-stu-id="d3ed8-116">All Adaptive Card elements **stack vertically** and **expand to the width of their parent** (think `display: block` in HTML).</span></span> <span data-ttu-id="d3ed8-117">Sie können jedoch eine `ColumnSet` , Seite-an-Seite-Spalten von Containern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-117">However, you can use a `ColumnSet` to create side-by-side columns of containers.</span></span>

## <a name="adaptive-elements"></a><span data-ttu-id="d3ed8-118">Adaptive Elemente</span><span class="sxs-lookup"><span data-stu-id="d3ed8-118">Adaptive Elements</span></span>

<span data-ttu-id="d3ed8-119">Die grundlegendsten Elemente sind:</span><span class="sxs-lookup"><span data-stu-id="d3ed8-119">The most fundamental elements are:</span></span>

* <span data-ttu-id="d3ed8-120">**TextBlock** -Fügt einen Block von Text mit Eigenschaften, die steuern, wie der Text aussieht</span><span class="sxs-lookup"><span data-stu-id="d3ed8-120">**TextBlock** - adds a block of text with properties to control what the text looks like</span></span>
* <span data-ttu-id="d3ed8-121">**Image** -Fügt ein Bild mit Eigenschaften, die steuern, wie das Bild aussieht</span><span class="sxs-lookup"><span data-stu-id="d3ed8-121">**Image** - adds an image with properties to control what the image looks like</span></span>

## <a name="container-elements"></a><span data-ttu-id="d3ed8-122">Containerelemente</span><span class="sxs-lookup"><span data-stu-id="d3ed8-122">Container elements</span></span>

<span data-ttu-id="d3ed8-123">Karten können auch Container verfügen, die eine Auflistung der untergeordneten Elemente anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-123">Cards can also have containers, which arrange a collection of child elements.</span></span>

* <span data-ttu-id="d3ed8-124">**Container** -definiert eine eine Auflistung von Elementen</span><span class="sxs-lookup"><span data-stu-id="d3ed8-124">**Container** - Defines a a collection of elements</span></span>
* <span data-ttu-id="d3ed8-125">**Spaltensatz-Spalte** -definiert eine Auflistung von Spalten, jede Spalte ist ein Container</span><span class="sxs-lookup"><span data-stu-id="d3ed8-125">**ColumnSet/Column** - Defines a collection of columns, each column is a container</span></span>
* <span data-ttu-id="d3ed8-126">**FactSet** -Container von Fakten</span><span class="sxs-lookup"><span data-stu-id="d3ed8-126">**FactSet** - Container of Facts</span></span>
* <span data-ttu-id="d3ed8-127">**ImageSet** -von Containerimages, damit die Benutzeroberfläche entsprechende anzeigen kann Fotos Oberfläche für den Anwendungskatalog für eine Sammlung von Bildern.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-127">**ImageSet** - Container of Images so that UI can show appropriate photo gallery experience for a collection of images.</span></span>

## <a name="input-elements"></a><span data-ttu-id="d3ed8-128">Input-Elemente</span><span class="sxs-lookup"><span data-stu-id="d3ed8-128">Input elements</span></span>

<span data-ttu-id="d3ed8-129">Input-Elemente können Sie native Benutzeroberfläche Erstellung einfacher Formulare anfordern:</span><span class="sxs-lookup"><span data-stu-id="d3ed8-129">Input elements allow you to ask for native UI to build simple forms:</span></span>

* <span data-ttu-id="d3ed8-130">**Input.Text** -Text-Inhalt wird vom Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-130">**Input.Text** - get text content from the user</span></span>
* <span data-ttu-id="d3ed8-131">**Input.Date** -erhalten Sie vom Benutzer ein Datum</span><span class="sxs-lookup"><span data-stu-id="d3ed8-131">**Input.Date** - get a Date from the user</span></span>
* <span data-ttu-id="d3ed8-132">**Input.Time** -erhalten Sie eine Zeit vom Benutzer</span><span class="sxs-lookup"><span data-stu-id="d3ed8-132">**Input.Time** - get a Time from the user</span></span>
* <span data-ttu-id="d3ed8-133">**Input.Number** – eine Anzahl vom Benutzer abrufen</span><span class="sxs-lookup"><span data-stu-id="d3ed8-133">**Input.Number** - get a Number from the user</span></span>
* <span data-ttu-id="d3ed8-134">**Input.ChoiceSet** : Weisen Sie dem Benutzer eine Reihe von Auswahlmöglichkeiten und diese auswählen</span><span class="sxs-lookup"><span data-stu-id="d3ed8-134">**Input.ChoiceSet** - Give the user a set of choices and have them pick</span></span>
* <span data-ttu-id="d3ed8-135">**Input.Toggle** : Weisen Sie dem Benutzer eine einzelne Auswahl zwischen zwei Elementen, und diese auswählen</span><span class="sxs-lookup"><span data-stu-id="d3ed8-135">**Input.Toggle** - Give the user a single choice between two items and have them pick</span></span>

## <a name="actions"></a><span data-ttu-id="d3ed8-136">Aktionen</span><span class="sxs-lookup"><span data-stu-id="d3ed8-136">Actions</span></span>

<span data-ttu-id="d3ed8-137">Aktionen Hinzufügen von Schaltflächen auf der Karte.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-137">Actions add buttons to the card.</span></span> <span data-ttu-id="d3ed8-138">Diese können eine Reihe von Aktionen, wie Sie eine URL öffnen oder Senden von Daten führen.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-138">These can perform a variety of actions, like opening a URL or submitting some data.</span></span>

* <span data-ttu-id="d3ed8-139">**Action.OpenUrl** -die Schaltfläche öffnet eine externe URL für die Anzeige</span><span class="sxs-lookup"><span data-stu-id="d3ed8-139">**Action.OpenUrl** - the button opens an external URL for viewing</span></span>
* <span data-ttu-id="d3ed8-140">**Action.ShowCard** -Anforderungen von einer untergeordneten Karte, die dem Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-140">**Action.ShowCard** - Requests a sub-card to be shown to the user.</span></span>
* <span data-ttu-id="d3ed8-141">**Action.Submit** -stellen Sie für alle Elemente mit der Eingabe in ein Objekt gesammelt werden, um die über eine Methode, die von der hostanwendung definiert dann an Sie gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-141">**Action.Submit** - Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

> <span data-ttu-id="d3ed8-142">**Beispiel-Action.Submit**: Mit Skype, ein Action.Submit sendet einen Bot Framework Bot Aktivität an den Bot mit den **Wert** Eigenschaft, die mit einem Objekt mit allen der Eingabedaten auf.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-142">**Example Action.Submit**: With Skype, an Action.Submit will send a Bot Framework bot activity back to the bot with the **Value** property containing an object with all of the input data on it.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d3ed8-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d3ed8-143">Learn More</span></span>

* <span data-ttu-id="d3ed8-144">[Beispiel-Karten Durchsuchen](http://adaptivecards.io/samples/) inspirieren</span><span class="sxs-lookup"><span data-stu-id="d3ed8-144">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="d3ed8-145">Verwenden der [Schema-Explorer](http://adaptivecards.io/explorer) um die verfügbaren Elemente zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d3ed8-145">Use the [Schema Explorer](http://adaptivecards.io/explorer) to browse the available elements</span></span>
* <span data-ttu-id="d3ed8-146">Erstellen einer Karte mit den [interaktive Schnellansicht](http://adaptivecards.io/visualizer/)</span><span class="sxs-lookup"><span data-stu-id="d3ed8-146">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/)</span></span>
* <span data-ttu-id="d3ed8-147">[Kontakt aufnehmen](http://adaptivecards.io/connect) mit Sie haben Feedback</span><span class="sxs-lookup"><span data-stu-id="d3ed8-147">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
