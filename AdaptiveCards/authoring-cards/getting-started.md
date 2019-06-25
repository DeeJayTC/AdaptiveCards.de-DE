---
title: Erste Schritte
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552682"
---
# <a name="getting-started"></a><span data-ttu-id="70cfa-102">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="70cfa-102">Getting Started</span></span> 

<span data-ttu-id="70cfa-103">Eine adaptive Karte ist ein JSON-serialisiertes Kartenobjektmodell.</span><span class="sxs-lookup"><span data-stu-id="70cfa-103">An Adaptive Card is a JSON-serialized card object model.</span></span>

## <a name="adaptive-card-structure"></a><span data-ttu-id="70cfa-104">Struktur von adaptiven Karten</span><span class="sxs-lookup"><span data-stu-id="70cfa-104">Adaptive Card structure</span></span>

<span data-ttu-id="70cfa-105">Die grundlegende Struktur einer Karte ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="70cfa-105">The basic structure of a card is as follows:</span></span>

* <span data-ttu-id="70cfa-106">`AdaptiveCard`: Das Stammobjekt beschreibt die adaptive Karte, u. a. ihre Elementzusammensetzung, ihre Aktionen, wie sie gesprochen werden soll und die zum Rendern erforderliche Schemaversion.</span><span class="sxs-lookup"><span data-stu-id="70cfa-106">`AdaptiveCard` - The root object describes the AdaptiveCard itself, including its element makeup, its actions, how it should be spoken, and the schema version required to render it.</span></span>
* <span data-ttu-id="70cfa-107">`body`: Der Text der Karte besteht aus Bausteinen, die auch als `elements` bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="70cfa-107">`body` - The body of the card is made up of building-blocks known as `elements`.</span></span> <span data-ttu-id="70cfa-108">Elemente können in nahezu unbegrenzten Anordnungen zusammengesetzt werden, um viele Typen von Karten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="70cfa-108">Elements can be composed in nearly infinite arrangements to create many types of cards.</span></span> 
* <span data-ttu-id="70cfa-109">`actions`: Viele Karten haben einen Satz von Aktionen, die ein Benutzer ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="70cfa-109">`actions` - Many cards have a set of actions a user may take on it.</span></span> <span data-ttu-id="70cfa-110">Diese Eigenschaft beschreibt die Aktionen, die in der Regel in einer „Aktionsleiste“ am unteren Rand gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="70cfa-110">This property describes those actions which typically get rendered in an "action bar" at the bottom.</span></span>

### <a name="example-card"></a><span data-ttu-id="70cfa-111">Beispielkarte</span><span class="sxs-lookup"><span data-stu-id="70cfa-111">Example Card</span></span>

<span data-ttu-id="70cfa-112">Diese Beispielkarte enthält eine einzelne Textzeile gefolgt von einem Bild.</span><span class="sxs-lookup"><span data-stu-id="70cfa-112">This sample card which includes a single line of text followed by an image.</span></span>

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

## <a name="type-property"></a><span data-ttu-id="70cfa-113">`Type`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="70cfa-113">`Type` property</span></span>

<span data-ttu-id="70cfa-114">Jedes Element verfügt über eine `type`-Eigenschaft, die angibt, um welche Art von Objekt es sich handelt.</span><span class="sxs-lookup"><span data-stu-id="70cfa-114">Every element has a `type` property which identifies what kind of object it is.</span></span> <span data-ttu-id="70cfa-115">Auf der oben gezeigten Karte siehst du zwei Elemente: `TextBlock` und `Image`.</span><span class="sxs-lookup"><span data-stu-id="70cfa-115">Looking at the above card, you can see we have two elements, a `TextBlock` and an `Image`.</span></span>

