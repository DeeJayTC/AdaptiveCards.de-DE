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
# <a name="getting-started---xamarinandroid"></a>Getting Started-xamarin. Android

Dabei handelt es sich um eine rendererbibliothek, die auf native xamarin Android-Anwendungen abzielt und auf dem Android-Renderer basiert, den Sie [hier](../../android/getting-started.md)finden können. 

## <a name="nuget-install"></a>Nuget-Installation

[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Xamarin.Android.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Xamarin.Android)

Die veröffentlichten Pakete finden Sie [hier](http://nuget.org) .

```console
Install-Package AdaptiveCards.Rendering.Xamarin.Android -Version 0.1.0-alpha
```

## <a name="namespace"></a>Namespace

Die erforderlichen Namespaces für die Verwendung dieser Bibliothek sind
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

## <a name="xamarinandroid-visualizer-sample"></a>Beispiel für xamarin. Android-Schnellansicht

Mit dem [Beispiel xamarin. Android Visualizer](https://github.com/Microsoft/AdaptiveCards/tree/master/source/xamarin/Xamarin.Droid.Sample) können Sie Karten mithilfe von xamarin. Android visualisieren. Wenn Sie die Android-Beispielanwendung schon einmal verwendet haben, finden Sie eine ähnliche Darstellung.

## <a name="next-steps"></a>Nächste Schritte

Für einen Schnellstart aktivieren Sie [eine Karte](render-a-card.md) für die nächsten Schritte.

Eine ausführlichere Ansicht der Klassen, die für die xamarin. Android-rendererbibliothek gebunden wurden, können Sie überprüfen, indem Sie einige der Klassen Klassen überprüfen, indem Sie unten darauf klicken:
* [```AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md)
* [```AdaptiveCardRenderer```](adaptivecards-rendering-xamarin-android-renderer-adaptivecardrenderer.md)
* [```CardRendererRegistration```](adaptivecards-rendering-xamarin-android-renderer-cardrendererregistration.md)
* [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md)
* [```ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md)
* [```RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md)