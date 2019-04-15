---
title: Mit Adaptive Cards für die Bot-Entwickler
author: matthidinger
ms.author: mahiding
ms.date: 05/30/2018
ms.topic: article
ms.openlocfilehash: 1acc30c0347ea5527de2af1fe74e605c7589cbc6
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553282"
---
# <a name="adaptive-cards-for-bot-developers"></a><span data-ttu-id="e048f-102">Mit Adaptive Cards für die Bot-Entwickler</span><span class="sxs-lookup"><span data-stu-id="e048f-102">Adaptive Cards for Bot Developers</span></span>

<span data-ttu-id="e048f-103">Mit Adaptive Cards eignen sich hervorragend für Bots.</span><span class="sxs-lookup"><span data-stu-id="e048f-103">Adaptive Cards are a great fit for Bots.</span></span> <span data-ttu-id="e048f-104">Damit können Sie eine Karte einmal erstellen und sie reibungslose in mehreren apps wie Microsoft Teams, Ihre eigene Website und mehr zu rendern.</span><span class="sxs-lookup"><span data-stu-id="e048f-104">They let you author a card once and have it render beautifully inside multiple apps, like  Microsoft Teams, your own website, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="e048f-105">Skype wird in der aktuellen Vorschauversion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e048f-105">Skype is not supported in the current preview.</span></span> <span data-ttu-id="e048f-106">Finden Sie unter den [Partnerstatus](../resources/partners.md) Seite für die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="e048f-106">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>

## <a name="try-it-out"></a><span data-ttu-id="e048f-107">Legen Sie los.</span><span class="sxs-lookup"><span data-stu-id="e048f-107">Try it out</span></span>