<span data-ttu-id="70cfa-116">Alle Elemente einer adaptiven Karte sind **vertikal gestapelt** und **auf die Breite des übergeordneten Elements erweitert**  (wie bei `display: block` in HTML).</span><span class="sxs-lookup"><span data-stu-id="70cfa-116">All Adaptive Card elements **stack vertically** and **expand to the width of their parent** (think `display: block` in HTML).</span></span> <span data-ttu-id="70cfa-117">Mit `ColumnSet` kannst du jedoch nebeneinander angeordnete Containerspalten erstellen.</span><span class="sxs-lookup"><span data-stu-id="70cfa-117">However, you can use a `ColumnSet` to create side-by-side columns of containers.</span></span>

## <a name="adaptive-elements"></a><span data-ttu-id="70cfa-118">Adaptive Elemente</span><span class="sxs-lookup"><span data-stu-id="70cfa-118">Adaptive Elements</span></span>

<span data-ttu-id="70cfa-119">Die grundlegenden Elemente sind:</span><span class="sxs-lookup"><span data-stu-id="70cfa-119">The most fundamental elements are:</span></span>

* <span data-ttu-id="70cfa-120">**TextBlock**: Fügt einen Textblock mit Eigenschaften hinzu, die steuern, wie der Text aussieht.</span><span class="sxs-lookup"><span data-stu-id="70cfa-120">**TextBlock** - adds a block of text with properties to control what the text looks like</span></span>
* <span data-ttu-id="70cfa-121">**Image**: Fügt ein Bild mit Eigenschaften hinzu, die steuern, wie das Bild aussieht.</span><span class="sxs-lookup"><span data-stu-id="70cfa-121">**Image** - adds an image with properties to control what the image looks like</span></span>

## <a name="container-elements"></a><span data-ttu-id="70cfa-122">Containerelemente</span><span class="sxs-lookup"><span data-stu-id="70cfa-122">Container elements</span></span>

<span data-ttu-id="70cfa-123">Karten verfügen unter Umständen auch über Container, die eine Sammlung untergeordneter Elemente anordnen.</span><span class="sxs-lookup"><span data-stu-id="70cfa-123">Cards can also have containers, which arrange a collection of child elements.</span></span>

* <span data-ttu-id="70cfa-124">**Container**: Definiert eine Auflistung von Elementen.</span><span class="sxs-lookup"><span data-stu-id="70cfa-124">**Container** - Defines a a collection of elements</span></span>
* <span data-ttu-id="70cfa-125">**ColumnSet/Column**: Definiert eine Sammlung von Spalten, jede Spalte ist ein Container.</span><span class="sxs-lookup"><span data-stu-id="70cfa-125">**ColumnSet/Column** - Defines a collection of columns, each column is a container</span></span>
* <span data-ttu-id="70cfa-126">**FactSet**: Container mit Fakten</span><span class="sxs-lookup"><span data-stu-id="70cfa-126">**FactSet** - Container of Facts</span></span>
* <span data-ttu-id="70cfa-127">**ImageSet**: Container mit Bildern, damit die Benutzeroberfläche für die Sammlung von Bildern einen entsprechenden Bilderkatalog anzeigen kann</span><span class="sxs-lookup"><span data-stu-id="70cfa-127">**ImageSet** - Container of Images so that UI can show appropriate photo gallery experience for a collection of images.</span></span>

## <a name="input-elements"></a><span data-ttu-id="70cfa-128">Eingabeelemente</span><span class="sxs-lookup"><span data-stu-id="70cfa-128">Input elements</span></span>

<span data-ttu-id="70cfa-129">Mit Eingabeelementen kannst du die native Benutzeroberfläche zum Erstellen einfacher Formulare auffordern:</span><span class="sxs-lookup"><span data-stu-id="70cfa-129">Input elements allow you to ask for native UI to build simple forms:</span></span>

