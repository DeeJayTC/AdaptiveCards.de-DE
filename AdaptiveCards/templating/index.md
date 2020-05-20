---
title: Übersicht über Vorlagen
author: matthidinger
ms.author: mahiding
ms.date: 05/18/2020
ms.topic: article
ms.openlocfilehash: db1f44c4465db88d375dec728bcb32d5933ef702
ms.sourcegitcommit: c921a7bb15a95c0ceb803ad375501ee3b8bef028
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83631369"
---
# <a name="adaptive-cards-templating"></a><span data-ttu-id="90186-102">Vorlagen für adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="90186-102">Adaptive Cards Templating</span></span>

<span data-ttu-id="90186-103">Wir freuen uns, Ihnen eine Vorschau neuer Tools zur Verfügung zu stellen ,mit denen Sie adaptive Karten **erstellen**, **wiederverwenden** und **freigeben** können.</span><span class="sxs-lookup"><span data-stu-id="90186-103">We're excited to share a preview of new tools that will help you **create**, **reuse**, and **share** Adaptive Cards.</span></span> 

> [!IMPORTANT] 
> 
> <span data-ttu-id="90186-104">**Breaking Changes** im **Release Candidate von Mai 2020**</span><span class="sxs-lookup"><span data-stu-id="90186-104">**Breaking changes** in the **May 2020 Release Candidate**</span></span>
>
> <span data-ttu-id="90186-105">Der Release Candidate für Vorlagen enthält einige kleinere, nicht abwärtskompatible Änderungen, die Sie kennen sollten, wenn Sie die älteren Pakete verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="90186-105">The templating release candidate includes some minor breaking changes that you should be aware of if you've been using the older packages.</span></span> <span data-ttu-id="90186-106">Einzelheiten finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="90186-106">See below for details.</span></span>


## <a name="breaking-changes-as-of-may-2020"></a><span data-ttu-id="90186-107">Breaking Changes Stand Mai 2020</span><span class="sxs-lookup"><span data-stu-id="90186-107">Breaking changes as of May 2020</span></span>

1. <span data-ttu-id="90186-108">Die Bindungssyntax wurde von `{...}` in `${...}` geändert.</span><span class="sxs-lookup"><span data-stu-id="90186-108">The binding syntax changed from `{...}` to `${...}`.</span></span> 
    * <span data-ttu-id="90186-109">Beispiel: Aus `"text": "Hello {name}"` wird `"text": "Hello ${name}"`.</span><span class="sxs-lookup"><span data-stu-id="90186-109">For Example: `"text": "Hello {name}"` becomes `"text": "Hello ${name}"`</span></span>
