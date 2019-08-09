---
title: Vorlagen Dienst für Adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 81d1e598b6157b6ba1fedbf458a7c624705afcd5
ms.sourcegitcommit: a16f53ba10a8607deacde5c8cc78927cac58657c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2019
ms.locfileid: "68878887"
---
# <a name="adaptive-cards-template-service"></a><span data-ttu-id="6370c-102">Vorlagen Dienst für Adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="6370c-102">Adaptive Cards Template Service</span></span>

<span data-ttu-id="6370c-103">Der Vorlagen Dienst für Adaptive Karten ist ein Proof of Concept-Dienst, mit dem jeder eine Reihe bekannter Vorlagen finden, mitwirken und freigeben kann.</span><span class="sxs-lookup"><span data-stu-id="6370c-103">The Adaptive Cards Template Service is a proof-of-concept service that allows anyone to find, contribute to, and share a set of well-known templates.</span></span>

<span data-ttu-id="6370c-104">Es ist nützlich, wenn Sie einige Daten anzeigen möchten, aber nicht mit dem Schreiben einer benutzerdefinierten adaptiven Karte für die Daten.</span><span class="sxs-lookup"><span data-stu-id="6370c-104">It's useful if you want to display some data but don't want to bother writing a custom adaptive card for it.</span></span>

> <span data-ttu-id="6370c-105">Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="6370c-105">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="6370c-106">*Bestimmungen und Vereinbarung*</span><span class="sxs-lookup"><span data-stu-id="6370c-106">*Terms and agreement*</span></span> 
> 
> <span data-ttu-id="6370c-107">Dieser Dienst auf **Alpha Ebene** wird unverändert bereitgestellt, wobei alle Fehler auftreten und in keiner Weise unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6370c-107">This **alpha-level** service is provided "as-is", with all faults and is not supported in any way.</span></span> <span data-ttu-id="6370c-108">Jede Datensammlung vom Dienst unterliegt den Daten [Schutzbestimmungen von Microsoft](https://go.microsoft.com/fwlink/?LinkID=824704).</span><span class="sxs-lookup"><span data-stu-id="6370c-108">Any data collection from the service is subject to the [Microsoft privacy statement](https://go.microsoft.com/fwlink/?LinkID=824704).</span></span>
> 
> <span data-ttu-id="6370c-109">Diese Features befinden sich **in der Vorschau Phase und können geändert**werden.</span><span class="sxs-lookup"><span data-stu-id="6370c-109">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="6370c-110">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass wir die benötigten Features bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6370c-110">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

## <a name="how-does-the-service-help-me"></a><span data-ttu-id="6370c-111">Wie unterstützt der Dienst mich?</span><span class="sxs-lookup"><span data-stu-id="6370c-111">How does the service help me?</span></span>

<span data-ttu-id="6370c-112">Nehmen wir an, ich habe nur ein Datenelement, vielleicht auch Finanzdaten, Microsoft Graph Daten, Schema.org Daten oder benutzerdefinierte Daten aus meiner Organisation.</span><span class="sxs-lookup"><span data-stu-id="6370c-112">Let's say I just got a piece of data, maybe it's financial data, Microsoft Graph data, schema.org data, or custom data from within my organization.</span></span> 

<span data-ttu-id="6370c-113">Jetzt möchte ich die Daten für einen Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6370c-113">Now I want to display the data to a user.</span></span> 

<span data-ttu-id="6370c-114">Normalerweise bedeutet dies, dass benutzerdefinierter Benutzeroberflächen Code in allen Front-End-Stapeln geschrieben werden muss, die für Endbenutzer bereitstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6370c-114">Traditionally that means writing custom UI code in all of the front-end stacks that I deliver to end-users.</span></span>

<span data-ttu-id="6370c-115">Was passiert jedoch, wenn meine APP neue Vorlagen für die Benutzeroberfläche basierend auf dem Typ der Daten "erlernen" könnte?</span><span class="sxs-lookup"><span data-stu-id="6370c-115">But what if there were a world where my app could "learn" new UI templates based on the type of data?</span></span> <span data-ttu-id="6370c-116">Eine Welt, in der alle Benutzeroberflächen Vorlagen, in ihren eigenen Projekten, innerhalb einer Organisation oder für das gesamte Internet mitwirken, verbessern und freigeben können.</span><span class="sxs-lookup"><span data-stu-id="6370c-116">A world where anyone could contribute, enhance, and share common UI templates, within their own projects, within an organization, or for the entire internet.</span></span>

