---
title: Übersicht über Vorlagen
author: matthidinger
ms.author: mahiding
ms.date: 07/29/2019
ms.topic: article
ms.openlocfilehash: ca21c70abc4638db8f96f3564d9e006aea39f926
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878947"
---
# <a name="adaptive-cards-templating-preview"></a><span data-ttu-id="d0b29-102">Vorlagen für adaptive Karten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d0b29-102">Adaptive Cards Templating (Preview)</span></span>

<span data-ttu-id="d0b29-103">Wir freuen uns, Ihnen eine Vorschau neuer Tools zur Verfügung zu stellen ,mit denen Sie adaptive Karten **erstellen**, **wiederverwenden** und **freigeben** können.</span><span class="sxs-lookup"><span data-stu-id="d0b29-103">We're excited to share a preview of new tools that will help you **create**, **reuse**, and **share** Adaptive Cards.</span></span> 

> [!IMPORTANT] 
> 
> <span data-ttu-id="d0b29-104">Diese Features befinden sich **in der Vorschauphase und können geändert werden**.</span><span class="sxs-lookup"><span data-stu-id="d0b29-104">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="d0b29-105">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.</span><span class="sxs-lookup"><span data-stu-id="d0b29-105">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

## <a name="how-can-templating-help-you"></a><span data-ttu-id="d0b29-106">Wie können Vorlagen Ihnen helfen?</span><span class="sxs-lookup"><span data-stu-id="d0b29-106">How can templating help you?</span></span>

<span data-ttu-id="d0b29-107">Durch Vorlagen wird die Trennung von **Daten** aus dem **Layout** in einer adaptiven Karte ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d0b29-107">Templating enables the separation of **data** from the **layout** in an Adaptive Card.</span></span> 

### <a name="it-helps-design-a-card-once-and-then-populate-it-with-real-data"></a><span data-ttu-id="d0b29-108">Dadurch können Karten einmalig erstellt und mit echten Daten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="d0b29-108">It helps design a card once, and then populate it with real data</span></span>