2. <span data-ttu-id="90186-110">Die JavaScript-API enthält kein `EvaluationContext`-Objekt mehr.</span><span class="sxs-lookup"><span data-stu-id="90186-110">The JavaScript API no longer contains an `EvaluationContext` object.</span></span> <span data-ttu-id="90186-111">Übergeben Sie Ihre Daten einfach an die `expand`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="90186-111">Simply pass your data to the `expand` function.</span></span> <span data-ttu-id="90186-112">Ausführliche Informationen finden Sie auf der [SDK-Seite](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="90186-112">Please see the [SDK page](sdk.md) for full details.</span></span>
3. <span data-ttu-id="90186-113">Die .NET-API wurde umgestaltet, damit sie der JavaScript-API besser entspricht.</span><span class="sxs-lookup"><span data-stu-id="90186-113">The .NET API was redesigned to more closely match the JavaScript API.</span></span> <span data-ttu-id="90186-114">Ausführliche Informationen finden Sie auf der [SDK-Seite](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="90186-114">Please see the [SDK page](sdk.md) for full details.</span></span>

## <a name="how-can-templating-help-you"></a><span data-ttu-id="90186-115">So können Vorlagen Ihnen helfen</span><span class="sxs-lookup"><span data-stu-id="90186-115">How can templating help you</span></span>

<span data-ttu-id="90186-116">Durch Vorlagen wird die Trennung von **Daten** aus dem **Layout** in einer adaptiven Karte ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="90186-116">Templating enables the separation of **data** from the **layout** in an Adaptive Card.</span></span> 

### <a name="it-helps-design-a-card-once-and-then-populate-it-with-real-data"></a><span data-ttu-id="90186-117">Dadurch können Karten einmalig erstellt und mit echten Daten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="90186-117">It helps design a card once, and then populate it with real data</span></span>

<span data-ttu-id="90186-118">Derzeit ist es nicht möglich, eine Karte mit dem [Adaptive Card Designer](https://adaptivecards.io/designer) (Designer für adaptive Karten) zu erstellen und mithilfe dieses JSON-Codes die Nutzlast mit **dynamischem Inhalt** aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="90186-118">Today it's impossible to create a card using the [Adaptive Card Designer](https://adaptivecards.io/designer) and use that JSON to populate the payload with **dynamic content**.</span></span> <span data-ttu-id="90186-119">Zu diesem Zweck müssen Sie benutzerdefinierten Code schreiben, um eine JSON-Zeichenfolge zu erstellen, oder die Objektmodell-SDKs verwenden, um ein Objektmodell zu erstellen, das Ihre Karte darstellt, und es zu JSON serialisieren.</span><span class="sxs-lookup"><span data-stu-id="90186-119">In order to achieve this you must write custom code to build a JSON string, or use the Object Model SDKs to build an OM representing your card and serialize it to JSON.</span></span> <span data-ttu-id="90186-120">In beiden Fällen erfolgt im Designer ein einmaliger unidirektionaler Vorgang, der es nicht einfach macht, den Kartenentwurf später zu optimieren, nachdem Sie ihn in Code umgewandelt haben.</span><span class="sxs-lookup"><span data-stu-id="90186-120">In either case the Designer is a one-time one-way operation and doesn't make it easy to tweak the card design later once you've converted it to code.</span></span>

### <a name="it-makes-transmissions-over-the-wire-smaller"></a><span data-ttu-id="90186-121">Die Menge der über das Netzwerk übertragenen Daten wird dadurch kleiner.</span><span class="sxs-lookup"><span data-stu-id="90186-121">It makes transmissions over the wire smaller</span></span>

<span data-ttu-id="90186-122">Stellen Sie sich eine Welt vor, in der eine Vorlage und Daten **direkt auf dem Client** kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="90186-122">Imagine a world where a template and data can be combined **directly on the client**.</span></span> <span data-ttu-id="90186-123">Das bedeutet, dass wenn Sie dieselbe Vorlage mehrmals verwenden oder sie mit neuen Daten aktualisieren möchten, Sie nur neue Daten an das Gerät senden müssen und es die gleiche Vorlage immer wieder verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="90186-123">This means if you use the same template multiple times, or want to update it with new data, you just need to send new data to the device and it can re-use the same template over and over.</span></span>

### <a name="it-helps-you-create-a-great-looking-card-from-just-the-data-you-provide"></a><span data-ttu-id="90186-124">Dies hilft Ihnen, eine ansprechende Karte nur anhand der von Ihnen bereitgestellten Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="90186-124">It helps you create a great looking card from just the data you provide</span></span>

<span data-ttu-id="90186-125">Wir denken, dass adaptive Karten großartig sind. Aber was wäre, wenn Sie nicht eine adaptive Karte für alles schreiben müssten, was Sie einem Benutzer zeigen möchten?</span><span class="sxs-lookup"><span data-stu-id="90186-125">We think Adaptive Cards are great, but what if you didn't have to write an Adaptive Card for everything you want to display to a user?</span></span> <span data-ttu-id="90186-126">Mit einem (nachstehend beschriebenen) Vorlagendienst können wir eine Lösung schaffen, in der jeder Vorlagen für jede Art von Daten beitragen, finden und freigeben kann.</span><span class="sxs-lookup"><span data-stu-id="90186-126">With a template service (described below) we can create a world where everyone can contribute, discover, and share templates over any type of data.</span></span> 

<span data-ttu-id="90186-127">Geben Sie sie in ihren eigenen Projekten, in Ihrer Organisation oder im gesamten Internet frei.</span><span class="sxs-lookup"><span data-stu-id="90186-127">Share within your own projects, your organization, or with the entire internet.</span></span>

### <a name="ai-and-other-services-could-improve-user-experiences"></a><span data-ttu-id="90186-128">Künstliche Intelligenz (KI) und andere Dienste können die Benutzerfreundlichkeit verbessern</span><span class="sxs-lookup"><span data-stu-id="90186-128">AI and other services could improve user experiences</span></span>

<span data-ttu-id="90186-129">Durch das Trennen von Daten und Inhalten öffnet sich für KI und andere Dienste eine Tür zur „vernünftigen“ Einschätzung der Daten in den Karten, die wir sehen, und zur Verbesserung der Benutzerproduktivität oder zum schnelleren Finden von Dingen.</span><span class="sxs-lookup"><span data-stu-id="90186-129">By separating data from content it opens a door for AI and other services to  "reason" over the data in the cards we see and enhance user productivity or help us find things.</span></span>

## <a name="what-is-adaptive-cards-templating"></a><span data-ttu-id="90186-130">Was sind Vorlagen für adaptive Karten?</span><span class="sxs-lookup"><span data-stu-id="90186-130">What is Adaptive Cards Templating?</span></span>

<span data-ttu-id="90186-131">Die Lösung besteht aus drei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="90186-131">It's comprised of 3 major components:</span></span>

1. <span data-ttu-id="90186-132">Die **[Vorlagensprache](language.md)** ist die Syntax, die zum Erstellen einer Vorlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90186-132">The **[Template Language](language.md)** is the syntax used for authoring a template.</span></span> <span data-ttu-id="90186-133">Mit dem Designer können Sie sogar eine Vorschau Ihrer Vorlagen zur Entwurfszeit anzeigen, indem Sie „Beispieldaten“ einfügen.</span><span class="sxs-lookup"><span data-stu-id="90186-133">The Designer even lets you preview your templates at design time by including "sample data".</span></span>
2. <span data-ttu-id="90186-134">Die **[Vorlagen-SDKs](sdk.md)** sind auf allen unterstützten Plattformen für adaptive Karten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="90186-134">The **[Templating SDK's](sdk.md)** will exist on all supported Adaptive Card platforms.</span></span> <span data-ttu-id="90186-135">Mit diesen SDKs können Sie eine Vorlage mit echten Daten auffüllen, entweder im Back-End oder direkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="90186-135">These SDKs allow you to populate a template with real data, on the back-end or directly on the client.</span></span> 
3. <span data-ttu-id="90186-136">Der **[Vorlagendienst](service.md)** ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="90186-136">The **[Template Service](service.md)** is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

## <a name="template-language"></a><span data-ttu-id="90186-137">Vorlagensprache</span><span class="sxs-lookup"><span data-stu-id="90186-137">Template Language</span></span>

<span data-ttu-id="90186-138">Die Vorlagensprache ist die Syntax, die zum Erstellen einer Vorlage einer adaptiven Karte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90186-138">The template language is the syntax used to author an Adaptive Card template.</span></span> 

> [!NOTE]
> 
> <span data-ttu-id="90186-139">Führen Sie das folgende Beispiel aus, um hier eine neue Registerkarte zu öffnen</span><span class="sxs-lookup"><span data-stu-id="90186-139">Follow along with the example below by opening up a new tab to</span></span>
>
> **https://adaptivecards.io/designer**
> 
> <span data-ttu-id="90186-140">Klicken Sie auf die Schaltfläche **Preview Mode** (Vorschaumodus), um zwischen Entwurfs- und Vorschaumodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="90186-140">Click the **Preview Mode** button to toggle between design-mode and preview-mode.</span></span>

![Screenshot des Designers](content/2019-08-01-13-58-27.png)

<span data-ttu-id="90186-142">Der neu aktualisierte Designer fügt Unterstützung für das Erstellen von Vorlagen und das Bereitstellen von **Beispieldaten** für die Vorschau der Karte zur Entwurfszeit hinzu.</span><span class="sxs-lookup"><span data-stu-id="90186-142">The newly updated Designer adds support for authoring templates and providing **Sample Data** to preview the card at design-time.</span></span>

<span data-ttu-id="90186-143">Fügen Sie das folgende Beispiel in den Bereich **Card Payload Editor** (Editor für die Kartennutzlast) ein:</span><span class="sxs-lookup"><span data-stu-id="90186-143">Paste the example below into the **Card Payload Editor** pane:</span></span> 

<span data-ttu-id="90186-144">**EmployeeCardTemplate.json**</span><span class="sxs-lookup"><span data-stu-id="90186-144">**EmployeeCardTemplate.json**</span></span>

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "ColumnSet",
            "style": "accent",
            "bleed": true,
            "columns": [
                {
                    "type": "Column",
                    "width": "auto",
                    "items": [
                        {
                            "type": "Image",
                            "url": "${photo}",
                            "altText": "Profile picture",
                            "size": "Small",
                            "style": "Person"
                        }
                    ]
                },
                {
                    "type": "Column",
                    "width": "stretch",
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Hi ${name}!",
                            "size": "Medium"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Here's a bit about your org...",
                            "spacing": "None"
                        }
                    ]
                }
            ]
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: **${manager.name}**"
        },
        {
            "type": "TextBlock",
            "text": "Your peers are:"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "$data": "${peers}",
                    "title": "${name}",
                    "value": "${title}"
                }
            ]
        }
    ]
}
```

<span data-ttu-id="90186-145">Fügen Sie dann die folgenden JSON-Daten in den **Sample Data Editor** (Beispieldaten-Editor) ein.</span><span class="sxs-lookup"><span data-stu-id="90186-145">Then paste the JSON data below into the **Sample Data Editor**.</span></span> 

<span data-ttu-id="90186-146">Mithilfe von **Beispieldaten** können Sie genau sehen, wie Ihre Karte zur Laufzeit aussieht, nachdem Sie echte Daten an sie übergeben haben.</span><span class="sxs-lookup"><span data-stu-id="90186-146">**Sample Data** helps you see exactly how your card will appear at runtime when passed actual data.</span></span>

<span data-ttu-id="90186-147">**EmployeeData**</span><span class="sxs-lookup"><span data-stu-id="90186-147">**EmployeeData**</span></span>

```json
{
    "name": "Matt",
    "photo": "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg",
    "manager": {
        "name": "Thomas",
        "title": "PM Lead"
    },
    "peers": [
        {
            "name": "Lei",
            "title": "Sr Program Manager"
        },
        {
            "name": "Andrew",
            "title": "Program Manager II"
        },
        {
            "name": "Mary Anne",
            "title": "Program Manager"
        }
    ]
}
```

<span data-ttu-id="90186-148">Klicken Sie auf die Schaltfläche **Preview Mode** (Vorschaumodus).</span><span class="sxs-lookup"><span data-stu-id="90186-148">Click the **Preview Mode** button.</span></span> <span data-ttu-id="90186-149">Die Karte sollte entsprechend den oben angegebenen Beispieldaten gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="90186-149">You should see the card render according to the sample data provided above.</span></span> <span data-ttu-id="90186-150">Zögern Sie nicht, Änderungen an den Beispieldaten vorzunehmen, und beobachten Sie die Aktualisierung der Karte in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="90186-150">Feel free to make tweaks to the sample data and watch the card update in realtime.</span></span>

<span data-ttu-id="90186-151">**Herzlichen Glückwunsch**. Sie haben soeben Ihre erste Vorlage erstellt!</span><span class="sxs-lookup"><span data-stu-id="90186-151">**Congratulations**, you just authored your first Adaptive Card Template!</span></span> <span data-ttu-id="90186-152">Als Nächstes erfahren Sie, wie Sie die Vorlage mit echten Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="90186-152">Next let's learn how to populate the template with real data.</span></span>

> <span data-ttu-id="90186-153">Weitere Informationen zur [Vorlagensprache](language.md)</span><span class="sxs-lookup"><span data-stu-id="90186-153">Learn more about the [template language](language.md)</span></span>

## <a name="sdk-support"></a><span data-ttu-id="90186-154">SDK-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="90186-154">SDK support</span></span>

<span data-ttu-id="90186-155">Die Vorlagen-SDKs ermöglichen es, eine Vorlage mit echten Daten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="90186-155">The Templating SDKs make it possible to populate a template with real-data.</span></span>

> [!NOTE]
>
> <span data-ttu-id="90186-156">Zum gegenwärtigen Zeitpunkt sind Vorlagen-SDKs für .NET und NodeJS erhältlich.</span><span class="sxs-lookup"><span data-stu-id="90186-156">At this time templating SDKs are available for .NET and NodeJS.</span></span> <span data-ttu-id="90186-157">Im Lauf der Zeit werden wir Vorlagen-SDKs für alle verbleibenden Plattformen für Adaptive Karten veröffentlichen, wie iOS, Android, UWP usw.</span><span class="sxs-lookup"><span data-stu-id="90186-157">Over time we will release templating SDKs for all remaining Adaptive Cards platform, like iOS, Android, UWP, etc.</span></span>

<span data-ttu-id="90186-158">Plattform</span><span class="sxs-lookup"><span data-stu-id="90186-158">Platform</span></span> | <span data-ttu-id="90186-159">Paket</span><span class="sxs-lookup"><span data-stu-id="90186-159">Package</span></span> | <span data-ttu-id="90186-160">Installation</span><span class="sxs-lookup"><span data-stu-id="90186-160">Install</span></span> | <span data-ttu-id="90186-161">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="90186-161">Documentation</span></span>
--- | --- | --- | ---
<span data-ttu-id="90186-162">JavaScript</span><span class="sxs-lookup"><span data-stu-id="90186-162">JavaScript</span></span> | <span data-ttu-id="90186-163">[![npm-Installation](https://img.shields.io/npm/v/adaptivecards-templating.svg)](https://www.npmjs.com/package/adaptivecards-templating)</span><span class="sxs-lookup"><span data-stu-id="90186-163">[![npm install](https://img.shields.io/npm/v/adaptivecards-templating.svg)](https://www.npmjs.com/package/adaptivecards-templating)</span></span> | `npm install adaptivecards-templating` | [<span data-ttu-id="90186-164">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="90186-164">Documentation</span></span>](https://www.npmjs.com/package/adaptivecards-templating)
<span data-ttu-id="90186-165">.NET</span><span class="sxs-lookup"><span data-stu-id="90186-165">.NET</span></span> | <span data-ttu-id="90186-166">[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Templating.svg)](https://www.nuget.org/packages/AdaptiveCards.Templating)</span><span class="sxs-lookup"><span data-stu-id="90186-166">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Templating.svg)](https://www.nuget.org/packages/AdaptiveCards.Templating)</span></span> | `dotnet add package AdaptiveCards.Templating` | [<span data-ttu-id="90186-167">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="90186-167">Documentation</span></span>](https://docs.microsoft.com/adaptive-cards/templating/sdk#net)

### <a name="javascript-example"></a><span data-ttu-id="90186-168">JavaScript-Beispiel</span><span class="sxs-lookup"><span data-stu-id="90186-168">JavaScript Example</span></span>

<span data-ttu-id="90186-169">Das folgende JavaScript zeigt das allgemeine Muster, das zum Auffüllen einer Vorlage mit Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90186-169">The JavaScript below shows the general pattern that will be used to populate a template with data.</span></span>

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

var card = template.expand({
    $root: {
        // Your data goes here
    }
});
// Now you have an AdaptiveCard ready to render!
```