## <a name="what-is-the-card-template-service"></a><span data-ttu-id="6370c-117">Was ist der Karten Vorlagen Dienst?</span><span class="sxs-lookup"><span data-stu-id="6370c-117">What is the card template service?</span></span>

<span data-ttu-id="6370c-118">Der Kartendienst für Karten ist ein einfacher Rest-Endpunkt, der Folgendes unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6370c-118">The card template service is a simple REST endpoint that helps:</span></span>

* <span data-ttu-id="6370c-119">**Suchen** Sie eine Vorlage, indem Sie die Struktur Ihrer Daten analysieren.</span><span class="sxs-lookup"><span data-stu-id="6370c-119">**Find** a template by analyzing the structure of your data</span></span>
* <span data-ttu-id="6370c-120">Sie **erhalten** eine Vorlage, sodass Sie Sie direkt auf dem Client binden können, *ohne die Daten an den Server zu senden oder jemals das Gerät zu hinterlassen* .</span><span class="sxs-lookup"><span data-stu-id="6370c-120">**Get** a template so you can bind it directly on the client, *without sending your data to the server or ever leaving the device*</span></span>
* <span data-ttu-id="6370c-121">**Füllen** Sie eine Vorlage auf dem Server auf, wenn die Client seitige Datenbindung nicht geeignet oder nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="6370c-121">**Populate** a template on the server, when client-side data binding isn't appropriate or possible</span></span>

<span data-ttu-id="6370c-122">Dahinter geht es:</span><span class="sxs-lookup"><span data-stu-id="6370c-122">Behind it all, is:</span></span>

* <span data-ttu-id="6370c-123">Ein frei gegebenes Open Source-vorlagenrepository, das von GitHub unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6370c-123">A shared, open-source template repository backed by GitHub.</span></span> <span data-ttu-id="6370c-124">*(Das Repository ist zurzeit privat, wird jedoch als öffentlich festgehalten, sobald einige lose Enden verknüpft sind.)*</span><span class="sxs-lookup"><span data-stu-id="6370c-124">*(The repo is currently private but will be made public as soon as we tie up some loose ends)*</span></span>
* <span data-ttu-id="6370c-125">Alle Vorlagen sind flatjson-Dateien im Repository, die die Bearbeitung, den Beitrag und die gemeinsame Nutzung eines natürlichen Teils eines Entwickler Workflows erleichtern.</span><span class="sxs-lookup"><span data-stu-id="6370c-125">All the templates are flat JSON files in the repo, which makes editing, contributing, and sharing a natural part of a developer workflow.</span></span>
* <span data-ttu-id="6370c-126">Der Code für den Dienst wird zur Verfügung gestellt, sodass Sie überall dort hosten können, wo Sie es am sinnvollsten machen.</span><span class="sxs-lookup"><span data-stu-id="6370c-126">The code for the service will be made available so you can host wherever makes the most sense to you.</span></span> 

## <a name="using-the-service"></a><span data-ttu-id="6370c-127">Verwenden des Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="6370c-127">Using the service</span></span>

### <a name="get-all-templates"></a><span data-ttu-id="6370c-128">Alle Vorlagen erhalten</span><span class="sxs-lookup"><span data-stu-id="6370c-128">Get all templates</span></span> 

<span data-ttu-id="6370c-129">Dieser Endpunkt gibt eine Liste aller bekannten Vorlagen zurück.</span><span class="sxs-lookup"><span data-stu-id="6370c-129">This endpoint returns a list of all known templates.</span></span>

> `HTTP GET https://templates.adaptivecards.io/list`

<span data-ttu-id="6370c-130">**Antwort Auszug**</span><span class="sxs-lookup"><span data-stu-id="6370c-130">**Response excerpt**</span></span>

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

### <a name="find-a-template"></a><span data-ttu-id="6370c-131">Vorlage suchen</span><span class="sxs-lookup"><span data-stu-id="6370c-131">Find a template</span></span>

<span data-ttu-id="6370c-132">Dieser Endpunkt versucht, eine Vorlage zu finden, indem er die Struktur der Daten analysiert.</span><span class="sxs-lookup"><span data-stu-id="6370c-132">This endpoint tries to find a template by analyzing the structure of your data.</span></span>

> `HTTP POST https://templates.adaptivecards.io/find`

#### <a name="example"></a><span data-ttu-id="6370c-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6370c-133">Example</span></span>

