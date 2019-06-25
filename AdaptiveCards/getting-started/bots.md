---
title: Adaptive Karten für Bot-Entwickler
author: matthidinger
ms.author: mahiding
ms.date: 05/30/2018
ms.topic: article
ms.openlocfilehash: 1acc30c0347ea5527de2af1fe74e605c7589cbc6
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "59553282"
---
# <a name="adaptive-cards-for-bot-developers"></a><span data-ttu-id="f0c6b-102">Adaptive Karten für Bot-Entwickler</span><span class="sxs-lookup"><span data-stu-id="f0c6b-102">Adaptive Cards for Bot Developers</span></span>

<span data-ttu-id="f0c6b-103">Adaptive Karten eignen sich hervorragend für Bots.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-103">Adaptive Cards are a great fit for Bots.</span></span> <span data-ttu-id="f0c6b-104">Damit kannst du eine Karte einmal erstellen und sie reibungslos in mehreren Apps wie Microsoft Teams, deiner eigenen Website usw. rendern.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-104">They let you author a card once and have it render beautifully inside multiple apps, like  Microsoft Teams, your own website, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="f0c6b-105">Skype wird in der aktuellen Vorschauversion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-105">Skype is not supported in the current preview.</span></span> <span data-ttu-id="f0c6b-106">Aktuelle Informationen findest du auf der Seite [Partner](../resources/partners.md).</span><span class="sxs-lookup"><span data-stu-id="f0c6b-106">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>

## <a name="try-it-out"></a><span data-ttu-id="f0c6b-107">Jetzt testen</span><span class="sxs-lookup"><span data-stu-id="f0c6b-107">Try it out</span></span>