<span data-ttu-id="e048f-108">Klicken Sie auf den folgenden Link und [wenden Sie sich an unser Bot Scuba](http://contososcubademo.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="e048f-108">Click the following link and [talk to our Scuba Bot](http://contososcubademo.azurewebsites.net/).</span></span> <span data-ttu-id="e048f-109">Sagen Sie `I'm looking for scuba` , und sie helfen Ihnen die Reiseroute Scuba Ihre Träume zu buchen.</span><span class="sxs-lookup"><span data-stu-id="e048f-109">Say `I'm looking for scuba` and it'll help you book the scuba trip of your dreams.</span></span>  

<span data-ttu-id="e048f-110">Alle Antworten für die Endpunkte des Bots sind mit Adaptive Cards erstellt.</span><span class="sxs-lookup"><span data-stu-id="e048f-110">All of the bot's responses are created with Adaptive Cards.</span></span>

<span data-ttu-id="e048f-111">[![Scuba Chat-screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="e048f-111">[![Scuba chat screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span></span>

<span data-ttu-id="e048f-112">**Code abrufen**: die vollständige [Contoso Scuba Bot Quellcode](https://github.com/matthidinger/ContosoScubaBot
) finden Sie auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="e048f-112">**Get the code**: the full [Contoso Scuba Bot source code](https://github.com/matthidinger/ContosoScubaBot
) can be found on GitHub.</span></span>


## <a name="bot-framework-integration"></a><span data-ttu-id="e048f-113">Bot Framework-Integration</span><span class="sxs-lookup"><span data-stu-id="e048f-113">Bot Framework Integration</span></span>

<span data-ttu-id="e048f-114">Mit der [Bot Framework](https://dev.botframework.com/) können Sie einem einzelnen Bot, die zum Chatten Sie mit der Benutzer auf "-Kanäle mehrere", z. B. Skype, Microsoft Teams, Facebook Messenger usw. kann schreiben.</span><span class="sxs-lookup"><span data-stu-id="e048f-114">With the [Bot Framework](https://dev.botframework.com/) you can write a single bot that is able to chat with users across multiple "channels", like Skype, Microsoft Teams, Facebook Messenger, etc.</span></span>

## <a name="walkthrough"></a><span data-ttu-id="e048f-115">Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="e048f-115">Walkthrough</span></span>

<span data-ttu-id="e048f-116">Es ist ziemlich einfach eine Adaptive Card Ihrem Bot hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e048f-116">It's pretty straight forward to add an Adaptive Card to your bot.</span></span>

### <a name="step-0-start-with-a-basic-message"></a><span data-ttu-id="e048f-117">Dies ist Schritt 0: Beginnen Sie mit einer einfachen Nachricht</span><span class="sxs-lookup"><span data-stu-id="e048f-117">Step 0: Start with a basic message</span></span>

<span data-ttu-id="e048f-118">Hier ist ein standard-Bot-Framework `message` Nutzlast, die an jeder Kanal übermittelt werden kann und Anzeigetext für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e048f-118">Here's a standard Bot Framework `message` payload that can be delivered to any channel and display text to the user.</span></span>

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a><span data-ttu-id="e048f-119">Schritt 1: Fügen Sie eine Adaptive Card `attachment`</span><span class="sxs-lookup"><span data-stu-id="e048f-119">Step 1: Add an Adaptive Card `attachment`</span></span>

<span data-ttu-id="e048f-120">Um einige Vielfältigkeit über nur-Text hinzuzufügen, Bot Framework verfügt über ein Konzept von `attachments`.</span><span class="sxs-lookup"><span data-stu-id="e048f-120">To add some richness beyond just text, the Bot Framework has a concept of `attachments`.</span></span> 

<span data-ttu-id="e048f-121">Wir fügen eine Adaptive Card, die benutzerdefinierten Text anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e048f-121">Let's attach an Adaptive Card that displays custom text.</span></span>

![Grundlegende adaptive card](media/bots/hello-adaptivecards.png)

```json
{
  "type": "message",
  "text": "Plain text is ok, but sometimes I long for more...",
  "attachments": [
    {
      "contentType": "application/vnd.microsoft.card.adaptive",
      "content": {
        "type": "AdaptiveCard",
        "version": "1.0",
        "body": [
          {
            "type": "TextBlock",
            "text": "Hello World!",
            "size": "large"
          },
          {
            "type": "TextBlock",
            "text": "*Sincerely yours,*"
          },
          {
            "type": "TextBlock",
            "text": "Adaptive Cards",
            "separation": "none"
          }
        ],
        "actions": [
          {
            "type": "Action.OpenUrl",
            "url": "http://adaptivecards.io",
            "title": "Learn More"
          }
        ]
      }
    }
  ]
}
```

### <a name="step-2-build-even-richer-cards"></a><span data-ttu-id="e048f-123">Schritt 2: Erstellen Sie noch umfassendere Karten</span><span class="sxs-lookup"><span data-stu-id="e048f-123">Step 2: Build even richer cards</span></span> 

<span data-ttu-id="e048f-124">Mit Adaptive Cards bietet viel mehr als nur anpassbare Text.</span><span class="sxs-lookup"><span data-stu-id="e048f-124">Adaptive Cards offer much more than just customizable text.</span></span> 

<span data-ttu-id="e048f-125">Sie haben folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="e048f-125">You can:</span></span> 

* <span data-ttu-id="e048f-126">Hinzufügen `Images` auf Ihrer Karte</span><span class="sxs-lookup"><span data-stu-id="e048f-126">Add `Images` to your card</span></span>
* <span data-ttu-id="e048f-127">Organisieren Sie Ihre Inhalte mit `Containers` und `Columns`</span><span class="sxs-lookup"><span data-stu-id="e048f-127">Organize your content with `Containers` and `Columns`</span></span>
* <span data-ttu-id="e048f-128">Fügen Sie mehrere Typen von hinzu. `Actions`</span><span class="sxs-lookup"><span data-stu-id="e048f-128">Add multiple types of `Actions`</span></span>
* <span data-ttu-id="e048f-129">Sammeln von `Input` von Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="e048f-129">Collect `Input` from your users</span></span>
* <span data-ttu-id="e048f-130">Haben Sie eine Karte `show another card`</span><span class="sxs-lookup"><span data-stu-id="e048f-130">Have one card `show another card`</span></span>
* <span data-ttu-id="e048f-131">[Sehen Sie sich das vollständige Schema-Explorer](http://adaptivecards.io/explorer/)!</span><span class="sxs-lookup"><span data-stu-id="e048f-131">[Check out the full schema explorer](http://adaptivecards.io/explorer/)!</span></span> 

## <a name="platform-sdks"></a><span data-ttu-id="e048f-132">Plattform-SDKs</span><span class="sxs-lookup"><span data-stu-id="e048f-132">Platform SDKs</span></span>

<span data-ttu-id="e048f-133">Wenn Sie Ihren Bot mit .NET- oder Node.js entwickelt wurde, haben wir Bibliotheken, die Erstellung mit Adaptive Cards sogar noch einfacher.</span><span class="sxs-lookup"><span data-stu-id="e048f-133">If your bot is developed using .NET or NodeJS we have libraries to make building Adaptive Cards even easier.</span></span>

<span data-ttu-id="e048f-134">Platform</span><span class="sxs-lookup"><span data-stu-id="e048f-134">Platform</span></span>|<span data-ttu-id="e048f-135">Installieren</span><span class="sxs-lookup"><span data-stu-id="e048f-135">Install</span></span>|<span data-ttu-id="e048f-136">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="e048f-136">Learn more</span></span>
--------|-------|----------
<span data-ttu-id="e048f-137">.NET</span><span class="sxs-lookup"><span data-stu-id="e048f-137">.NET</span></span> | `Install-Package AdaptiveCards -IncludePrerelease` | [<span data-ttu-id="e048f-138">Bot Framework .NET-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="e048f-138">Bot Framework .NET Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
<span data-ttu-id="e048f-139">NodeJS</span><span class="sxs-lookup"><span data-stu-id="e048f-139">NodeJS</span></span> | `npm install adaptivecards` | [<span data-ttu-id="e048f-140">Bot Framework NodeJS-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="e048f-140">Bot Framework NodeJS Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a><span data-ttu-id="e048f-141">Kanalstatus</span><span class="sxs-lookup"><span data-stu-id="e048f-141">Channel status</span></span>

<span data-ttu-id="e048f-142">Die Bot-Framework können Sie Ihren Bot für mehrere Kanäle zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e048f-142">The Bot Framework lets you publish your bot to multiple channels.</span></span> <span data-ttu-id="e048f-143">Wir arbeiten mit verschiedenen Kanälen vollständige Unterstützung für mit Adaptive Cards bietet.</span><span class="sxs-lookup"><span data-stu-id="e048f-143">We're working with various channels to provide full support for Adaptive Cards.</span></span> <span data-ttu-id="e048f-144">Finden Sie unter den [Partnerstatus](../resources/partners.md) Seite für die neueste Version.</span><span class="sxs-lookup"><span data-stu-id="e048f-144">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>


## <a name="dive-in"></a><span data-ttu-id="e048f-145">Ohne weitere!</span><span class="sxs-lookup"><span data-stu-id="e048f-145">Dive in!</span></span>

<span data-ttu-id="e048f-146">Wir haben nur in diesem Tutorial also bitte oberflächlich verschaffen Sie sich einen Blick auf die Links unten, um weitere Möglichkeiten, Ihren Bot mit Adaptive Cards verbessert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e048f-146">We've just scratched the surface in this tutorial, so please take a look at the links below to explore more ways that Adaptive Cards can enhance your bot.</span></span>

* <span data-ttu-id="e048f-147">[Beispiel-Karten Durchsuchen](http://adaptivecards.io/samples/) inspirieren</span><span class="sxs-lookup"><span data-stu-id="e048f-147">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="e048f-148">Verwenden der [Schema-Explorer](http://adaptivecards.io/explorer) um die verfügbaren Elemente zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="e048f-148">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="e048f-149">Erstellen einer Karte mit den [interaktive Schnellansicht](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span><span class="sxs-lookup"><span data-stu-id="e048f-149">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="e048f-150">[Kontakt aufnehmen](http://adaptivecards.io/connect) mit Sie haben Feedback</span><span class="sxs-lookup"><span data-stu-id="e048f-150">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