<span data-ttu-id="6370c-134">Nehmen wir an, ich klicke einfach auf einen [Microsoft Graph](https://graph.microsoft.com) Endpunkt, um Organisationsdaten zu mir zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6370c-134">Let's say I just hit a [Microsoft Graph](https://graph.microsoft.com) endpoint to get organizational data about me.</span></span>

> `HTTP GET https://graph.microsoft.com/v1.0/me/`

![Screenshot des Graph-Explorers](content/2019-08-01-12-08-13.png)

<span data-ttu-id="6370c-136">Diese API gab **JSON-Daten**zurück, aber wie **zeige ich Sie** Benutzern mit adaptiven Karten?</span><span class="sxs-lookup"><span data-stu-id="6370c-136">That API returned **JSON data**, but how do I **display it** to users using Adaptive Cards?</span></span> 

<span data-ttu-id="6370c-137">Zuerst möchte ich überprüfen, ob für diese Art von Daten eine Vorlage vorhanden ist `/find` `POST body`. daher erstelle ich eine HTTP-Anforderung an den Endpunkt mit meinen Daten im.</span><span class="sxs-lookup"><span data-stu-id="6370c-137">First I want to see if a template exists for this type of data, so I make an HTTP request to the `/find` endpoint with my data in the `POST body`.</span></span>

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

<span data-ttu-id="6370c-138">**Auf**</span><span class="sxs-lookup"><span data-stu-id="6370c-138">**Response:**</span></span>

```json
[
  {
    "templateUrl": "graph.microsoft.com/Profile.json",
    "confidence": 1
  }
]
```

<span data-ttu-id="6370c-139">Der Dienst gibt eine Liste aller übereinstimmenden Vorlagen zusammen mit einem `confidence` -Wert zurück, der angibt, wie nah die Übereinstimmung ist.</span><span class="sxs-lookup"><span data-stu-id="6370c-139">The service returns a list of any matching templates, along with a `confidence` indicating how close the match is.</span></span> <span data-ttu-id="6370c-140">Nun kann ich diese Vorlagen-URL verwenden, um die Vorlage zu **erhalten** , oder Sie kann serverseitig auffüllen.</span><span class="sxs-lookup"><span data-stu-id="6370c-140">Now I can use that template URL to **get** the template, or **populate** it server-side.</span></span>

### <a name="get-a-template"></a><span data-ttu-id="6370c-141">Vorlage erstellen</span><span class="sxs-lookup"><span data-stu-id="6370c-141">Get a template</span></span>

<span data-ttu-id="6370c-142">Eine Vorlage, die von diesem Endpunkt abgerufen wird, kann [mithilfe der templatng-sdche](sdk.md)zur Laufzeit mit Daten aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="6370c-142">A template retrieved from this endpoint can be populated with data at runtime [using the templatng SDKs](sdk.md).</span></span>

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]`

<span data-ttu-id="6370c-143">Sie können auch "Sample Data" in die Vorlage einschließen, sodass die Bearbeitung im Designer benutzerfreundlicher wird:</span><span class="sxs-lookup"><span data-stu-id="6370c-143">You can also include "sample data" with the template, which makes editing in the designer more friendly:</span></span>

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]?sampleData=true`

#### <a name="example"></a><span data-ttu-id="6370c-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6370c-144">Example</span></span>

<span data-ttu-id="6370c-145">Wir holen uns die Microsoft Graph Profil Vorlage, die `/find` oben zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6370c-145">Let's get the Microsoft Graph profile template that was returned from `/find` above.</span></span>

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

<span data-ttu-id="6370c-146">**Antwort Auszug**</span><span class="sxs-lookup"><span data-stu-id="6370c-146">**Response excerpt**</span></span>

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

<span data-ttu-id="6370c-147">Verwenden Sie diese Vorlage jetzt mit den Vorlagen- [sdchen](sdk.md) , um eine fertige Adaptive Karte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6370c-147">Now use this template with the [templating SDKs](sdk.md) to create a ready-to-render Adaptive Card.</span></span>

### <a name="populate-a-template-server-side"></a><span data-ttu-id="6370c-148">Auffüllen einer serverseitigen Vorlage</span><span class="sxs-lookup"><span data-stu-id="6370c-148">Populate a template server-side</span></span>

<span data-ttu-id="6370c-149">In einigen Fällen ist es möglicherweise nicht sinnvoll, eine Vorlage auf dem Client aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="6370c-149">In some cases it may not make sense to populate a template on the client.</span></span>  <span data-ttu-id="6370c-150">In diesen Anwendungsfällen kann der Dienst eine vollständig aufgefüllte Adaptive Karte zurückgeben lassen, die an einen beliebigen adaptiver Karten-Renderer übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6370c-150">For these use cases, you can have the service return a fully-populated Adaptive Card, ready to be passed to any Adaptive Card Renderer.</span></span>

