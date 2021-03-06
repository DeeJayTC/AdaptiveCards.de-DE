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
# <a name="adaptive-cards-templating"></a>Vorlagen für adaptive Karten

Wir freuen uns, Ihnen eine Vorschau neuer Tools zur Verfügung zu stellen ,mit denen Sie adaptive Karten **erstellen**, **wiederverwenden** und **freigeben** können. 

> [!IMPORTANT] 
> 
> **Breaking Changes** im **Release Candidate von Mai 2020**
>
> Der Release Candidate für Vorlagen enthält einige kleinere, nicht abwärtskompatible Änderungen, die Sie kennen sollten, wenn Sie die älteren Pakete verwendet haben. Einzelheiten finden Sie unten.


## <a name="breaking-changes-as-of-may-2020"></a>Breaking Changes Stand Mai 2020

1. Die Bindungssyntax wurde von `{...}` in `${...}` geändert. 
    * Beispiel: Aus `"text": "Hello {name}"` wird `"text": "Hello ${name}"`.
2. Die JavaScript-API enthält kein `EvaluationContext`-Objekt mehr. Übergeben Sie Ihre Daten einfach an die `expand`-Funktion. Ausführliche Informationen finden Sie auf der [SDK-Seite](sdk.md).
3. Die .NET-API wurde umgestaltet, damit sie der JavaScript-API besser entspricht. Ausführliche Informationen finden Sie auf der [SDK-Seite](sdk.md).

## <a name="how-can-templating-help-you"></a>So können Vorlagen Ihnen helfen

Durch Vorlagen wird die Trennung von **Daten** aus dem **Layout** in einer adaptiven Karte ermöglicht. 

### <a name="it-helps-design-a-card-once-and-then-populate-it-with-real-data"></a>Dadurch können Karten einmalig erstellt und mit echten Daten aufgefüllt werden.

