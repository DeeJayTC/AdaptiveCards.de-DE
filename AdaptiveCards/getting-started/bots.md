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
# <a name="adaptive-cards-for-bot-developers"></a>Mit Adaptive Cards für die Bot-Entwickler

Mit Adaptive Cards eignen sich hervorragend für Bots. Damit können Sie eine Karte einmal erstellen und sie reibungslose in mehreren apps wie Microsoft Teams, Ihre eigene Website und mehr zu rendern.

> [!NOTE]
> Skype wird in der aktuellen Vorschauversion nicht unterstützt. Finden Sie unter den [Partnerstatus](../resources/partners.md) Seite für die neueste Version.

## <a name="try-it-out"></a>Legen Sie los.

Klicken Sie auf den folgenden Link und [wenden Sie sich an unser Bot Scuba](http://contososcubademo.azurewebsites.net/). Sagen Sie `I'm looking for scuba` , und sie helfen Ihnen die Reiseroute Scuba Ihre Träume zu buchen.  

Alle Antworten für die Endpunkte des Bots sind mit Adaptive Cards erstellt.

[![Scuba Chat-screenshot](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)

**Code abrufen**: die vollständige [Contoso Scuba Bot Quellcode](https://github.com/matthidinger/ContosoScubaBot
) finden Sie auf GitHub.


## <a name="bot-framework-integration"></a>Bot Framework-Integration

Mit der [Bot Framework](https://dev.botframework.com/) können Sie einem einzelnen Bot, die zum Chatten Sie mit der Benutzer auf "-Kanäle mehrere", z. B. Skype, Microsoft Teams, Facebook Messenger usw. kann schreiben.

## <a name="walkthrough"></a>Exemplarische Vorgehensweise

Es ist ziemlich einfach eine Adaptive Card Ihrem Bot hinzufügen.

### <a name="step-0-start-with-a-basic-message"></a>Dies ist Schritt 0: Beginnen Sie mit einer einfachen Nachricht

Hier ist ein standard-Bot-Framework `message` Nutzlast, die an jeder Kanal übermittelt werden kann und Anzeigetext für den Benutzer.

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a>Schritt 1: Fügen Sie eine Adaptive Card `attachment`

Um einige Vielfältigkeit über nur-Text hinzuzufügen, Bot Framework verfügt über ein Konzept von `attachments`. 

Wir fügen eine Adaptive Card, die benutzerdefinierten Text anzeigt.

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

### <a name="step-2-build-even-richer-cards"></a>Schritt 2: Erstellen Sie noch umfassendere Karten 

Mit Adaptive Cards bietet viel mehr als nur anpassbare Text. 

Sie haben folgende Möglichkeiten: 

* Hinzufügen `Images` auf Ihrer Karte
* Organisieren Sie Ihre Inhalte mit `Containers` und `Columns`
* Fügen Sie mehrere Typen von hinzu. `Actions`
* Sammeln von `Input` von Ihren Benutzern
* Haben Sie eine Karte `show another card`
* [Sehen Sie sich das vollständige Schema-Explorer](http://adaptivecards.io/explorer/)! 

## <a name="platform-sdks"></a>Plattform-SDKs

Wenn Sie Ihren Bot mit .NET- oder Node.js entwickelt wurde, haben wir Bibliotheken, die Erstellung mit Adaptive Cards sogar noch einfacher.

Platform|Installieren|Mehr erfahren
--------|-------|----------
.NET | `Install-Package AdaptiveCards -IncludePrerelease` | [Bot Framework .NET-Dokumentation](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
NodeJS | `npm install adaptivecards` | [Bot Framework NodeJS-Dokumentation](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a>Kanalstatus

Die Bot-Framework können Sie Ihren Bot für mehrere Kanäle zu veröffentlichen. Wir arbeiten mit verschiedenen Kanälen vollständige Unterstützung für mit Adaptive Cards bietet. Finden Sie unter den [Partnerstatus](../resources/partners.md) Seite für die neueste Version.


## <a name="dive-in"></a>Ohne weitere!

Wir haben nur in diesem Tutorial also bitte oberflächlich verschaffen Sie sich einen Blick auf die Links unten, um weitere Möglichkeiten, Ihren Bot mit Adaptive Cards verbessert werden kann.

* [Beispiel-Karten Durchsuchen](http://adaptivecards.io/samples/) inspirieren
* Verwenden der [Schema-Explorer](http://adaptivecards.io/explorer) um die verfügbaren Elemente zu erfahren.
* Erstellen einer Karte mit den [interaktive Schnellansicht](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)
* [Kontakt aufnehmen](http://adaptivecards.io/connect) mit Sie haben Feedback