<span data-ttu-id="d0b29-109">Derzeit ist es nicht möglich, eine Karte mit dem [Adaptive Card Designer](https://adaptivecards.io/designer) (Designer für adaptive Karten) zu erstellen und mithilfe dieses JSON-Codes die Nutzlast mit **dynamischem Inhalt** aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-109">Today it's impossible to create a card using the [Adaptive Card Designer](https://adaptivecards.io/designer) and use that JSON to populate the payload with **dynamic content**.</span></span> <span data-ttu-id="d0b29-110">Zu diesem Zweck müssen Sie benutzerdefinierten Code schreiben, um eine JSON-Zeichenfolge zu erstellen, oder die Objektmodell-SDKs verwenden, um ein Objektmodell zu erstellen, das Ihre Karte darstellt, und es zu JSON serialisieren.</span><span class="sxs-lookup"><span data-stu-id="d0b29-110">In order to achieve this you must write custom code to build a JSON string, or use the Object Model SDKs to build an OM representing your card and serialize it to JSON.</span></span> <span data-ttu-id="d0b29-111">In beiden Fällen erfolgt im Designer ein einmaliger unidirektionaler Vorgang, der es nicht einfach macht, den Kartenentwurf später zu optimieren, nachdem Sie ihn in Code umgewandelt haben.</span><span class="sxs-lookup"><span data-stu-id="d0b29-111">In either case the Designer is a one-time one-way operation and doesn't make it easy to tweak the card design later once you've converted it to code.</span></span>

### <a name="it-makes-tranmissions-over-the-wire-smaller"></a><span data-ttu-id="d0b29-112">Die Menge der über das Netzwerk übertragenen Daten wird dadurch kleiner.</span><span class="sxs-lookup"><span data-stu-id="d0b29-112">It makes tranmissions over the wire smaller</span></span>

<span data-ttu-id="d0b29-113">Stellen Sie sich eine Welt vor, in der eine Vorlage und Daten **direkt auf dem Client** kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="d0b29-113">Imagine a world where a template and data can be combined **directly on the client**.</span></span> <span data-ttu-id="d0b29-114">Das bedeutet, dass wenn Sie dieselbe Vorlage mehrmals verwenden oder sie mit neuen Daten aktualisieren möchten, Sie nur neue Daten an das Gerät senden müssen und es die gleiche Vorlage immer wieder verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="d0b29-114">This means if you use the same template multiple times, or want to update it with new data, you just need to send new data to the device and it can re-use the same template over and over.</span></span>

### <a name="it-helps-you-create-a-great-looking-card-from-just-the-data-you-provide"></a><span data-ttu-id="d0b29-115">Dies hilft Ihnen, eine ansprechende Karte nur anhand der von Ihnen bereitgestellten Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-115">It helps you create a great looking card from just the data you provide</span></span>

<span data-ttu-id="d0b29-116">Wir denken, dass adaptive Karten großartig sind. Aber was wäre, wenn Sie nicht eine adaptive Karte für alles schreiben müssten, was Sie einem Benutzer zeigen möchten?</span><span class="sxs-lookup"><span data-stu-id="d0b29-116">We think Adaptive Cards are great, but what if you didn't have to write an Adaptive Card for everything you want to display to a user?</span></span> <span data-ttu-id="d0b29-117">Mit einem (nachstehend beschriebenen) Vorlagendienst können wir eine Lösung schaffen, in der jeder Vorlagen für jede Art von Daten beitragen, finden und freigeben kann.</span><span class="sxs-lookup"><span data-stu-id="d0b29-117">With a template service (described below) we can create a world where everyone can contribute, discover, and share templates over any type of data.</span></span> 

<span data-ttu-id="d0b29-118">Geben Sie sie in ihren eigenen Projekten, in Ihrer Organisation oder im gesamten Internet frei.</span><span class="sxs-lookup"><span data-stu-id="d0b29-118">Share within your own projects, your organization, or with the entire internet.</span></span>

### <a name="ai-and-other-services-could-improve-user-experiences"></a><span data-ttu-id="d0b29-119">Künstliche Intelligenz (KI) und andere Dienste können die Benutzerfreundlichkeit verbessern</span><span class="sxs-lookup"><span data-stu-id="d0b29-119">AI and other services could improve user experiences</span></span>

<span data-ttu-id="d0b29-120">Durch das Trennen von Daten und Inhalten öffnet sich für KI und andere Dienste eine Tür zur „vernünftigen“ Einschätzung der Daten in den Karten, die wir sehen, und zur Verbesserung der Benutzerproduktivität oder zum schnelleren Finden von Dingen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-120">By separating data from content it opens a door for AI and other services to  "reason" over the data in the cards we see and enhance user productivity or help us find things.</span></span>

## <a name="what-is-adaptive-cards-templating"></a><span data-ttu-id="d0b29-121">Was sind Vorlagen für adaptive Karten?</span><span class="sxs-lookup"><span data-stu-id="d0b29-121">What is Adaptive Cards Templating?</span></span>

<span data-ttu-id="d0b29-122">Die Lösung besteht aus drei Hauptkomponenten:</span><span class="sxs-lookup"><span data-stu-id="d0b29-122">It's comprised of 3 major components:</span></span>

1. <span data-ttu-id="d0b29-123">Die **[Vorlagensprache](language.md)** ist die Syntax, die zum Erstellen einer Vorlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0b29-123">The **[Template Language](language.md)** is the syntax used for authoring a template.</span></span> <span data-ttu-id="d0b29-124">Mit dem Designer können Sie sogar eine Vorschau Ihrer Vorlagen zur Entwurfszeit anzeigen, indem Sie „Beispieldaten“ einfügen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-124">The Designer even lets you preview your templates at design time by including "sample data".</span></span>
2. <span data-ttu-id="d0b29-125">Die **[Vorlagen-SDKs](sdk.md)** sind auf allen unterstützten Plattformen für adaptive Karten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d0b29-125">The **[Templating SDK's](sdk.md)** will exist on all supported Adaptive Card platforms.</span></span> <span data-ttu-id="d0b29-126">Mit diesen SDKs können Sie eine Vorlage mit echten Daten auffüllen, entweder im Back-End oder direkt auf dem Client.</span><span class="sxs-lookup"><span data-stu-id="d0b29-126">These SDKs allow you to populate a template with real data, on the back-end or directly on the client.</span></span> 
3. <span data-ttu-id="d0b29-127">Der **[Vorlagendienst](service.md)** ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="d0b29-127">The **[Template Service](service.md)** is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

## <a name="template-language"></a><span data-ttu-id="d0b29-128">Vorlagensprache</span><span class="sxs-lookup"><span data-stu-id="d0b29-128">Template Language</span></span>

<span data-ttu-id="d0b29-129">Die Vorlagensprache ist die Syntax, die zum Erstellen einer Vorlage einer adaptiven Karte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0b29-129">The template langauge is the syntax used to author an Adaptive Card template.</span></span> 

> [!NOTE]
> 
> <span data-ttu-id="d0b29-130">Führen Sie das folgende Beispiel aus, um hier eine neue Registerkarte zu öffnen</span><span class="sxs-lookup"><span data-stu-id="d0b29-130">Follow along with the example below by opening up a new tab to</span></span>
>
> **https://vnext.adaptivecards.io/designer**
> 
> <span data-ttu-id="d0b29-131">Klicken Sie auf die Schaltfläche **Preview Mode** (Vorschaumodus), um zwischen Entwurfs- und Vorschaumodus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="d0b29-131">Click the **Preview Mode** button to toggle between design-mode and preview-mode.</span></span>

![Screenshot des Designers](content/2019-08-01-13-58-27.png)

<span data-ttu-id="d0b29-133">Der [vNext Designer](https://vnext.adaptivecards.io/designer) fügt Unterstützung für das Erstellen von Vorlagen und das Bereitstellen von **Beispieldaten** für die Vorschau der Karte zur Entwurfszeit hinzu.</span><span class="sxs-lookup"><span data-stu-id="d0b29-133">The ["vNext Designer"](https://vnext.adaptivecards.io/designer) adds support for authoring templates and providing **Sample Data** to preview the card at design-time.</span></span>

<span data-ttu-id="d0b29-134">Fügen Sie das folgende Beispiel in den Bereich **Card Payload Editor** (Editor für die Kartennutzlast) ein:</span><span class="sxs-lookup"><span data-stu-id="d0b29-134">Paste the example below into the **Card Payload Editor** pane:</span></span> 

<span data-ttu-id="d0b29-135">**EmployeeCardTemplate.json**</span><span class="sxs-lookup"><span data-stu-id="d0b29-135">**EmployeeCardTemplate.json**</span></span>

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
                            "url": "{photo}",
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
                            "text": "Hi {name}!",
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
            "text": "Your manager is: **{manager.name}**"
        },
        {
            "type": "TextBlock",
            "text": "Your peers are:"
        },
        {
            "type": "FactSet",
            "facts": [
                {
                    "$data": "{peers}",
                    "title": "{name}",
                    "value": "{title}"
                }
            ]
        }
    ]
}
```

<span data-ttu-id="d0b29-136">Fügen Sie dann die folgenden JSON-Daten in den **Sample Data Editor** (Beispieldaten-Editor) ein.</span><span class="sxs-lookup"><span data-stu-id="d0b29-136">Then paste the JSON data below into the **Sample Data Editor**.</span></span> 

<span data-ttu-id="d0b29-137">Mithilfe von **Beispieldaten** können Sie genau sehen, wie Ihre Karte zur Laufzeit aussieht, nachdem Sie echte Daten an sie übergeben haben.</span><span class="sxs-lookup"><span data-stu-id="d0b29-137">**Sample Data** helps you see exactly how your card will appear at runtime when passed actual data.</span></span>

<span data-ttu-id="d0b29-138">**EmployeeData**</span><span class="sxs-lookup"><span data-stu-id="d0b29-138">**EmployeeData**</span></span>

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

<span data-ttu-id="d0b29-139">Klicken Sie auf die Schaltfläche **Preview Mode** (Vorschaumodus).</span><span class="sxs-lookup"><span data-stu-id="d0b29-139">Click the **Preview Mode** button.</span></span> <span data-ttu-id="d0b29-140">Die Karte sollte entsprechend den oben angegebenen Beispieldaten gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="d0b29-140">You should see the card render according to the sample data provided above.</span></span> <span data-ttu-id="d0b29-141">Zögern Sie nicht, Änderungen an den Beispieldaten vorzunehmen, und beobachten Sie die Aktualisierung der Karte in Echtzeit.</span><span class="sxs-lookup"><span data-stu-id="d0b29-141">Feel free to make tweaks to the sample data and watch the card update in realtime.</span></span>

<span data-ttu-id="d0b29-142">**Herzlichen Glückwunsch**. Sie haben soeben Ihre erste Vorlage erstellt!</span><span class="sxs-lookup"><span data-stu-id="d0b29-142">**Congratulations**, you just authored your first Adaptive Card Template!</span></span> <span data-ttu-id="d0b29-143">Als Nächstes erfahren Sie, wie Sie die Vorlage mit echten Daten auffüllen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-143">Next let's learn how to populate the template with real data.</span></span>

> <span data-ttu-id="d0b29-144">Weitere Informationen zur [Vorlagensprache](language.md)</span><span class="sxs-lookup"><span data-stu-id="d0b29-144">Learn more about the [template language](language.md)</span></span>

## <a name="sdk-support"></a><span data-ttu-id="d0b29-145">SDK-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d0b29-145">SDK support</span></span>

<span data-ttu-id="d0b29-146">Die Vorlagen-SDKs ermöglichen es, eine Vorlage mit echten Daten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-146">The Templating SDKs make it possible to populate a template with real-data.</span></span>

> [!NOTE]
>
> <span data-ttu-id="d0b29-147">In der ersten Vorschauphase steht nur eine begrenzte Anzahl von SDKs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d0b29-147">During the initial preview we only have a limited set of SDKs available.</span></span> <span data-ttu-id="d0b29-148">Nach der Veröffentlichung wird es Vorlagenbibliotheken für jede unterstützte Plattform für adaptive Karten geben.</span><span class="sxs-lookup"><span data-stu-id="d0b29-148">When we release there will be templating libraries for every supported Adaptive Cards platform.</span></span>

<span data-ttu-id="d0b29-149">Plattform</span><span class="sxs-lookup"><span data-stu-id="d0b29-149">Platform</span></span> | <span data-ttu-id="d0b29-150">Installieren</span><span class="sxs-lookup"><span data-stu-id="d0b29-150">Install</span></span> | <span data-ttu-id="d0b29-151">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d0b29-151">Documentation</span></span>
--- | --- | ---
<span data-ttu-id="d0b29-152">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d0b29-152">JavaScript</span></span> | `npm install adaptivecards-templating` | [<span data-ttu-id="d0b29-153">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d0b29-153">Documentation</span></span>](https://www.npmjs.com/package/adaptivecards-templating)
<span data-ttu-id="d0b29-154">.NET</span><span class="sxs-lookup"><span data-stu-id="d0b29-154">.NET</span></span> | <span data-ttu-id="d0b29-155">*In Kürze verfügbar*</span><span class="sxs-lookup"><span data-stu-id="d0b29-155">*coming soon*</span></span> | <span data-ttu-id="d0b29-156">*In Kürze verfügbar*</span><span class="sxs-lookup"><span data-stu-id="d0b29-156">*coming soon*</span></span>

### <a name="javascript-example"></a><span data-ttu-id="d0b29-157">JavaScript-Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0b29-157">JavaScript Example</span></span>

<span data-ttu-id="d0b29-158">Das folgende JavaScript zeigt das allgemeine Muster, das zum Auffüllen einer Vorlage mit Daten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0b29-158">The JavaScript below shows the general pattern that will be used to populate a template with data.</span></span>

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

var dataContext = new ACData.EvaluationContext();
dataContext.$root = {
    // Data goes here
};

var card = template.expand(dataContext);
// Now you have an AdaptiveCard ready to render!
```

