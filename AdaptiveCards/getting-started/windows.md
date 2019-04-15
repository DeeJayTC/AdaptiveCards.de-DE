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
# <a name="adaptive-cards-for-windows-developers"></a><span data-ttu-id="bb507-102">Mit Adaptive Cards für Windows-Entwickler</span><span class="sxs-lookup"><span data-stu-id="bb507-102">Adaptive Cards for Windows Developers</span></span>



## <a name="timeline"></a><span data-ttu-id="bb507-103">Zeitrahmen</span><span class="sxs-lookup"><span data-stu-id="bb507-103">Timeline</span></span>

<span data-ttu-id="bb507-104">Die ersten Windows auftreten, für die Unterstützung, die mit Adaptive Cards Zeitachse einer ganz neuen Umgebung, die erstmals in Windows 10-Version 1803 ist.</span><span class="sxs-lookup"><span data-stu-id="bb507-104">The first Windows experience to supports Adaptive Cards is Timeline, a brand new experience first introduced in Windows 10 1803.</span></span> 

![Zeitrahmen](media/windows/timeline.png)

### <a name="useractivity-api"></a><span data-ttu-id="bb507-106">UserActivity API</span><span class="sxs-lookup"><span data-stu-id="bb507-106">UserActivity API</span></span>

<span data-ttu-id="bb507-107">Die [ `Windows.ApplicationModel.UserActivities.UserActivity` ](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) -API ist, was eine Aktivität in der Zeitachse füllt.</span><span class="sxs-lookup"><span data-stu-id="bb507-107">The [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API is what populates an Activity into Timeline.</span></span>

<span data-ttu-id="bb507-108">Wird die Adaptive Card angegeben werden, über die `Content` Eigenschaft `VisualElement`, wie unten dargestellt:</span><span class="sxs-lookup"><span data-stu-id="bb507-108">The Adaptive Card will be supplied via the `Content` property of `VisualElement`, as seen below:</span></span>

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learn-more"></a><span data-ttu-id="bb507-109">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="bb507-109">Learn more</span></span>

<span data-ttu-id="bb507-110">Diese Sitzung auf der Build 2017 behandelt Benutzeraktivitäten in Detial.</span><span class="sxs-lookup"><span data-stu-id="bb507-110">This session at Build 2017 covers User Activities in detial.</span></span>

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a><span data-ttu-id="bb507-111">Anderen Windows-Oberflächen</span><span class="sxs-lookup"><span data-stu-id="bb507-111">Other Windows Surfaces</span></span>
<span data-ttu-id="bb507-112">Wir haben damit nichts noch freigeben, aber wir arbeiten mit Adaptive Cards in weitere Windows-Umgebungen integrieren.</span><span class="sxs-lookup"><span data-stu-id="bb507-112">We don't have anything to share just yet, but we're working on incorporating Adaptive Cards into more Windows experiences.</span></span>

## <a name="dive-in"></a><span data-ttu-id="bb507-113">Ohne weitere!</span><span class="sxs-lookup"><span data-stu-id="bb507-113">Dive in!</span></span>

<span data-ttu-id="bb507-114">Wir haben hier in diesem Tutorial nur so bald zurück, und Durchsuchen die Links unten, um mehr über mit Adaptive Cards untersuchen.</span><span class="sxs-lookup"><span data-stu-id="bb507-114">We've barely scratched the surface in this tutorial, so check back soon and browse the links below to explore more about Adaptive Cards.</span></span>

* <span data-ttu-id="bb507-115">[Beispiel-Karten Durchsuchen](http://adaptivecards.io/samples/) inspirieren</span><span class="sxs-lookup"><span data-stu-id="bb507-115">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="bb507-116">Verwenden der [Schema-Explorer](http://adaptivecards.io/explorer) um die verfügbaren Elemente zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="bb507-116">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="bb507-117">Erstellen einer Karte mit den [interaktive Schnellansicht](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span><span class="sxs-lookup"><span data-stu-id="bb507-117">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="bb507-118">[Kontakt aufnehmen](http://adaptivecards.io/connect) mit Sie haben Feedback</span><span class="sxs-lookup"><span data-stu-id="bb507-118">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
