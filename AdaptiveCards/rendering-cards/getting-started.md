---
title: Rendern von Karten in Ihrer Anwendung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 0a9507c56a8bae9f038c220cdf55e34b2c3b0829
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552922"
---
# <a name="rendering-cards-inside-your-application"></a>Rendern von Karten in Ihrer Anwendung

Es ist einfach, mit Adaptive Cards in Ihrer Anwendung zu rendern. Wir stellen SDKs für die alle gängiger Plattformen, sowie eine [ausführliche Spezifikation](implement-a-renderer.md) für das Erstellen eigener Adaptive Card-Renderer.

1. **Installieren Sie einen Renderer SDK** : für die Zielplattform.
2. **Erstellen Sie eine Instanz der Renderer** – mit Ihrer app-Stil, Regeln und Aktion Ereignishandler konfiguriert.
3. **Eine Karte zu rendern und native UI** – automatisch formatiertes zu Ihrer app.

## <a name="adaptive-cards-sdks"></a>Mit Adaptive Cards-SDKs

|Platform|Installieren|Version|Dokumentation|Status|
|---|---|---|---|---|
| JavaScript | [![Npm-Installation](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/nodejs)| [Docs](../sdk/rendering-cards/javascript/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20564.svg) |
| WPF FÜR .NET | [![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet)| [Docs](../sdk/rendering-cards/net-wpf/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| .NET HTML | [![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Html.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Html) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet) | [Docs](../sdk/rendering-cards/net-html/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| Windows UWP | [![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Uwp.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Uwp) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/uwp) | [Docs](../sdk/rendering-cards/uwp/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20583.svg) |
| Android | [![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/android) | [Docs](../sdk/rendering-cards/android/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/17651.svg)
| iOS | [![CocoaPods](https://img.shields.io/cocoapods/v/AdaptiveCards.svg)](https://cocoapods.org/pods/AdaptiveCards) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/ios) | [Docs](../sdk/rendering-cards/ios/getting-started.md) |  ![Buildstatus](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/16990.svg) |

## <a name="create-an-instance-of-the-renderer"></a>Erstellen Sie eine Instanz des Renderers

Der nächste Schritt ist die Erstellung von einer Instanz von einem `AdaptiveCardRenderer`. 

### <a name="hook-up-action-events"></a>Einbinden von Aktionsereignissen

Standardmäßig werden die Aktionen als Schaltflächen auf der Karte gerendert, aber es liegt an Ihre app so zu machen, die das erwartete Verhalten. Jedes SDK verfügt über das Äquivalent einer `OnAction` -Ereignis, das Sie behandeln müssen.

* **Action.OpenUrl** – öffnen Sie das angegebene `url`.  
* **Action.Submit** – nutzen Sie das Ergebnis der Sendevorgang und senden Sie sie an der Quelle. Wie Sie es an der Quelle der Karte senden ist völlig Ihnen überlassen.
* **Action.ShowCard** : Ruft ein Dialogfeld und rendert die untergeordneten Karte in diesem Dialogfeld. Beachten Sie, dass Sie nur diesen, wenn behandeln müssen `ShowCardActionMode` nastaven NA hodnotu `popup`.

## <a name="render-a-card"></a>Rendern einer Karte

Nachdem Sie eine Karte-Nutzlast erhalten, haben rufen Sie den Renderer einfach, und übergeben Sie die Karte. Sehen Sie ein systemeigenes UI-Objekt, das den Karteninhalt besteht zurückzukehren. Jetzt gerade haben Sie diese Benutzeroberfläche an einer beliebigen Stelle in Ihrer app.

## <a name="customization"></a>Anpassung

Es gibt mehrere Möglichkeiten, die Sie anpassen können, was gerendert wird. 

### <a name="hostconfig"></a>HostConfig

Ein [HostConfig](host-config.md) ist ein gemeinsam genutzter, plattformübergreifende Konfigurationsobjekt, das die grundlegende Aussehen und das Verhalten der Karten in Ihrer app steuert. Dinge wie Schriftgrößen, Abstände zwischen den Elementen, die Farben, die Anzahl der unterstützten Aktionen usw. definiert. 

### <a name="native-platform-styling"></a>Systemeigene Plattform erstellen

Die meisten Benutzeroberflächen-Frameworks können Sie die gerenderte Karte zu formatieren, indem Sie mit den nativen UI-Framework-Stil. Z. B. in HTML-Code können Sie CSS-Klassen für den HTML-Code angeben, oder in XAML können Sie in einem benutzerdefinierten ResourceDictionary übergeben, für eine präzisere Kontrolle der Ausgabe.

### <a name="customize-per-element-rendering"></a>Anpassen von pro Element-Textrendering

Jedes SDK können Sie das Rendering eines Elements zu überschreiben oder sogar Hinzufügen von Unterstützung für völlig neue Elemente, die Sie definieren.  Sie können z. B. Ändern der `Input.Date` Renderer, Ihr eigenes benutzerdefinierte Steuerelement auszugeben, ohne dabei den Rest der Ausgabe des Renderers. Oder Sie können Unterstützung für ein benutzerdefiniertes hinzufügen `Rating` -Element, das Sie definieren.