> <span data-ttu-id="d0b29-159">Weitere Informationen zu den [Vorlagen-SDKs](sdk.md)</span><span class="sxs-lookup"><span data-stu-id="d0b29-159">Learn more about the [templating SDKs](sdk.md)</span></span>

## <a name="template-service"></a><span data-ttu-id="d0b29-160">Vorlagendienst</span><span class="sxs-lookup"><span data-stu-id="d0b29-160">Template Service</span></span>

<span data-ttu-id="d0b29-161">Der Vorlagendienst für adaptive Karten ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="d0b29-161">The Adaptive Cards Template Service is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

<span data-ttu-id="d0b29-162">Er ist nützlich, wenn Sie einige Daten anzeigen möchten, sich aber nicht die Mühe machen möchten, eine benutzerdefinierte adaptive Karte dafür zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d0b29-162">It's useful if you want to display some data but don't want to bother writing a custom Adaptive Card for it.</span></span>

<span data-ttu-id="d0b29-163">Die API zum Abrufen einer Vorlage ist unkompliziert, aber der Dienst bietet tatsächlich viel mehr, einschließlich der Möglichkeit, Ihre Daten zu analysieren und eine Vorlage zu finden, die für Sie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="d0b29-163">The API to get a template is straight-forward enough, but the service actually offers much more, including the ability to analyze your data and find a template that might work for you.</span></span>

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

