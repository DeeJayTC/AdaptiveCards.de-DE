---
title: JavaScript-SDKS für mit Adaptive Cards
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 6372f2f23a817ecc4d07d950d6513d14357547b7
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552662"
---
# <a name="javascript-sdk-for-creating-cards"></a>JavaScript-SDK zum Erstellen von Karten

> [!IMPORTANT]
> Die für das Serialisieren von JSON-Bibliothek befindet sich noch in Entwicklung und Ihre Milage abweichen.

Wie wir unter den ersten Schritten im Abschnitt, eine adaptive Card ist lediglich ein serialisiertes JSON-Objekt ein Objektmodell für die Karte.  Zum Bearbeiten des Objektmodells erleichtern haben wir einige Bibliotheken definiert, die eine stark typisierte Klassenhierarchie, die einfach definieren zu serialisieren/Deserialisieren von Json ist.

Sie können alle Tools verwenden, die den adaptive Card JSON-Code erstellt werden soll.

Die `adaptivecards` Npm-Paket definiert eine Bibliothek für den Umgang mit adaptive Cards in Javascript

## <a name="to-install"></a>So installieren Sie
```console
npm install adaptivecards
```

## <a name="example-creating"></a>Beispiel zu erstellen 
Es gibt Definitionen für Schnittstellen in `schema.d.ts` beschrieben, die die Form des Schemas

```typescript
let card = {
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "Container",
            "items": [
                {
                    "type": "TextBlock",
                    "text": "Meow!"
                },
                {
                    "type": "Image",
                    "url": "http://adaptivecards.io/content/cats/1.png"
                }
            ]
        }
    ]
};
```

Es gibt auch ein Objektmodell für das Erstellen von Karten.


```typescript
let card :IAdaptiveCard =  new AdaptiveCard();
card.body.add(new TextBlock() 
{
    text = "hello world"
});
```