> `HTTP POST https://templates.adaptivecards.io/[TEMPLATE-PATH]`

#### <a name="example"></a><span data-ttu-id="6370c-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6370c-151">Example</span></span>

<span data-ttu-id="6370c-152">Füllen wir nun die Microsoft Graph Profil Vorlage auf, die bei `/find` Verwendung der obigen Daten zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6370c-152">Let's populate the Microsoft Graph profile template that was returned from `/find` using the data above.</span></span>

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

<span data-ttu-id="6370c-153">**Antwort Auszug**</span><span class="sxs-lookup"><span data-stu-id="6370c-153">**Response excerpt**</span></span>

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

<span data-ttu-id="6370c-154">Beachten Sie, dass die Antwort den Text der ersten `TextBlock` `"Megan Bowen"` durch anstelle von `"{name}"`, wie in der `GET` Anforderung, ersetzt hat.</span><span class="sxs-lookup"><span data-stu-id="6370c-154">Notice how the response replaced the text of the first `TextBlock` with `"Megan Bowen"` instead of `"{name}"`, as in the `GET` request.</span></span> <span data-ttu-id="6370c-155">Diese adaptivecard kann nun an jeden adaptiver Karten-Renderer übergeben werden, ohne die Client seitige Vorlage zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="6370c-155">This AdaptiveCard can now be passed to any Adaptive Card renderer without going through client-side templating.</span></span>

## <a name="contributing-templates"></a><span data-ttu-id="6370c-156">Beitragende Vorlagen</span><span class="sxs-lookup"><span data-stu-id="6370c-156">Contributing templates</span></span>

<span data-ttu-id="6370c-157">Der Vorlagen Dienst wird von einem GitHub-Repository unterstützt (das derzeit **Privat**ist), aber wir werden die Quelle öffnen, sobald wir einige lose Enden anbinden.</span><span class="sxs-lookup"><span data-stu-id="6370c-157">The template service is backed by a GitHub repo (which is currently **private**), but we will open source once we tie up some loose ends.</span></span>

<span data-ttu-id="6370c-158">Wir hoffen, dass wir mithilfe von GitHub als Sicherungs Speicher für die Vorlagen den Prozess der Erstellung, Verbesserung und Freigabe von Vorlagen "demokratisieren" können.</span><span class="sxs-lookup"><span data-stu-id="6370c-158">Our hope is that by using GitHub as a backing store for the templates, we can "democratize" the process of authoring, enhancing, and sharing templates.</span></span> <span data-ttu-id="6370c-159">Jeder kann einen Pull Request übermitteln, der eine völlig neue Vorlage enthält, oder vorhandene Verbesserungen an vorhandenen... alles innerhalb des Entwickler freundlichen GitHub-Erlebnisses.</span><span class="sxs-lookup"><span data-stu-id="6370c-159">Anyone can submit a Pull Request that includes an entirely new template, or make enhancements to existing ones... all within the developer-friendly experience of GitHub.</span></span>

## <a name="self-hosting-the-service"></a><span data-ttu-id="6370c-160">Self-Hosting des Diensts</span><span class="sxs-lookup"><span data-stu-id="6370c-160">Self-hosting the service</span></span>

<span data-ttu-id="6370c-161">Nicht alle Datentypen eignen sich für den "zentralen" adaptiven Kartendienst, der unter `https://templates.adaptivecards.io`gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="6370c-161">Not all types of data are appropriate for the "central" Adaptive Cards template service hosted at `https://templates.adaptivecards.io`.</span></span> 

<span data-ttu-id="6370c-162">Wir möchten sicherstellen, dass alle Benutzer den Vorlagen Dienst innerhalb Ihrer Organisation hosten können, sodass der Quellcode verfügbar gemacht wird, und wir vereinfachen die Bereitstellung in Azure oder in Ihrem eigenen Back-End.</span><span class="sxs-lookup"><span data-stu-id="6370c-162">We want to make sure anyone can host the template service within your organization, so the source code will be made available and we'll make it very simple to deploy to Azure or your own back-end.</span></span>

<span data-ttu-id="6370c-163">Weitere Informationen hierzu zu einem späteren Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="6370c-163">More on this at a later date.</span></span>