<span data-ttu-id="d0b29-164">Sämtliche Vorlagen sind flache JSON-Dateien, die in einem GitHub-Repository gespeichert sind, sodass jeder wie bei jedem anderen Open-Source-Code daran mitwirken kann.</span><span class="sxs-lookup"><span data-stu-id="d0b29-164">All templates are flat JSON files stored in a GitHub repo so anyone can contribute to them like any other open source code.</span></span>

> <span data-ttu-id="d0b29-165">Weitere Informationen zum [Kartenvorlagendienst](service.md)</span><span class="sxs-lookup"><span data-stu-id="d0b29-165">Learn more about the [card template Service](service.md)</span></span>

## <a name="whats-next-and-sending-feedback"></a><span data-ttu-id="d0b29-166">Nächste Schritte und Senden von Feedback</span><span class="sxs-lookup"><span data-stu-id="d0b29-166">What's next and sending feedback</span></span>

<span data-ttu-id="d0b29-167">Die Vorlagenerstellung und Trennung der Präsentation von den Daten bringt uns unserem Ziel ein ganzes Stück näher, nämlich „einem Ökosystem für den Austausch von Karteninhalten auf einheitliche Weise“.</span><span class="sxs-lookup"><span data-stu-id="d0b29-167">Templating and the separation of presentation from data takes us a whole lot closer toward our mission: "an ecosystem for exchanging card content in a common and consistent way".</span></span>

<span data-ttu-id="d0b29-168">Wir sind bestrebt, Ihnen schnellstmöglich mehr Informationen zukommen zu lassen.</span><span class="sxs-lookup"><span data-stu-id="d0b29-168">We're eager to share more as soon as we can.</span></span> <span data-ttu-id="d0b29-169">Geben Sie in der Zwischenzeit hier Feedback: [GitHub](https://github.com/microsoft/AdaptiveCards) oder Twitter **[@MattHidinger](https://twitter.com/matthidinger)** / **#AdaptiveCards**.</span><span class="sxs-lookup"><span data-stu-id="d0b29-169">In the meantime please give feedback here, [GitHub](https://github.com/microsoft/AdaptiveCards), or Twitter **[@MattHidinger](https://twitter.com/matthidinger)**/**#AdaptiveCards**.</span></span> 
