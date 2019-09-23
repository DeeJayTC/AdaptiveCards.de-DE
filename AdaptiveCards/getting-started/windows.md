---
title: Adaptive Karten für Windows-Entwickler
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 65494ed437303d26a202c9a5b95f88255147cbd0
ms.sourcegitcommit: 48838a50b5f0316e15b48d740a7dd0a5f96ebae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70923077"
---
# <a name="adaptive-cards-for-windows-developers"></a><span data-ttu-id="eb8cb-102">Adaptive Karten für Windows-Entwickler</span><span class="sxs-lookup"><span data-stu-id="eb8cb-102">Adaptive Cards for Windows Developers</span></span>

## <a name="timeline"></a><span data-ttu-id="eb8cb-103">Zeitrahmen</span><span class="sxs-lookup"><span data-stu-id="eb8cb-103">Timeline</span></span>

<span data-ttu-id="eb8cb-104">Die erste Windows-Oberfläche, die adaptive Karten unterstützt, ist die Chronik, die in Windows 10 1803 eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-104">The first Windows experience to supports Adaptive Cards is Timeline, a brand new experience first introduced in Windows 10 1803.</span></span> 

![Zeitrahmen](media/windows/timeline.png)

### <a name="useractivity-api"></a><span data-ttu-id="eb8cb-106">UserActivity-API</span><span class="sxs-lookup"><span data-stu-id="eb8cb-106">UserActivity API</span></span>

<span data-ttu-id="eb8cb-107">Die [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity)-API füllt die Chronik mit Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-107">The [`Windows.ApplicationModel.UserActivities.UserActivity`](https://docs.microsoft.com/en-us/uwp/api/windows.applicationmodel.useractivities.useractivity) API is what populates an Activity into Timeline.</span></span>

<span data-ttu-id="eb8cb-108">Die adaptive Karte wird über die Eigenschaft `Content` von `VisualElement` bereitgestellt (s. u.):</span><span class="sxs-lookup"><span data-stu-id="eb8cb-108">The Adaptive Card will be supplied via the `Content` property of `VisualElement`, as seen below:</span></span>

```csharp
UserActivity userActivity = await channel.GetOrCreateUserActivityAsync(activityId, new HostName("contoso.com"));
userActivity.ActivationUri = new Uri("rss-reader:article?" + article.Link);
userActivity.DisplayText = article.Title; //used for details tile text
userActivity.VisualElements.Content = AdaptiveCardBuilder.CreateAdaptiveCardFromJson(jsonString);
await userActivity.SaveAsync();
```

### <a name="learning-module"></a><span data-ttu-id="eb8cb-109">Lernmodul</span><span class="sxs-lookup"><span data-stu-id="eb8cb-109">Learning Module</span></span>

<span data-ttu-id="eb8cb-110">Diese Schritte werden vollständig in einem hervorragenden, 45-minütigen Lernmodul behandelt.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-110">There is a great 45-min learn module that covers these steps end-to-end.</span></span>

[<span data-ttu-id="eb8cb-111">Adaptive Karten in die Windows 10-Zeitachse integrieren</span><span class="sxs-lookup"><span data-stu-id="eb8cb-111">Integrate adaptive cards into Windows 10 Timeline</span></span>](https://docs.microsoft.com/en-us/learn/modules/integrate-app-into-windows-10-timeline/)

### <a name="learn-more"></a><span data-ttu-id="eb8cb-112">Mehr erfahren</span><span class="sxs-lookup"><span data-stu-id="eb8cb-112">Learn more</span></span>

<span data-ttu-id="eb8cb-113">Diese Sitzung auf der Build 2017 behandelt Benutzeraktivitäten im Detail.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-113">This session at Build 2017 covers User Activities in detial.</span></span>

<iframe src="https://channel9.msdn.com/Events/Build/2017/B8108/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

## <a name="other-windows-surfaces"></a><span data-ttu-id="eb8cb-114">Weitere Windows-Oberflächen</span><span class="sxs-lookup"><span data-stu-id="eb8cb-114">Other Windows Surfaces</span></span>
<span data-ttu-id="eb8cb-115">Hier können wir dir noch nichts zeigen, aber wir arbeiten daran, adaptive Karten in mehr Windows-Oberflächen zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-115">We don't have anything to share just yet, but we're working on incorporating Adaptive Cards into more Windows experiences.</span></span>

## <a name="dive-in"></a><span data-ttu-id="eb8cb-116">Jetzt eintauchen</span><span class="sxs-lookup"><span data-stu-id="eb8cb-116">Dive in!</span></span>

<span data-ttu-id="eb8cb-117">In diesem Tutorial haben wir das Thema nur oberflächlich behandelt. Sieh dir daher die folgenden Links an, um mehr über adaptive Karten zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-117">We've barely scratched the surface in this tutorial, so check back soon and browse the links below to explore more about Adaptive Cards.</span></span>

* <span data-ttu-id="eb8cb-118">Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-118">[Browse Sample cards](http://adaptivecards.io/samples/) for inspiration</span></span>
* <span data-ttu-id="eb8cb-119">Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer).</span><span class="sxs-lookup"><span data-stu-id="eb8cb-119">Use the [Schema Explorer](http://adaptivecards.io/explorer) to learn the available elements</span></span>
* <span data-ttu-id="eb8cb-120">Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype).</span><span class="sxs-lookup"><span data-stu-id="eb8cb-120">Build a card using the [Interactive Visualizer](http://adaptivecards.io/visualizer/index.html?hostApp=Skype)</span></span>
* <span data-ttu-id="eb8cb-121">[Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.</span><span class="sxs-lookup"><span data-stu-id="eb8cb-121">[Get in touch](http://adaptivecards.io/connect) with any feedback you have</span></span>
