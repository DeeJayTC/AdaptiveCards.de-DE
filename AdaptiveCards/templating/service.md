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
# <a name="adaptive-cards-template-service"></a>Vorlagen Dienst für Adaptive Karten

Der Vorlagen Dienst für Adaptive Karten ist ein Proof of Concept-Dienst, mit dem jeder eine Reihe bekannter Vorlagen finden, mitwirken und freigeben kann.

Es ist nützlich, wenn Sie einige Daten anzeigen möchten, aber nicht mit dem Schreiben einer benutzerdefinierten adaptiven Karte für die Daten.

> Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.

> [!IMPORTANT] 
> 
> *Bestimmungen und Vereinbarung* 
> 
> Dieser Dienst auf **Alpha Ebene** wird unverändert bereitgestellt, wobei alle Fehler auftreten und in keiner Weise unterstützt werden. Jede Datensammlung vom Dienst unterliegt den Daten [Schutzbestimmungen von Microsoft](https://go.microsoft.com/fwlink/?LinkID=824704).
> 
> Diese Features befinden sich **in der Vorschau Phase und können geändert**werden. Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass wir die benötigten Features bereitstellen.

## <a name="how-does-the-service-help-me"></a>Wie unterstützt der Dienst mich?

Nehmen wir an, ich habe nur ein Datenelement, vielleicht auch Finanzdaten, Microsoft Graph Daten, Schema.org Daten oder benutzerdefinierte Daten aus meiner Organisation. 

Jetzt möchte ich die Daten für einen Benutzer anzeigen. 

Normalerweise bedeutet dies, dass benutzerdefinierter Benutzeroberflächen Code in allen Front-End-Stapeln geschrieben werden muss, die für Endbenutzer bereitstellt werden.

Was passiert jedoch, wenn meine APP neue Vorlagen für die Benutzeroberfläche basierend auf dem Typ der Daten "erlernen" könnte? Eine Welt, in der alle Benutzeroberflächen Vorlagen, in ihren eigenen Projekten, innerhalb einer Organisation oder für das gesamte Internet mitwirken, verbessern und freigeben können.

## <a name="what-is-the-card-template-service"></a>Was ist der Karten Vorlagen Dienst?

Der Kartendienst für Karten ist ein einfacher Rest-Endpunkt, der Folgendes unterstützt:

* **Suchen** Sie eine Vorlage, indem Sie die Struktur Ihrer Daten analysieren.
* Sie **erhalten** eine Vorlage, sodass Sie Sie direkt auf dem Client binden können, *ohne die Daten an den Server zu senden oder jemals das Gerät zu hinterlassen* .
* **Füllen** Sie eine Vorlage auf dem Server auf, wenn die Client seitige Datenbindung nicht geeignet oder nicht möglich ist.

Dahinter geht es:

* Ein frei gegebenes Open Source-vorlagenrepository, das von GitHub unterstützt wird. *(Das Repository ist zurzeit privat, wird jedoch als öffentlich festgehalten, sobald einige lose Enden verknüpft sind.)*
* Alle Vorlagen sind flatjson-Dateien im Repository, die die Bearbeitung, den Beitrag und die gemeinsame Nutzung eines natürlichen Teils eines Entwickler Workflows erleichtern.
* Der Code für den Dienst wird zur Verfügung gestellt, sodass Sie überall dort hosten können, wo Sie es am sinnvollsten machen. 

## <a name="using-the-service"></a>Verwenden des Dienstanbieter

### <a name="get-all-templates"></a>Alle Vorlagen erhalten 

Dieser Endpunkt gibt eine Liste aller bekannten Vorlagen zurück.

> `HTTP GET https://templates.adaptivecards.io/list`

**Antwort Auszug**

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

### <a name="find-a-template"></a>Vorlage suchen

Dieser Endpunkt versucht, eine Vorlage zu finden, indem er die Struktur der Daten analysiert.

> `HTTP POST https://templates.adaptivecards.io/find`

#### <a name="example"></a>Beispiel

Nehmen wir an, ich klicke einfach auf einen [Microsoft Graph](https://graph.microsoft.com) Endpunkt, um Organisationsdaten zu mir zu erhalten.

> `HTTP GET https://graph.microsoft.com/v1.0/me/`

![Screenshot des Graph-Explorers](content/2019-08-01-12-08-13.png)

Diese API gab **JSON-Daten**zurück, aber wie **zeige ich Sie** Benutzern mit adaptiven Karten? 

Zuerst möchte ich überprüfen, ob für diese Art von Daten eine Vorlage vorhanden ist `/find` `POST body`. daher erstelle ich eine HTTP-Anforderung an den Endpunkt mit meinen Daten im.

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

**Auf**

```json
[
  {
    "templateUrl": "graph.microsoft.com/Profile.json",
    "confidence": 1
  }
]
```

Der Dienst gibt eine Liste aller übereinstimmenden Vorlagen zusammen mit einem `confidence` -Wert zurück, der angibt, wie nah die Übereinstimmung ist. Nun kann ich diese Vorlagen-URL verwenden, um die Vorlage zu **erhalten** , oder Sie kann serverseitig auffüllen.

### <a name="get-a-template"></a>Vorlage erstellen

Eine Vorlage, die von diesem Endpunkt abgerufen wird, kann [mithilfe der templatng-sdche](sdk.md)zur Laufzeit mit Daten aufgefüllt werden.

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]`

Sie können auch "Sample Data" in die Vorlage einschließen, sodass die Bearbeitung im Designer benutzerfreundlicher wird:

> `HTTP GET https://templates.adaptivecards.io/[TEMPLATE-PATH]?sampleData=true`

#### <a name="example"></a>Beispiel

Wir holen uns die Microsoft Graph Profil Vorlage, die `/find` oben zurückgegeben wurde.

`HTTP GET https://templates.adaptivecards.io/graph.microsoft.com/Profile.json`

**Antwort Auszug**

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

Verwenden Sie diese Vorlage jetzt mit den Vorlagen- [sdchen](sdk.md) , um eine fertige Adaptive Karte zu erstellen.

### <a name="populate-a-template-server-side"></a>Auffüllen einer serverseitigen Vorlage

In einigen Fällen ist es möglicherweise nicht sinnvoll, eine Vorlage auf dem Client aufzufüllen.  In diesen Anwendungsfällen kann der Dienst eine vollständig aufgefüllte Adaptive Karte zurückgeben lassen, die an einen beliebigen adaptiver Karten-Renderer übermittelt werden kann.

> `HTTP POST https://templates.adaptivecards.io/[TEMPLATE-PATH]`

#### <a name="example"></a>Beispiel

Füllen wir nun die Microsoft Graph Profil Vorlage auf, die bei `/find` Verwendung der obigen Daten zurückgegeben wurde.

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

**Antwort Auszug**

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

Beachten Sie, dass die Antwort den Text der ersten `TextBlock` `"Megan Bowen"` durch anstelle von `"{name}"`, wie in der `GET` Anforderung, ersetzt hat. Diese adaptivecard kann nun an jeden adaptiver Karten-Renderer übergeben werden, ohne die Client seitige Vorlage zu durchlaufen.

## <a name="contributing-templates"></a>Beitragende Vorlagen

Der Vorlagen Dienst wird von einem GitHub-Repository unterstützt (das derzeit **Privat**ist), aber wir werden die Quelle öffnen, sobald wir einige lose Enden anbinden.

Wir hoffen, dass wir mithilfe von GitHub als Sicherungs Speicher für die Vorlagen den Prozess der Erstellung, Verbesserung und Freigabe von Vorlagen "demokratisieren" können. Jeder kann einen Pull Request übermitteln, der eine völlig neue Vorlage enthält, oder vorhandene Verbesserungen an vorhandenen... alles innerhalb des Entwickler freundlichen GitHub-Erlebnisses.

## <a name="self-hosting-the-service"></a>Self-Hosting des Diensts

Nicht alle Datentypen eignen sich für den "zentralen" adaptiven Kartendienst, der unter `https://templates.adaptivecards.io`gehostet wird. 

Wir möchten sicherstellen, dass alle Benutzer den Vorlagen Dienst innerhalb Ihrer Organisation hosten können, sodass der Quellcode verfügbar gemacht wird, und wir vereinfachen die Bereitstellung in Azure oder in Ihrem eigenen Back-End.

Weitere Informationen hierzu zu einem späteren Zeitpunkt.