> <span data-ttu-id="90186-170">Weitere Informationen zu den [Vorlagen-SDKs](sdk.md)</span><span class="sxs-lookup"><span data-stu-id="90186-170">Learn more about the [templating SDKs](sdk.md)</span></span>

## <a name="template-service"></a><span data-ttu-id="90186-171">Vorlagendienst</span><span class="sxs-lookup"><span data-stu-id="90186-171">Template Service</span></span>

<span data-ttu-id="90186-172">Der Vorlagendienst für adaptive Karten ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="90186-172">The Adaptive Cards Template Service is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

<span data-ttu-id="90186-173">Er ist nützlich, wenn Sie einige Daten anzeigen möchten, sich aber nicht die Mühe machen möchten, eine benutzerdefinierte adaptive Karte dafür zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="90186-173">It's useful if you want to display some data but don't want to bother writing a custom Adaptive Card for it.</span></span>

<span data-ttu-id="90186-174">Die API zum Abrufen einer Vorlage ist unkompliziert, aber der Dienst bietet tatsächlich viel mehr, einschließlich der Möglichkeit, Ihre Daten zu analysieren und eine Vorlage zu finden, die für Sie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="90186-174">The API to get a template is straight-forward enough, but the service actually offers much more, including the ability to analyze your data and find a template that might work for you.</span></span>

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

