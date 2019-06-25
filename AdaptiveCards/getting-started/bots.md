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
# <a name="adaptive-cards-for-bot-developers"></a>Adaptive Karten für Bot-Entwickler

Adaptive Karten eignen sich hervorragend für Bots. Damit kannst du eine Karte einmal erstellen und sie reibungslos in mehreren Apps wie Microsoft Teams, deiner eigenen Website usw. rendern.

> [!NOTE]
> Skype wird in der aktuellen Vorschauversion nicht unterstützt. Aktuelle Informationen findest du auf der Seite [Partner](../resources/partners.md).

## <a name="try-it-out"></a>Jetzt testen

Klicke auf den folgenden Link und [sprich mit unserem Scuba-Bot](http://contososcubademo.azurewebsites.net/). Sage `I'm looking for scuba`, und er hilft dir dabei, den Tauchurlaub deines Lebens zu buchen.  

Alle Antworten des Bots wurden mit adaptiven Karten erstellt.

[![Screenshot: Scuba-Chat](media/bots/scuba-chat.png)](http://contososcubademo.azurewebsites.net/)

**Code abrufen**: Den vollständigen [Contoso Scuba Bot-Quellcode](https://github.com/matthidinger/ContosoScubaBot
) findest du auf GitHub.


## <a name="bot-framework-integration"></a>Bot Framework-Integration

Mit dem [Bot Framework](https://dev.botframework.com/) kannst du einem einzelnen Bot schreiben, der mit Benutzern über mehrere „Kanäle“ wie Skype, Microsoft Teams, Facebook Messenger usw. chatten kann.

## <a name="walkthrough"></a>Exemplarische Vorgehensweise

Es ist recht einfach, eine adaptive Karte zu deinem Bot hinzuzufügen.

### <a name="step-0-start-with-a-basic-message"></a>Schritt 0: Beginne mit einer einfachen Nachricht

Dies ist eine `message`-Standardnutzlast von Bot Framework, die für jeden Kanal bereitgestellt werden kann und dem Benutzer Text anzeigt.

```json
{
   "type": "message",
   "text": "Plain text is ok, but sometimes I long for more..."
}
```

### <a name="step-1-add-an-adaptive-card-attachment"></a>Schritt 1: Füge ein `attachment`-Element für die adaptive Karte hinzu.

Damit nicht nur Text eingefügt wird, verfügt das Bot Framework über das Konzept von `attachments`. 

Im Folgenden fügen wir eine adaptive Karte hinzu, die benutzerdefinierten Text anzeigt.

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

### <a name="step-2-build-even-richer-cards"></a>Schritt 2: Erstelle noch umfassendere Karten. 

Adaptive Karten bieten viel mehr als nur anpassbaren Text. 

Du hast folgende Möglichkeiten: 

* Füge `Images` zu deiner Karte hinzu.
* Organisiere deine Inhalte mit `Containers` und `Columns`.
* Füge mehrere Typen von `Actions` hinzu.
* Erfasse `Input` von deinen Benutzern.
* Lass eine Karte eine andere anzeigen (`show another card`).
* [Sieh dir den vollständigen Schema-Explorer an!](http://adaptivecards.io/explorer/) 

## <a name="platform-sdks"></a>Plattform-SDKs

Wenn dein Bot mit .NET oder NodeJS entwickelt wurde, haben wir Bibliotheken, die das Erstellen adaptiver Karten noch einfacher macht.

Plattform|Installieren|Mehr erfahren
--------|-------|----------
.NET | `Install-Package AdaptiveCards -IncludePrerelease` | [Bot Framework-Dokumentation für .NET](https://docs.microsoft.com/en-us/bot-framework/dotnet/bot-builder-dotnet-add-rich-card-attachments)
NodeJS | `npm install adaptivecards` | [Bot Framework-Dokumentation für NodeJS](https://docs.microsoft.com/en-us/bot-framework/nodejs/bot-builder-nodejs-send-rich-cards)


## <a name="channel-status"></a>Kanalstatus

Bot Framework ermöglicht es dir, deinen Bot für mehrere Kanäle zu veröffentlichen. Wir arbeiten mit verschiedenen Kanälen, um vollständige Unterstützung für adaptive Karten zu bieten. Aktuelle Informationen findest du auf der Seite [Partner](../resources/partners.md).


## <a name="dive-in"></a>Jetzt eintauchen

In diesem Tutorial haben wir das Thema nur oberflächlich behandelt. Sieh dir daher die folgenden Links an, um mehr darüber zu erfahren, wie adaptive Karten deinen Bot optimieren können.

* Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.
* Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer).
* Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype).
* [Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.
