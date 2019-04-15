---
title: Mit Adaptive Cards für Windows-Entwickler
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 20b324c12cd7cec10f2142fc2cf76039b5c329de
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552852"
---
# <a name="adaptive-cards-for-windows-developers"></a>Mit Adaptive Cards für Windows-Entwickler



## <a name="timeline"></a>Zeitrahmen

Die ersten Windows auftreten, für die Unterstützung, die mit Adaptive Cards Zeitachse einer ganz neuen Umgebung, die erstmals in Windows 10-Version 1803 ist. 

![Zeitrahmen](media/windows/timeline.png)

### <a name="useractivity-api"></a>UserActivity API

Die [ `Windows.ApplicationModel.UserActivities.UserActivity` ](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) -API ist, was eine Aktivität in der Zeitachse füllt.

Wird die Adaptive Card angegeben werden, über die `Content` Eigenschaft `VisualElement`, wie unten dargestellt:

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a>Mehr erfahren

Diese Sitzung auf der Build 2017 behandelt Benutzeraktivitäten in Detial.

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a>Anderen Windows-Oberflächen
Wir haben damit nichts noch freigeben, aber wir arbeiten mit Adaptive Cards in weitere Windows-Umgebungen integrieren.

## <a name="dive-in"></a>Ohne weitere!

Wir haben hier in diesem Tutorial nur so bald zurück, und Durchsuchen die Links unten, um mehr über mit Adaptive Cards untersuchen.

* [Beispiel-Karten Durchsuchen](http://adaptivecards.io/samples/) inspirieren
* Verwenden der [Schema-Explorer](http://adaptivecards.io/explorer) um die verfügbaren Elemente zu erfahren.
* Erstellen einer Karte mit den [interaktive Schnellansicht](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)
* [Kontakt aufnehmen](http://adaptivecards.io/connect) mit Sie haben Feedback