<span data-ttu-id="90186-175">Sämtliche Vorlagen sind flache JSON-Dateien, die in einem GitHub-Repository gespeichert sind, sodass jeder wie bei jedem anderen Open-Source-Code daran mitwirken kann.</span><span class="sxs-lookup"><span data-stu-id="90186-175">All templates are flat JSON files stored in a GitHub repo so anyone can contribute to them like any other open source code.</span></span>

> <span data-ttu-id="90186-176">Weitere Informationen zum [Kartenvorlagendienst](service.md)</span><span class="sxs-lookup"><span data-stu-id="90186-176">Learn more about the [card template Service](service.md)</span></span>

## <a name="whats-next-and-sending-feedback"></a><span data-ttu-id="90186-177">Nächste Schritte und Senden von Feedback</span><span class="sxs-lookup"><span data-stu-id="90186-177">What's next and sending feedback</span></span>

<span data-ttu-id="90186-178">Die Vorlagenerstellung und die Trennung der Präsentation von den Daten bringen uns unserem Ziel ein ganzes Stück näher, nämlich „einem Ökosystem für den standardisierten Austausch von Karteninhalten zwischen Apps und Diensten“.</span><span class="sxs-lookup"><span data-stu-id="90186-178">Templating and the separation of presentation from data takes us a whole lot closer toward our mission: "an ecosystem standardized content exchange between apps and services".</span></span> <span data-ttu-id="90186-179">Wir haben auf diesem Gebiet eine Menge zu bieten, also bleiben Sie am Ball, und informieren Sie uns auf [GitHub](https://github.com/Microsoft/AdaptiveCards/issues) über Ihre Erfahrungen!</span><span class="sxs-lookup"><span data-stu-id="90186-179">We've got plenty to deliver in this area, so stay tuned and let us know how it's working for you on [GitHub](https://github.com/Microsoft/AdaptiveCards/issues)!</span></span>
