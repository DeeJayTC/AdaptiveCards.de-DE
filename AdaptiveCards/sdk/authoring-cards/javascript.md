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
# <a name="javascript-sdk-for-creating-cards"></a><span data-ttu-id="62b29-102">JavaScript-SDK zum Erstellen von Karten</span><span class="sxs-lookup"><span data-stu-id="62b29-102">JavaScript SDK for creating cards</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62b29-103">Die für das Serialisieren von JSON-Bibliothek befindet sich noch in Entwicklung und Ihre Milage abweichen.</span><span class="sxs-lookup"><span data-stu-id="62b29-103">The library for serializing JSON is still in development and your milage may vary.</span></span>

<span data-ttu-id="62b29-104">Wie wir unter den ersten Schritten im Abschnitt, eine adaptive Card ist lediglich ein serialisiertes JSON-Objekt ein Objektmodell für die Karte.</span><span class="sxs-lookup"><span data-stu-id="62b29-104">As we described in the getting started section, an adaptive card is nothing more then a serialized json object of a card object model.</span></span>  <span data-ttu-id="62b29-105">Zum Bearbeiten des Objektmodells erleichtern haben wir einige Bibliotheken definiert, die eine stark typisierte Klassenhierarchie, die einfach definieren zu serialisieren/Deserialisieren von Json ist.</span><span class="sxs-lookup"><span data-stu-id="62b29-105">To make it easy to manipulate the object model we have defined some libraries which define a strongly typed class hierarchy that is easy to serialize/deserialize json.</span></span>

<span data-ttu-id="62b29-106">Sie können alle Tools verwenden, die den adaptive Card JSON-Code erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="62b29-106">You can use any tooling that you want to create the adaptive card json.</span></span>

<span data-ttu-id="62b29-107">Die `adaptivecards` Npm-Paket definiert eine Bibliothek für den Umgang mit adaptive Cards in Javascript</span><span class="sxs-lookup"><span data-stu-id="62b29-107">The `adaptivecards` npm package defines a library for working with adaptive cards in javascript</span></span>

## <a name="to-install"></a><span data-ttu-id="62b29-108">So installieren Sie</span><span class="sxs-lookup"><span data-stu-id="62b29-108">To install</span></span>
```console
npm install adaptivecards
```

## <a name="example-creating"></a><span data-ttu-id="62b29-109">Beispiel zu erstellen</span><span class="sxs-lookup"><span data-stu-id="62b29-109">Example creating</span></span> 
<span data-ttu-id="62b29-110">Es gibt Definitionen für Schnittstellen in `schema.d.ts` beschrieben, die die Form des Schemas</span><span class="sxs-lookup"><span data-stu-id="62b29-110">There are interface definitions in `schema.d.ts` which describe the shape of the schema</span></span>

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

<span data-ttu-id="62b29-111">Es gibt auch ein Objektmodell für das Erstellen von Karten.</span><span class="sxs-lookup"><span data-stu-id="62b29-111">There is also an object model for creating cards.</span></span>


```typescript
let card :IAdaptiveCard =  new AdaptiveCard();
card.body.add(new TextBlock() 
{
    text = "hello world"
});
```