<span data-ttu-id="f0c6b-108">Klicke auf den folgenden Link und [sprich mit unserem Scuba-Bot](http://contososcubademo.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="f0c6b-108">Click the following link and [talk to our Scuba Bot](http://contososcubademo.azurewebsites.net/).</span></span> <span data-ttu-id="f0c6b-109">Sage `I'm looking for scuba`, und er hilft dir dabei, den Tauchurlaub deines Lebens zu buchen.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-109">Say `I'm looking for scuba` and it'll help you book the scuba trip of your dreams.</span></span>  

<span data-ttu-id="f0c6b-110">Alle Antworten des Bots wurden mit adaptiven Karten erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-110">All of the bot's responses are created with Adaptive Cards.</span></span>

<span data-ttu-id="f0c6b-111">[![Screenshot: Scuba-Chat](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span><span class="sxs-lookup"><span data-stu-id="f0c6b-111">[![Scuba chat screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)</span></span>

<span data-ttu-id="f0c6b-112">**Code abrufen**: Den vollständigen [Contoso Scuba Bot-Quellcode](https://github.com/matthidinger/ContosoScubaBot
) findest du auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-112">**Get the code**: the full [Contoso Scuba Bot source code](https://github.com/matthidinger/ContosoScubaBot
) can be found on GitHub.</span></span>


## <a name="bot-framework-integration"></a><span data-ttu-id="f0c6b-113">Bot Framework-Integration</span><span class="sxs-lookup"><span data-stu-id="f0c6b-113">Bot Framework Integration</span></span>

<span data-ttu-id="f0c6b-114">Mit dem [Bot Framework](https://dev.botframework.com/) kannst du einem einzelnen Bot schreiben, der mit Benutzern über mehrere „Kanäle“ wie Skype, Microsoft Teams, Facebook Messenger usw. chatten kann.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-114">With the [Bot Framework](https://dev.botframework.com/) you can write a single bot that is able to chat with users across multiple "channels", like Skype, Microsoft Teams, Facebook Messenger, etc.</span></span>

## <a name="walkthrough"></a><span data-ttu-id="f0c6b-115">Exemplarische Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="f0c6b-115">Walkthrough</span></span>

<span data-ttu-id="f0c6b-116">Es ist recht einfach, eine adaptive Karte zu deinem Bot hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-116">It's pretty straight forward to add an Adaptive Card to your bot.</span></span>

### <a name="step-0-start-with-a-basic-message"></a><span data-ttu-id="f0c6b-117">Schritt 0: Beginne mit einer einfachen Nachricht</span><span class="sxs-lookup"><span data-stu-id="f0c6b-117">Step 0: Start with a basic message</span></span>

<span data-ttu-id="f0c6b-118">Dies ist eine `message`-Standardnutzlast von Bot Framework, die für jeden Kanal bereitgestellt werden kann und dem Benutzer Text anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-118">Here's a standard Bot Framework `message` payload that can be delivered to any channel and display text to the user.</span></span>

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a><span data-ttu-id="f0c6b-119">Schritt 1: Füge ein `attachment`-Element für die adaptive Karte hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-119">Step 1: Add an Adaptive Card `attachment`</span></span>

<span data-ttu-id="f0c6b-120">Damit nicht nur Text eingefügt wird, verfügt das Bot Framework über das Konzept von `attachments`.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-120">To add some richness beyond just text, the Bot Framework has a concept of `attachments`.</span></span> 

<span data-ttu-id="f0c6b-121">Im Folgenden fügen wir eine adaptive Karte hinzu, die benutzerdefinierten Text anzeigt.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-121">Let's attach an Adaptive Card that displays custom text.</span></span>

![Grundlegende adaptive Karte](media/bots/hello-adaptivecards.png)

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

### <a name="step-2-build-even-richer-cards"></a><span data-ttu-id="f0c6b-123">Schritt 2: Erstelle noch umfassendere Karten.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-123">Step 2: Build even richer cards</span></span> 

<span data-ttu-id="f0c6b-124">Adaptive Karten bieten viel mehr als nur anpassbaren Text.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-124">Adaptive Cards offer much more than just customizable text.</span></span> 

<span data-ttu-id="f0c6b-125">Du hast folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f0c6b-125">You can:</span></span> 

* <span data-ttu-id="f0c6b-126">Füge `Images` zu deiner Karte hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-126">Add `Images` to your card</span></span>
* <span data-ttu-id="f0c6b-127">Organisiere deine Inhalte mit `Containers` und `Columns`.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-127">Organize your content with `Containers` and `Columns`</span></span>
* <span data-ttu-id="f0c6b-128">Füge mehrere Typen von `Actions` hinzu.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-128">Add multiple types of `Actions`</span></span>
* <span data-ttu-id="f0c6b-129">Erfasse `Input` von deinen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-129">Collect `Input` from your users</span></span>
* <span data-ttu-id="f0c6b-130">Lass eine Karte eine andere anzeigen (`show another card`).</span><span class="sxs-lookup"><span data-stu-id="f0c6b-130">Have one card `show another card`</span></span>
* <span data-ttu-id="f0c6b-131">[Sieh dir den vollständigen Schema-Explorer an!](http://adaptivecards.io/explorer/)</span><span class="sxs-lookup"><span data-stu-id="f0c6b-131">[Check out the full schema explorer](http://adaptivecards.io/explorer/)!</span></span> 

## <a name="platform-sdks"></a><span data-ttu-id="f0c6b-132">Plattform-SDKs</span><span class="sxs-lookup"><span data-stu-id="f0c6b-132">Platform SDKs</span></span>

<span data-ttu-id="f0c6b-133">Wenn dein Bot mit .NET oder NodeJS entwickelt wurde, haben wir Bibliotheken, die das Erstellen adaptiver Karten noch einfacher macht.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-133">If your bot is developed using .NET or NodeJS we have libraries to make building Adaptive Cards even easier.</span></span>

<span data-ttu-id="f0c6b-134">Plattform</span><span class="sxs-lookup"><span data-stu-id="f0c6b-134">Platform</span></span>|<span data-ttu-id="f0c6b-135">Installieren</span><span class="sxs-lookup"><span data-stu-id="f0c6b-135">Install</span></span>|<span data-ttu-id="f0c6b-136">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="f0c6b-136">Learn more</span></span>
--------|-------|----------
<span data-ttu-id="f0c6b-137">.NET</span><span class="sxs-lookup"><span data-stu-id="f0c6b-137">.NET</span></span> | `Install-Package AdaptiveCards -IncludePrerelease` | [<span data-ttu-id="f0c6b-138">Bot Framework-Dokumentation für .NET</span><span class="sxs-lookup"><span data-stu-id="f0c6b-138">Bot Framework .NET Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
<span data-ttu-id="f0c6b-139">NodeJS</span><span class="sxs-lookup"><span data-stu-id="f0c6b-139">NodeJS</span></span> | `npm install adaptivecards` | [<span data-ttu-id="f0c6b-140">Bot Framework-Dokumentation für NodeJS</span><span class="sxs-lookup"><span data-stu-id="f0c6b-140">Bot Framework NodeJS Docs</span></span>](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a><span data-ttu-id="f0c6b-141">Kanalstatus</span><span class="sxs-lookup"><span data-stu-id="f0c6b-141">Channel status</span></span>

<span data-ttu-id="f0c6b-142">Bot Framework ermöglicht es dir, deinen Bot für mehrere Kanäle zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-142">The Bot Framework lets you publish your bot to multiple channels.</span></span> <span data-ttu-id="f0c6b-143">Wir arbeiten mit verschiedenen Kanälen, um vollständige Unterstützung für adaptive Karten zu bieten.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-143">We're working with various channels to provide full support for Adaptive Cards.</span></span> <span data-ttu-id="f0c6b-144">Aktuelle Informationen findest du auf der Seite [Partner](../resources/partners.md).</span><span class="sxs-lookup"><span data-stu-id="f0c6b-144">See the [Partner Status](../resources/partners.md) page for the latest.</span></span>


## <a name="dive-in"></a><span data-ttu-id="f0c6b-145">Jetzt eintauchen</span><span class="sxs-lookup"><span data-stu-id="f0c6b-145">Dive in!</span></span>

<span data-ttu-id="f0c6b-146">In diesem Tutorial haben wir das Thema nur oberflächlich behandelt. Sieh dir daher die folgenden Links an, um mehr darüber zu erfahren, wie adaptive Karten deinen Bot optimieren können.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-146">We've just scratched the surface in this tutorial, so please take a look at the links below to explore more ways that Adaptive Cards can enhance your bot.</span></span>

* <span data-ttu-id="f0c6b-147">Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-147">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="f0c6b-148">Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer).</span><span class="sxs-lookup"><span data-stu-id="f0c6b-148">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="f0c6b-149">Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype).</span><span class="sxs-lookup"><span data-stu-id="f0c6b-149">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="f0c6b-150">[Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.</span><span class="sxs-lookup"><span data-stu-id="f0c6b-150">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
