---
title: Adaptive Karten für Windows-Entwickler
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 20b324c12cd7cec10f2142fc2cf76039b5c329de
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552852"
---
# <a name="adaptive-cards-for-windows-developers"></a>Adaptive Karten für Windows-Entwickler



## <a name="timeline"></a>Chronik

Die erste Windows-Oberfläche, die adaptive Karten unterstützt, ist die Chronik, die in Windows 10 1803 eingeführt wurde. 

![Chronik](media/windows/timeline.png)

### <a name="useractivity-api"></a>UserActivity-API

Die [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity)-API füllt die Chronik mit Aktivitäten.

Die adaptive Karte wird über die Eigenschaft `Content` von `VisualElement` bereitgestellt (s. u.):

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a>Mehr erfahren

Diese Sitzung auf der Build 2017 behandelt Benutzeraktivitäten im Detail.

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a>Weitere Windows-Oberflächen
Hier können wir dir noch nichts zeigen, aber wir arbeiten daran, adaptive Karten in mehr Windows-Oberflächen zu integrieren.

## <a name="dive-in"></a>Jetzt eintauchen

In diesem Tutorial haben wir das Thema nur oberflächlich behandelt. Sieh dir daher die folgenden Links an, um mehr über adaptive Karten zu erfahren.

* Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.
* Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer).
* Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype).
* [Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.
