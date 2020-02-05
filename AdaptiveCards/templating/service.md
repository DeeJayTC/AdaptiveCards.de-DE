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
# <a name="adaptive-cards-template-service"></a>Vorlagendienst für adaptive Karten

Der Vorlagendienst für adaptive Karten ist ein Machbarkeitsnachweisdienst, der es jedem Benutzer ermöglicht, eine Reihe bekannter Vorlagen zu finden, zu ergänzen und freizugeben.

Er ist nützlich, wenn Sie einige Daten anzeigen möchten, sich aber nicht die Mühe machen möchten, eine benutzerdefinierte adaptive Karte dafür zu schreiben.

> Hier finden Sie einen [Überblick über Vorlagen für adaptive Karten](index.md).

> [!IMPORTANT] 
> 
> *Geschäftsbedingungen und Vertrag* 
> 
> Dieser **alpha-level**-Dienst wird „in der vorliegenden Form“ und mit allen möglichen Fehler und ohne jeglichen Support bereitgestellt. Jede Datensammlung des Diensts unterliegt der [Microsoft-Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?LinkID=824704).
> 
> Diese Features befinden sich **in der Vorschauphase und können geändert werden**. Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.

## <a name="how-does-the-service-help-me"></a>Wie unterstützt der Dienst mich?

Angenommen, ich verfüge nur über ein einziges Datenelement, beispielsweise Finanzdaten, Microsoft Graph-Daten, schema.org-Daten oder benutzerdefinierte Daten aus meiner Organisation. 

Jetzt möchte ich die Daten für einen Benutzer anzeigen. 

Normalerweise bedeutet dies, dass ich benutzerdefinierten Benutzeroberflächencode in allen Front-End-Stapeln schreiben muss, die für Endbenutzer bereitstellt werden.

Was wäre jedoch, wenn meine App neue Benutzeroberflächenvorlagen basierend auf dem Typ der Daten „erlernen“ könnte? Was, wenn jeder an Benutzeroberflächenvorlagen mitwirken, diese verbessern und in eigenen Projekten innerhalb einer Organisation oder für das gesamte Internet freigeben könnte?

## <a name="what-is-the-card-template-service"></a>Was ist der Kartenvorlagendienst?

Der Kartenvorlagendienst ist ein einfacher REST-Endpunkt, der Folgendes unterstützt:

* **Suchen** einer Vorlage durch Analysieren der Struktur Ihrer Daten
* **Abrufen** einer Vorlage mit einer direkten Bindung auf dem Client, *ohne dass die Daten an den Server gesendet werden oder das Gerät jemals verlassen*
* **Auffüllen** einer Vorlage auf dem Server, wenn die clientseitige Datenbindung nicht geeignet oder nicht möglich ist

Dahinter steht:

* Ein freigegebenes Open Source-Vorlagenrepository, das von GitHub unterstützt wird. *(Das Repository ist zurzeit privat, wird jedoch öffentlich gemacht, sobald einige lose Enden verknüpft sind.)*
* Alle Vorlagen sind JSON-Flatfiles im Repository, wodurch das Bearbeiten, Mitwirken und Freigeben zu einem natürlichen Bestandteil des Entwicklerworkflows wird.
* Der Code für den Dienst wird zur Verfügung gestellt, sodass Sie ihn überall dort hosten können, wo es für Sie am sinnvollsten ist. 

## <a name="using-the-service"></a>Verwenden des Diensts

### <a name="get-all-templates"></a>Abrufen aller Vorlagen 

Dieser Endpunkt gibt eine Liste aller bekannten Vorlagen zurück.

> `HTTP GET https://templates.adaptivecards.io/list`

**Antwortauszug**

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

### <a name="find-a-template"></a>Suchen einer Vorlage

Dieser Endpunkt versucht, eine Vorlage durch Analysieren der Struktur Ihrer Daten zu finden.

> `HTTP POST https://templates.adaptivecards.io/find`

#### <a name="example"></a>Beispiel