* <span data-ttu-id="70cfa-130">**Input.Text**: Abrufen von Textinhalt vom Benutzer</span><span class="sxs-lookup"><span data-stu-id="70cfa-130">**Input.Text** - get text content from the user</span></span>
* <span data-ttu-id="70cfa-131">**Input.Date**: Abrufen eines Datums vom Benutzer</span><span class="sxs-lookup"><span data-stu-id="70cfa-131">**Input.Date** - get a Date from the user</span></span>
* <span data-ttu-id="70cfa-132">**Input.Time**: Abrufen einer Uhrzeit vom Benutzer</span><span class="sxs-lookup"><span data-stu-id="70cfa-132">**Input.Time** - get a Time from the user</span></span>
* <span data-ttu-id="70cfa-133">**Input.Number**: Abrufen einer Nummer vom Benutzer</span><span class="sxs-lookup"><span data-stu-id="70cfa-133">**Input.Number** - get a Number from the user</span></span>
* <span data-ttu-id="70cfa-134">**Input.ChoiceSet**: Bereitstellen von Auswahlmöglichkeiten, aus denen der Benutzer wählen kann</span><span class="sxs-lookup"><span data-stu-id="70cfa-134">**Input.ChoiceSet** - Give the user a set of choices and have them pick</span></span>
* <span data-ttu-id="70cfa-135">**Input.Toggle**: Bereitstellen einer Auswahl aus zwei Elementen, aus denen der Benutzer wählen kann</span><span class="sxs-lookup"><span data-stu-id="70cfa-135">**Input.Toggle** - Give the user a single choice between two items and have them pick</span></span>

## <a name="actions"></a><span data-ttu-id="70cfa-136">Aktionen</span><span class="sxs-lookup"><span data-stu-id="70cfa-136">Actions</span></span>

<span data-ttu-id="70cfa-137">Aktionen fügen der Karte Schaltflächen hinzu.</span><span class="sxs-lookup"><span data-stu-id="70cfa-137">Actions add buttons to the card.</span></span> <span data-ttu-id="70cfa-138">Diese können eine Reihe von Aktionen ausführen, wie etwa das Öffnen einer URL oder das Senden von Daten.</span><span class="sxs-lookup"><span data-stu-id="70cfa-138">These can perform a variety of actions, like opening a URL or submitting some data.</span></span>

* <span data-ttu-id="70cfa-139">**Action.OpenUrl**: Die Schaltfläche öffnet eine externe URL zur Ansicht.</span><span class="sxs-lookup"><span data-stu-id="70cfa-139">**Action.OpenUrl** - the button opens an external URL for viewing</span></span>
* <span data-ttu-id="70cfa-140">**Action.ShowCard**: Fordert eine untergeordnete Karte an, die dem Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="70cfa-140">**Action.ShowCard** - Requests a sub-card to be shown to the user.</span></span>
* <span data-ttu-id="70cfa-141">**Action.Submit**: Fordert an, dass alle Eingabeelemente in einem Objekt zusammengefasst werden, das dir anschließend über eine von der Hostanwendung definierte Methode geschickt wird.</span><span class="sxs-lookup"><span data-stu-id="70cfa-141">**Action.Submit** - Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

> <span data-ttu-id="70cfa-142">**Example Action.Submit**: „Action.Submit“ sendet per Skype eine Bot Framework-Botaktivität zurück an den Bot mit der **Value**-Eigenschaft, die ein Objekt mit allen Eingabedaten dazu enthält.</span><span class="sxs-lookup"><span data-stu-id="70cfa-142">**Example Action.Submit**: With Skype, an Action.Submit will send a Bot Framework bot activity back to the bot with the **Value** property containing an object with all of the input data on it.</span></span>

## <a name="learn-more"></a><span data-ttu-id="70cfa-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70cfa-143">Learn More</span></span>

* <span data-ttu-id="70cfa-144">Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.</span><span class="sxs-lookup"><span data-stu-id="70cfa-144">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="70cfa-145">Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer)</span><span class="sxs-lookup"><span data-stu-id="70cfa-145">Use the [Schema Explorer](http://adaptivecards.io/explorer) to browse the available elements</span></span>
* <span data-ttu-id="70cfa-146">Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/)</span><span class="sxs-lookup"><span data-stu-id="70cfa-146">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/)</span></span>
* <span data-ttu-id="70cfa-147">[Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.</span><span class="sxs-lookup"><span data-stu-id="70cfa-147">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
