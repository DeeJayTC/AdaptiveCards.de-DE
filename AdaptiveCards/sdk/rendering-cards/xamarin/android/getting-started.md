---
title: Xamarin.Android-SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: a7fd40ac7f026e2a325e7dc52e10defe550fd43a
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146004"
---
# <a name="getting-started---xamarinandroid"></a><span data-ttu-id="9fcac-102">Getting Started-xamarin. Android</span><span class="sxs-lookup"><span data-stu-id="9fcac-102">Getting started - Xamarin.Android</span></span>

<span data-ttu-id="9fcac-103">Dabei handelt es sich um eine rendererbibliothek, die auf native xamarin Android-Anwendungen abzielt und auf dem Android-Renderer basiert, den Sie [hier](../../android/getting-started.md)finden können.</span><span class="sxs-lookup"><span data-stu-id="9fcac-103">This is a renderer library which targets native xamarin android applications and is based on the Android renderer that you can find [here](../../android/getting-started.md).</span></span> 

## <a name="nuget-install"></a><span data-ttu-id="9fcac-104">Nuget-Installation</span><span class="sxs-lookup"><span data-stu-id="9fcac-104">NuGet install</span></span>

<span data-ttu-id="9fcac-105">[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Xamarin.Android.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Xamarin.Android)</span><span class="sxs-lookup"><span data-stu-id="9fcac-105">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Xamarin.Android.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Xamarin.Android)</span></span>

<span data-ttu-id="9fcac-106">Die veröffentlichten Pakete finden Sie [hier](http://nuget.org) .</span><span class="sxs-lookup"><span data-stu-id="9fcac-106">You can find the published packages [here](http://nuget.org)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Xamarin.Android -Version 0.1.0-alpha
```

## <a name="namespace"></a><span data-ttu-id="9fcac-107">Namespace</span><span class="sxs-lookup"><span data-stu-id="9fcac-107">Namespace</span></span>

<span data-ttu-id="9fcac-108">Die erforderlichen Namespaces für die Verwendung dieser Bibliothek sind</span><span class="sxs-lookup"><span data-stu-id="9fcac-108">The necessary namespaces for using this library are</span></span>
```csharp
// To import the base object model classes as AdaptiveCard, TextBlock, Column, ShowCardAction, ...
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;

// To import the AdaptiveCardRenderer class
using AdaptiveCards.Rendering.Xamarin.Android.Renderer;

// To import the ICardActionHandler interface
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler;

// To use feature registration and register custom behaviour 
using AdaptiveCards.Rendering.Xamarin.Android.Renderer.Registration;
```

## <a name="xamarinandroid-visualizer-sample"></a><span data-ttu-id="9fcac-109">Beispiel für xamarin. Android-Schnellansicht</span><span class="sxs-lookup"><span data-stu-id="9fcac-109">Xamarin.Android Visualizer Sample</span></span>

<span data-ttu-id="9fcac-110">Mit dem [Beispiel xamarin. Android Visualizer](https://github.com/Microsoft/AdaptiveCards/tree/master/source/xamarin/Xamarin.Droid.Sample) können Sie Karten mithilfe von xamarin. Android visualisieren.</span><span class="sxs-lookup"><span data-stu-id="9fcac-110">The [Xamarin.Android Visualizer sample](https://github.com/Microsoft/AdaptiveCards/tree/master/source/xamarin/Xamarin.Droid.Sample) lets you visualize cards using Xamarin.Android.</span></span> <span data-ttu-id="9fcac-111">Wenn Sie die Android-Beispielanwendung schon einmal verwendet haben, finden Sie eine ähnliche Darstellung.</span><span class="sxs-lookup"><span data-stu-id="9fcac-111">If you have ever used the Android sample application you'll find the experience to be really similar.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9fcac-112">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9fcac-112">Next steps</span></span>

<span data-ttu-id="9fcac-113">Für einen Schnellstart aktivieren Sie [eine Karte](render-a-card.md) für die nächsten Schritte.</span><span class="sxs-lookup"><span data-stu-id="9fcac-113">For a quick start check [Render a card](render-a-card.md) for the next steps!</span></span>

<span data-ttu-id="9fcac-114">Eine ausführlichere Ansicht der Klassen, die für die xamarin. Android-rendererbibliothek gebunden wurden, können Sie überprüfen, indem Sie einige der Klassen Klassen überprüfen, indem Sie unten darauf klicken:</span><span class="sxs-lookup"><span data-stu-id="9fcac-114">For a more in depth view of the classes that have been binded for the Xamarin.Android renderer library, you can check some of the binded classes by clicking on them below:</span></span>
* [```AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md)
* [```AdaptiveCardRenderer```](adaptivecards-rendering-xamarin-android-renderer-adaptivecardrenderer.md)
* [```CardRendererRegistration```](adaptivecards-rendering-xamarin-android-renderer-cardrendererregistration.md)
* [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md)
* [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md)
* [```RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md)