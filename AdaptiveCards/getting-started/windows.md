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
# <a name="adaptive-cards-for-windows-developers"></a><span data-ttu-id="3626e-102">Adaptive Karten für Windows-Entwickler</span><span class="sxs-lookup"><span data-stu-id="3626e-102">Adaptive Cards for Windows Developers</span></span>



## <a name="timeline"></a><span data-ttu-id="3626e-103">Chronik</span><span class="sxs-lookup"><span data-stu-id="3626e-103">Timeline</span></span>

<span data-ttu-id="3626e-104">Die erste Windows-Oberfläche, die adaptive Karten unterstützt, ist die Chronik, die in Windows 10 1803 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3626e-104">The first Windows experience to supports Adaptive Cards is Timeline, a brand new experience first introduced in Windows 10 1803.</span></span> 

![Chronik](media/windows/timeline.png)

### <a name="useractivity-api"></a><span data-ttu-id="3626e-106">UserActivity-API</span><span class="sxs-lookup"><span data-stu-id="3626e-106">UserActivity API</span></span>

<span data-ttu-id="3626e-107">Die [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity)-API füllt die Chronik mit Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="3626e-107">The [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API is what populates an Activity into Timeline.</span></span>

<span data-ttu-id="3626e-108">Die adaptive Karte wird über die Eigenschaft `Content` von `VisualElement` bereitgestellt (s. u.):</span><span class="sxs-lookup"><span data-stu-id="3626e-108">The Adaptive Card will be supplied via the `Content` property of `VisualElement`, as seen below:</span></span>

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a><span data-ttu-id="3626e-109">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="3626e-109">Learn more</span></span>

<span data-ttu-id="3626e-110">Diese Sitzung auf der Build 2017 behandelt Benutzeraktivitäten im Detail.</span><span class="sxs-lookup"><span data-stu-id="3626e-110">This session at Build 2017 covers User Activities in detial.</span></span>

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a><span data-ttu-id="3626e-111">Weitere Windows-Oberflächen</span><span class="sxs-lookup"><span data-stu-id="3626e-111">Other Windows Surfaces</span></span>
<span data-ttu-id="3626e-112">Hier können wir dir noch nichts zeigen, aber wir arbeiten daran, adaptive Karten in mehr Windows-Oberflächen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-112">We don't have anything to share just yet, but we're working on incorporating Adaptive Cards into more Windows experiences.</span></span>

## <a name="dive-in"></a><span data-ttu-id="3626e-113">Jetzt eintauchen</span><span class="sxs-lookup"><span data-stu-id="3626e-113">Dive in!</span></span>

<span data-ttu-id="3626e-114">In diesem Tutorial haben wir das Thema nur oberflächlich behandelt. Sieh dir daher die folgenden Links an, um mehr über adaptive Karten zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="3626e-114">We've barely scratched the surface in this tutorial, so check back soon and browse the links below to explore more about Adaptive Cards.</span></span>

* <span data-ttu-id="3626e-115">Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.</span><span class="sxs-lookup"><span data-stu-id="3626e-115">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="3626e-116">Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer).</span><span class="sxs-lookup"><span data-stu-id="3626e-116">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="3626e-117">Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype).</span><span class="sxs-lookup"><span data-stu-id="3626e-117">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="3626e-118">[Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.</span><span class="sxs-lookup"><span data-stu-id="3626e-118">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