Derzeit ist es nicht möglich, eine Karte mit dem [Adaptive Card Designer](https://adaptivecards.io/designer) (Designer für adaptive Karten) zu erstellen und mithilfe dieses JSON-Codes die Nutzlast mit **dynamischem Inhalt** aufzufüllen. Zu diesem Zweck müssen Sie benutzerdefinierten Code schreiben, um eine JSON-Zeichenfolge zu erstellen, oder die Objektmodell-SDKs verwenden, um ein Objektmodell zu erstellen, das Ihre Karte darstellt, und es zu JSON serialisieren. In beiden Fällen erfolgt im Designer ein einmaliger unidirektionaler Vorgang, der es nicht einfach macht, den Kartenentwurf später zu optimieren, nachdem Sie ihn in Code umgewandelt haben.

### <a name="it-makes-transmissions-over-the-wire-smaller"></a>Die Menge der über das Netzwerk übertragenen Daten wird dadurch kleiner.

Stellen Sie sich eine Welt vor, in der eine Vorlage und Daten **direkt auf dem Client** kombiniert werden können. Das bedeutet, dass wenn Sie dieselbe Vorlage mehrmals verwenden oder sie mit neuen Daten aktualisieren möchten, Sie nur neue Daten an das Gerät senden müssen und es die gleiche Vorlage immer wieder verwenden kann.

### <a name="it-helps-you-create-a-great-looking-card-from-just-the-data-you-provide"></a>Dies hilft Ihnen, eine ansprechende Karte nur anhand der von Ihnen bereitgestellten Daten zu erstellen.

Wir denken, dass adaptive Karten großartig sind. Aber was wäre, wenn Sie nicht eine adaptive Karte für alles schreiben müssten, was Sie einem Benutzer zeigen möchten? Mit einem (nachstehend beschriebenen) Vorlagendienst können wir eine Lösung schaffen, in der jeder Vorlagen für jede Art von Daten beitragen, finden und freigeben kann. 

Geben Sie sie in ihren eigenen Projekten, in Ihrer Organisation oder im gesamten Internet frei.

### <a name="ai-and-other-services-could-improve-user-experiences"></a>Künstliche Intelligenz (KI) und andere Dienste können die Benutzerfreundlichkeit verbessern

Durch das Trennen von Daten und Inhalten öffnet sich für KI und andere Dienste eine Tür zur „vernünftigen“ Einschätzung der Daten in den Karten, die wir sehen, und zur Verbesserung der Benutzerproduktivität oder zum schnelleren Finden von Dingen.

## <a name="what-is-adaptive-cards-templating"></a>Was sind Vorlagen für adaptive Karten?

Die Lösung besteht aus drei Hauptkomponenten:

1. Die **[Vorlagensprache](language.md)** ist die Syntax, die zum Erstellen einer Vorlage verwendet wird. Mit dem Designer können Sie sogar eine Vorschau Ihrer Vorlagen zur Entwurfszeit anzeigen, indem Sie „Beispieldaten“ einfügen.
2. Die **[Vorlagen-SDKs](sdk.md)** sind auf allen unterstützten Plattformen für adaptive Karten vorhanden. Mit diesen SDKs können Sie eine Vorlage mit echten Daten auffüllen, entweder im Back-End oder direkt auf dem Client. 
3. Der **[Vorlagendienst](service.md)** ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.

## <a name="template-language"></a>Vorlagensprache

Die Vorlagensprache ist die Syntax, die zum Erstellen einer Vorlage einer adaptiven Karte verwendet wird. 

> [!NOTE]
> 
> Führen Sie das folgende Beispiel aus, um hier eine neue Registerkarte zu öffnen
>
> **https://adaptivecards.io/designer**
> 
> Klicken Sie auf die Schaltfläche **Preview Mode** (Vorschaumodus), um zwischen Entwurfs- und Vorschaumodus zu wechseln.

![Screenshot des Designers](content/2019-08-01-13-58-27.png)

Der neu aktualisierte Designer fügt Unterstützung für das Erstellen von Vorlagen und das Bereitstellen von **Beispieldaten** für die Vorschau der Karte zur Entwurfszeit hinzu.

Fügen Sie das folgende Beispiel in den Bereich **Card Payload Editor** (Editor für die Kartennutzlast) ein: 

**EmployeeCardTemplate.json**

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

Fügen Sie dann die folgenden JSON-Daten in den **Sample Data Editor** (Beispieldaten-Editor) ein. 

Mithilfe von **Beispieldaten** können Sie genau sehen, wie Ihre Karte zur Laufzeit aussieht, nachdem Sie echte Daten an sie übergeben haben.

**EmployeeData**

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

Klicken Sie auf die Schaltfläche **Preview Mode** (Vorschaumodus). Die Karte sollte entsprechend den oben angegebenen Beispieldaten gerendert werden. Zögern Sie nicht, Änderungen an den Beispieldaten vorzunehmen, und beobachten Sie die Aktualisierung der Karte in Echtzeit.

**Herzlichen Glückwunsch**. Sie haben soeben Ihre erste Vorlage erstellt! Als Nächstes erfahren Sie, wie Sie die Vorlage mit echten Daten auffüllen.

> Weitere Informationen zur [Vorlagensprache](language.md)

## <a name="sdk-support"></a>SDK-Unterstützung

Die Vorlagen-SDKs ermöglichen es, eine Vorlage mit echten Daten aufzufüllen.

> [!NOTE]
>
> Zum gegenwärtigen Zeitpunkt sind Vorlagen-SDKs für .NET und NodeJS erhältlich. Im Lauf der Zeit werden wir Vorlagen-SDKs für alle verbleibenden Plattformen für Adaptive Karten veröffentlichen, wie iOS, Android, UWP usw.

Plattform | Paket | Installation | Dokumentation
--- | --- | --- | ---
JavaScript | [![npm-Installation](https://img.shields.io/npm/v/adaptivecards-templating.svg)](https://www.npmjs.com/package/adaptivecards-templating) | `npm install adaptivecards-templating` | [Dokumentation](https://www.npmjs.com/package/adaptivecards-templating)
.NET | [![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Templating.svg)](https://www.nuget.org/packages/AdaptiveCards.Templating) | `dotnet add package AdaptiveCards.Templating` | [Dokumentation](https://docs.microsoft.com/adaptive-cards/templating/sdk#net)

### <a name="javascript-example"></a>JavaScript-Beispiel

Das folgende JavaScript zeigt das allgemeine Muster, das zum Auffüllen einer Vorlage mit Daten verwendet wird.

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

> Weitere Informationen zu den [Vorlagen-SDKs](sdk.md)

## <a name="template-service"></a>Vorlagendienst

Der Vorlagendienst für adaptive Karten ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.

Er ist nützlich, wenn Sie einige Daten anzeigen möchten, sich aber nicht die Mühe machen möchten, eine benutzerdefinierte adaptive Karte dafür zu schreiben.

Die API zum Abrufen einer Vorlage ist unkompliziert, aber der Dienst bietet tatsächlich viel mehr, einschließlich der Möglichkeit, Ihre Daten zu analysieren und eine Vorlage zu finden, die für Sie geeignet ist.

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

Sämtliche Vorlagen sind flache JSON-Dateien, die in einem GitHub-Repository gespeichert sind, sodass jeder wie bei jedem anderen Open-Source-Code daran mitwirken kann.

> Weitere Informationen zum [Kartenvorlagendienst](service.md)

## <a name="whats-next-and-sending-feedback"></a>Nächste Schritte und Senden von Feedback

Die Vorlagenerstellung und die Trennung der Präsentation von den Daten bringen uns unserem Ziel ein ganzes Stück näher, nämlich „einem Ökosystem für den standardisierten Austausch von Karteninhalten zwischen Apps und Diensten“. Wir haben auf diesem Gebiet eine Menge zu bieten, also bleiben Sie am Ball, und informieren Sie uns auf [GitHub](https://github.com/Microsoft/AdaptiveCards/issues) über Ihre Erfahrungen!
