---
title: Vorlagendienst für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 81d1e598b6157b6ba1fedbf458a7c624705afcd5
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878887"
---
# <a name="adaptive-cards-template-service"></a><span data-ttu-id="cb782-102">Vorlagendienst für adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="cb782-102">Adaptive Cards Template Service</span></span>

<span data-ttu-id="cb782-103">Der Vorlagendienst für adaptive Karten ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.</span><span class="sxs-lookup"><span data-stu-id="cb782-103">The Adaptive Cards Template Service is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

<span data-ttu-id="cb782-104">Er ist nützlich, wenn Sie einige Daten anzeigen möchten, sich aber nicht die Mühe machen möchten, eine benutzerdefinierte adaptive Karte dafür zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cb782-104">It's useful if you want to display some data but don't want to bother writing a custom adaptive card for it.</span></span>

> <span data-ttu-id="cb782-105">Hier finden Sie einen [Überblick über Vorlagen für adaptive Karten](index.md).</span><span class="sxs-lookup"><span data-stu-id="cb782-105">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="cb782-106">*Geschäftsbedingungen und Vertrag*</span><span class="sxs-lookup"><span data-stu-id="cb782-106">*Terms and agreement*</span></span> 
> 
> <span data-ttu-id="cb782-107">Dieser **alpha-level**-Dienst wird „in der vorliegenden Form“ und mit allen möglichen Fehler und ohne jeglichen Support bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="cb782-107">This **alpha-level** service is provided "as-is", with all faults and is not supported in any way.</span></span> <span data-ttu-id="cb782-108">Jede Datensammlung des Diensts unterliegt der [Microsoft-Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?LinkID=824704).</span><span class="sxs-lookup"><span data-stu-id="cb782-108">Any data collection from the service is subject to the [Microsoft privacy statement](https://go.microsoft.com/fwlink/?LinkID=824704).</span></span>
> 
> <span data-ttu-id="cb782-109">Diese Features befinden sich **in der Vorschauphase und können geändert werden**.</span><span class="sxs-lookup"><span data-stu-id="cb782-109">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="cb782-110">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.</span><span class="sxs-lookup"><span data-stu-id="cb782-110">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

## <a name="how-does-the-service-help-me"></a><span data-ttu-id="cb782-111">Wie unterstützt der Dienst mich?</span><span class="sxs-lookup"><span data-stu-id="cb782-111">How does the service help me?</span></span>

<span data-ttu-id="cb782-112">Angenommen, ich verfüge nur über ein einziges Datenelement, beispielsweise Finanzdaten, Microsoft Graph-Daten, schema.org-Daten oder benutzerdefinierte Daten aus meiner Organisation.</span><span class="sxs-lookup"><span data-stu-id="cb782-112">Let's say I just got a piece of data, maybe it's financial data, Microsoft Graph data, schema.org data, or custom data from within my organization.</span></span> 

<span data-ttu-id="cb782-113">Jetzt möchte ich die Daten für einen Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cb782-113">Now I want to display the data to a user.</span></span> 

<span data-ttu-id="cb782-114">Normalerweise bedeutet dies, dass ich benutzerdefinierten Benutzeroberflächencode in allen Front-End-Stapeln schreiben muss, die für Endbenutzer bereitstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cb782-114">Traditionally that means writing custom UI code in all of the front-end stacks that I deliver to end-users.</span></span>

<span data-ttu-id="cb782-115">Was wäre jedoch, wenn meine App neue Benutzeroberflächenvorlagen basierend auf dem Typ der Daten „erlernen“ könnte?</span><span class="sxs-lookup"><span data-stu-id="cb782-115">But what if there were a world where my app could "learn" new UI templates based on the type of data?</span></span> <span data-ttu-id="cb782-116">Was, wenn jeder an Benutzeroberflächenvorlagen mitwirken, diese verbessern und in eigenen Projekten innerhalb einer Organisation oder für das gesamte Internet freigeben könnte?</span><span class="sxs-lookup"><span data-stu-id="cb782-116">A world where anyone could contribute, enhance, and share common UI templates, within their own projects, within an organization, or for the entire internet.</span></span>

## <a name="what-is-the-card-template-service"></a><span data-ttu-id="cb782-117">Was ist der Kartenvorlagendienst?</span><span class="sxs-lookup"><span data-stu-id="cb782-117">What is the card template service?</span></span>

<span data-ttu-id="cb782-118">Der Kartenvorlagendienst ist ein einfacher REST-Endpunkt, der Folgendes unterstützt:</span><span class="sxs-lookup"><span data-stu-id="cb782-118">The card template service is a simple REST endpoint that helps:</span></span>

* <span data-ttu-id="cb782-119">**Suchen** einer Vorlage durch Analysieren der Struktur Ihrer Daten</span><span class="sxs-lookup"><span data-stu-id="cb782-119">**Find** a template by analyzing the structure of your data</span></span>
* <span data-ttu-id="cb782-120">**Abrufen** einer Vorlage mit einer direkten Bindung auf dem Client, *ohne dass die Daten an den Server gesendet werden oder das Gerät jemals verlassen*</span><span class="sxs-lookup"><span data-stu-id="cb782-120">**Get** a template so you can bind it directly on the client, *without sending your data to the server or ever leaving the device*</span></span>
* <span data-ttu-id="cb782-121">**Auffüllen** einer Vorlage auf dem Server, wenn die clientseitige Datenbindung nicht geeignet oder nicht möglich ist</span><span class="sxs-lookup"><span data-stu-id="cb782-121">**Populate** a template on the server, when client-side data binding isn't appropriate or possible</span></span>

<span data-ttu-id="cb782-122">Dahinter steht:</span><span class="sxs-lookup"><span data-stu-id="cb782-122">Behind it all, is:</span></span>

* <span data-ttu-id="cb782-123">Ein freigegebenes Open Source-Vorlagenrepository, das von GitHub unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="cb782-123">A shared, open-source template repository backed by GitHub.</span></span> <span data-ttu-id="cb782-124">*(Das Repository ist zurzeit privat, wird jedoch öffentlich gemacht, sobald einige lose Enden verknüpft sind.)*</span><span class="sxs-lookup"><span data-stu-id="cb782-124">*(The repo is currently private but will be made public as soon as we tie up some loose ends)*</span></span>
* <span data-ttu-id="cb782-125">Alle Vorlagen sind JSON-Flatfiles im Repository, wodurch das Bearbeiten, Mitwirken und Freigeben zu einem natürlichen Bestandteil des Entwicklerworkflows wird.</span><span class="sxs-lookup"><span data-stu-id="cb782-125">All the templates are flat JSON files in the repo, which makes editing, contributing, and sharing a natural part of a developer workflow.</span></span>
* <span data-ttu-id="cb782-126">Der Code für den Dienst wird zur Verfügung gestellt, sodass Sie ihn überall dort hosten können, wo es für Sie am sinnvollsten ist.</span><span class="sxs-lookup"><span data-stu-id="cb782-126">The code for the service will be made available so you can host wherever makes the most sense to you.</span></span> 

## <a name="using-the-service"></a><span data-ttu-id="cb782-127">Verwenden des Diensts</span><span class="sxs-lookup"><span data-stu-id="cb782-127">Using the service</span></span>

### <a name="get-all-templates"></a><span data-ttu-id="cb782-128">Abrufen aller Vorlagen</span><span class="sxs-lookup"><span data-stu-id="cb782-128">Get all templates</span></span> 

<span data-ttu-id="cb782-129">Dieser Endpunkt gibt eine Liste aller bekannten Vorlagen zurück.</span><span class="sxs-lookup"><span data-stu-id="cb782-129">This endpoint returns a list of all known templates.</span></span>

> `HTTP GET https://templates.adaptivecards.io/list`

<span data-ttu-id="cb782-130">**Antwortauszug**</span><span class="sxs-lookup"><span data-stu-id="cb782-130">**Response excerpt**</span></span>

```json
{
  "graph.microsoft.com": {
    "templates": [
      {
        "file": "Files.json",
        "fullPath": "graph.microsoft.com/Files.json"
      },
      {
        "file": "Profile.json",
        "fullPath": "graph.microsoft.com/Profile.json"
      }
   ]
}
```

### <a name="find-a-template"></a><span data-ttu-id="cb782-131">Suchen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="cb782-131">Find a template</span></span>

<span data-ttu-id="cb782-132">Dieser Endpunkt versucht, eine Vorlage durch Analysieren der Struktur Ihrer Daten zu finden.</span><span class="sxs-lookup"><span data-stu-id="cb782-132">This endpoint tries to find a template by analyzing the structure of your data.</span></span>

> `HTTP POST https://templates.adaptivecards.io/find`

#### <a name="example"></a><span data-ttu-id="cb782-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb782-133">Example</span></span>

<span data-ttu-id="cb782-134">Angenommen, ich klicke einfach auf einen [Microsoft Graph](https://graph.microsoft.com)-Endpunkt, um Organisationsdaten über mich abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cb782-134">Let's say I just hit a [Microsoft Graph](https://graph.microsoft.com) endpoint to get organizational data about me.</span></span>

> `HTTP GET https://graph.microsoft.com/v1.0/me/`

![Graph-Explorer-Screenshot](content/2019-08-01-12-08-13.png)

<span data-ttu-id="cb782-136">Diese API gab **JSON-Daten** zurück, aber wie kann ich Benutzern **diese Daten mit adaptiven Karten anzeigen**?</span><span class="sxs-lookup"><span data-stu-id="cb782-136">That API returned **JSON data**, but how do I **display it** to users using Adaptive Cards?</span></span> 

<span data-ttu-id="cb782-137">Zuerst möchte ich überprüfen, ob für diese Art von Daten eine Vorlage vorhanden ist. Daher stelle ich eine HTTP-Anforderung an den `/find`-Endpunkt mit meinen Daten im `POST body`.</span><span class="sxs-lookup"><span data-stu-id="cb782-137">First I want to see if a template exists for this type of data, so I make an HTTP request to the `/find` endpoint with my data in the `POST body`.</span></span>

```
HTTP POST https://templates.adaptivecards.io/find

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "businessPhones": [
        "+1 412 555 0109"
    ],
    "displayName": "Megan Bowen",
    "givenName": "Megan",
    "jobTitle": "Auditor",
    "mail": "MeganB@M365x214355.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": "12/1110",
    "preferredLanguage": "en-US",
    "surname": "Bowen",
    "userPrincipalName": "MeganB@M365x214355.onmicrosoft.com",
    "id": "48d31887-5fad-4d73-a9f5-3c356e68a038"
}
```

<span data-ttu-id="cb782-138">**Antwort:**</span><span class="sxs-lookup"><span data-stu-id="cb782-138">**Response:**</span></span>

```json
[
  {
    "templateUrl": "graph.microsoft.com/Profile.json",
    "confidence": 1
  }
]
```

<span data-ttu-id="cb782-139">Der Dienst gibt eine Liste aller übereinstimmenden Vorlagen zurück, zusammen mit einem `confidence`-Element, das angibt, wie genau die Übereinstimmung ist.</span><span class="sxs-lookup"><span data-stu-id="cb782-139">The service returns a list of any matching templates, along with a `confidence` indicating how close the match is.</span></span> <span data-ttu-id="cb782-140">Jetzt kann ich diese Vorlagen-URL verwenden, um die Vorlage **abzurufen** oder sie serverseitig **aufzufüllen**.</span><span class="sxs-lookup"><span data-stu-id="cb782-140">Now I can use that template URL to **get** the template, or **populate** it server-side.</span></span>

### <a name="get-a-template"></a><span data-ttu-id="cb782-141">Abrufen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="cb782-141">Get a template</span></span>

<span data-ttu-id="cb782-142">Eine Vorlage, die von diesem Endpunkt abgerufen wird, kann zur Laufzeit [unter Verwendung des Vorlagen-SDKs](sdk.md) mit Daten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="cb782-142">A template retrieved from this endpoint can be populated with data at runtime [using the templatng SDKs](sdk.md).</span></span>

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]`

<span data-ttu-id="cb782-143">Sie können auch „Beispieldaten“ in die Vorlage einschließen, sodass die Bearbeitung im Designer benutzerfreundlicher wird:</span><span class="sxs-lookup"><span data-stu-id="cb782-143">You can also include "sample data" with the template, which makes editing in the designer more friendly:</span></span>

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]?sampleData=true`

#### <a name="example"></a><span data-ttu-id="cb782-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb782-144">Example</span></span>

<span data-ttu-id="cb782-145">Abrufen der Microsoft Graph-Profilvorlage, die von `/find` oben zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cb782-145">Let's get the Microsoft Graph profile template that was returned from `/find` above.</span></span>

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

<span data-ttu-id="cb782-146">**Antwortauszug**</span><span class="sxs-lookup"><span data-stu-id="cb782-146">**Response excerpt**</span></span>

```json
{
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "{name}"
    },
    {
        // ...snip
    }
  ]
}
```

<span data-ttu-id="cb782-147">Verwenden Sie diese Vorlage jetzt mit den [Vorlagen-SDKs](sdk.md), um eine zum Rendern bereite adaptive Karte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb782-147">Now use this template with the [templating SDKs](sdk.md) to create a ready-to-render Adaptive Card.</span></span>

### <a name="populate-a-template-server-side"></a><span data-ttu-id="cb782-148">Serverseitiges Auffüllen einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="cb782-148">Populate a template server-side</span></span>

<span data-ttu-id="cb782-149">In einigen Fällen ist es möglicherweise nicht sinnvoll, eine Vorlage auf dem Client aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="cb782-149">In some cases it may not make sense to populate a template on the client.</span></span>  <span data-ttu-id="cb782-150">In diesen Anwendungsfällen können Sie vom Dienst eine vollständig aufgefüllte adaptive Karte zurückgeben lassen, die bereit für die Übergabe an einen beliebigen Renderer für adaptive Karten ist.</span><span class="sxs-lookup"><span data-stu-id="cb782-150">For these use cases, you can have the service return a fully-populated Adaptive Card, ready to be passed to any Adaptive Card Renderer.</span></span>

> `HTTP POST https://templates.adaptivecards.io/[TEMPLATE-PATH]`

#### <a name="example"></a><span data-ttu-id="cb782-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb782-151">Example</span></span>

<span data-ttu-id="cb782-152">Auffüllen der Microsoft Graph-Profilvorlage, die von `/find` oben zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cb782-152">Let's populate the Microsoft Graph profile template that was returned from `/find` using the data above.</span></span>

```
HTTP POST https://templates.adaptivecards.io/graph.microsoft.com/Profile.json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "businessPhones": [
        "+1 412 555 0109"
    ],
    "displayName": "Megan Bowen",
    "givenName": "Megan",
    "jobTitle": "Auditor",
    "mail": "MeganB@M365x214355.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": "12/1110",
    "preferredLanguage": "en-US",
    "surname": "Bowen",
    "userPrincipalName": "MeganB@M365x214355.onmicrosoft.com",
    "id": "48d31887-5fad-4d73-a9f5-3c356e68a038"
}
```

<span data-ttu-id="cb782-153">**Antwortauszug**</span><span class="sxs-lookup"><span data-stu-id="cb782-153">**Response excerpt**</span></span>

```json
{
  "type": "AdaptiveCard",
  "version": "1.0",
  "body": [
    {
      "type": "TextBlock",
      "size": "Medium",
      "weight": "Bolder",
      "text": "Megan Bowen"
    },
    {
        // ...snip
    }
  ]
}
```

<span data-ttu-id="cb782-154">Beachten Sie, dass die Antwort den Text des ersten `TextBlock` durch `"Megan Bowen"` anstelle von `"{name}"` ersetzt hat, wie in der `GET`-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cb782-154">Notice how the response replaced the text of the first `TextBlock` with `"Megan Bowen"` instead of `"{name}"`, as in the `GET` request.</span></span> <span data-ttu-id="cb782-155">Diese adaptive Karte kann nun ohne clientseitige Vorlagenanwendung an einen beliebigen Renderer für adaptive Karten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb782-155">This AdaptiveCard can now be passed to any Adaptive Card renderer without going through client-side templating.</span></span>

## <a name="contributing-templates"></a><span data-ttu-id="cb782-156">Beitragende Vorlagen</span><span class="sxs-lookup"><span data-stu-id="cb782-156">Contributing templates</span></span>

<span data-ttu-id="cb782-157">Der Vorlagendienst wird von einem GitHub-Repository unterstützt. Das Repository ist zurzeit **privat**, wird jedoch als Open Source verfügbar gemacht, sobald einige lose Enden verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="cb782-157">The template service is backed by a GitHub repo (which is currently **private**), but we will open source once we tie up some loose ends.</span></span>

<span data-ttu-id="cb782-158">Wir hoffen, dass wir mithilfe von GitHub als Sicherungsspeicher für die Vorlagen den Prozess der Erstellung, Verbesserung und Freigabe von Vorlagen „demokratischer“ gestalten können.</span><span class="sxs-lookup"><span data-stu-id="cb782-158">Our hope is that by using GitHub as a backing store for the templates, we can "democratize" the process of authoring, enhancing, and sharing templates.</span></span> <span data-ttu-id="cb782-159">Jeder kann einen Pull Request mit einer völlig neuen Vorlage übermitteln oder Verbesserungen an vorhandenen Vorlagen vornehmen, und zwar alles innerhalb der entwicklerfreundlichen GitHub-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="cb782-159">Anyone can submit a Pull Request that includes an entirely new template, or make enhancements to existing ones... all within the developer-friendly experience of GitHub.</span></span>

## <a name="self-hosting-the-service"></a><span data-ttu-id="cb782-160">Selbsthosting des Diensts</span><span class="sxs-lookup"><span data-stu-id="cb782-160">Self-hosting the service</span></span>

<span data-ttu-id="cb782-161">Nicht alle Datentypen sind für den unter `https://templates.adaptivecards.io` gehosteten „zentralen“ Vorlagendienst für adaptive Karten geeignet.</span><span class="sxs-lookup"><span data-stu-id="cb782-161">Not all types of data are appropriate for the "central" Adaptive Cards template service hosted at `https://templates.adaptivecards.io`.</span></span> 

<span data-ttu-id="cb782-162">Wir möchten sicherstellen, dass alle Benutzer den Vorlagendienst in Ihrer Organisation hosten können, um den Quellcode verfügbar zu machten, und wir vereinfachen die Bereitstellung in Azure oder in Ihrem eigenen Back-End.</span><span class="sxs-lookup"><span data-stu-id="cb782-162">We want to make sure anyone can host the template service within your organization, so the source code will be made available and we'll make it very simple to deploy to Azure or your own back-end.</span></span>

<span data-ttu-id="cb782-163">Weitere Informationen hierzu zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="cb782-163">More on this at a later date.</span></span>