Angenommen, ich klicke einfach auf einen [Microsoft Graph](https://graph.microsoft.com)-Endpunkt, um Organisationsdaten über mich abzurufen.

> `HTTP GET https://graph.microsoft.com/v1.0/me/`

![Graph-Explorer-Screenshot](content/2019-08-01-12-08-13.png)

Diese API gab **JSON-Daten** zurück, aber wie kann ich Benutzern **diese Daten mit adaptiven Karten anzeigen**? 

Zuerst möchte ich überprüfen, ob für diese Art von Daten eine Vorlage vorhanden ist. Daher stelle ich eine HTTP-Anforderung an den `/find`-Endpunkt mit meinen Daten im `POST body`.

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

**Antwort:**

```json
[
  {
    "templateUrl": "graph.microsoft.com/Profile.json",
    "confidence": 1
  }
]
```

Der Dienst gibt eine Liste aller übereinstimmenden Vorlagen zurück, zusammen mit einem `confidence`-Element, das angibt, wie genau die Übereinstimmung ist. Jetzt kann ich diese Vorlagen-URL verwenden, um die Vorlage **abzurufen** oder sie serverseitig **aufzufüllen**.

### <a name="get-a-template"></a>Abrufen einer Vorlage

Eine Vorlage, die von diesem Endpunkt abgerufen wird, kann zur Laufzeit [unter Verwendung des Vorlagen-SDKs](sdk.md) mit Daten aufgefüllt werden.

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]`

Sie können auch „Beispieldaten“ in die Vorlage einschließen, sodass die Bearbeitung im Designer benutzerfreundlicher wird:

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]?sampleData=true`

#### <a name="example"></a>Beispiel

Abrufen der Microsoft Graph-Profilvorlage, die von `/find` oben zurückgegeben wurde.

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

**Antwortauszug**

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

Verwenden Sie diese Vorlage jetzt mit den [Vorlagen-SDKs](sdk.md), um eine zum Rendern bereite adaptive Karte zu erstellen.

### <a name="populate-a-template-server-side"></a>Serverseitiges Auffüllen einer Vorlage

In einigen Fällen ist es möglicherweise nicht sinnvoll, eine Vorlage auf dem Client aufzufüllen.  In diesen Anwendungsfällen können Sie vom Dienst eine vollständig aufgefüllte adaptive Karte zurückgeben lassen, die bereit für die Übergabe an einen beliebigen Renderer für adaptive Karten ist.

> `HTTP POST https://templates.adaptivecards.io/[TEMPLATE-PATH]`

#### <a name="example"></a>Beispiel

Auffüllen der Microsoft Graph-Profilvorlage, die von `/find` oben zurückgegeben wurde.

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

**Antwortauszug**

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

Beachten Sie, dass die Antwort den Text des ersten `TextBlock` durch `"Megan Bowen"` anstelle von `"{name}"` ersetzt hat, wie in der `GET`-Anforderung. Diese adaptive Karte kann nun ohne clientseitige Vorlagenanwendung an einen beliebigen Renderer für adaptive Karten übergeben werden.

## <a name="contributing-templates"></a>Beitragende Vorlagen

Der Vorlagendienst wird von einem GitHub-Repository unterstützt. Das Repository ist zurzeit **privat**, wird jedoch als Open Source verfügbar gemacht, sobald einige lose Enden verknüpft sind.

Wir hoffen, dass wir mithilfe von GitHub als Sicherungsspeicher für die Vorlagen den Prozess der Erstellung, Verbesserung und Freigabe von Vorlagen „demokratischer“ gestalten können. Jeder kann einen Pull Request mit einer völlig neuen Vorlage übermitteln oder Verbesserungen an vorhandenen Vorlagen vornehmen, und zwar alles innerhalb der entwicklerfreundlichen GitHub-Umgebung.

## <a name="self-hosting-the-service"></a>Selbsthosting des Diensts

Nicht alle Datentypen sind für den unter `https://templates.adaptivecards.io` gehosteten „zentralen“ Vorlagendienst für adaptive Karten geeignet. 

Wir möchten sicherstellen, dass alle Benutzer den Vorlagendienst in Ihrer Organisation hosten können, um den Quellcode verfügbar zu machten, und wir vereinfachen die Bereitstellung in Azure oder in Ihrem eigenen Back-End.

Weitere Informationen hierzu zu einem späteren Zeitpunkt.