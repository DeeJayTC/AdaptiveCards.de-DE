---
title: Rendern von Karten in der Anwendung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 0a5f99268ce483fddd99f4493b386db796c3e9d2
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138093"
---
# <a name="rendering-cards-inside-your-application"></a>Rendern von Karten in der Anwendung

Das Rendern von adaptiven Karten in deiner Anwendung ist ganz einfach. Wir stellen SDKs für alle gängigen Plattformen sowie eine [detaillierte Spezifikation](implement-a-renderer.md) bereit, damit du einen eigenen Renderer für adaptive Karten erstellen kannst.

1. **Installiere ein Renderer-SDK** für deine Zielplattform.
2. **Erstelle eine Rendererinstanz**, die mit dem Stil, den Regeln und den Aktionsereignishandlern deiner App konfiguriert ist.
3. **Rendere eine Karte auf der nativen Benutzeroberfläche**, die automatisch den Stil deiner App aufweist.

## <a name="adaptive-cards-sdks"></a>SDKs für adaptive Karten

|Plattform|Installieren|Version|Dokumentation|Status|
|---|---|---|---|---|
| JavaScript | [![npm-Installation](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/nodejs)| [Dokumentation](../sdk/rendering-cards/javascript/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20564.svg) |
| .NET WPF | [![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet)| [Dokumentation](../sdk/rendering-cards/net-wpf/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| .NET HTML | [![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Html.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Html) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet) | [Dokumentation](../sdk/rendering-cards/net-html/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20596.svg) |
| Universelle Windows-Plattform | [![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Uwp.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Uwp) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/uwp) | [Dokumentation](../sdk/rendering-cards/uwp/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/56cf629e-8f3a-4412-acbc-bf69366c552c/20583.svg) |
| Android | [![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/android) | [Dokumentation](../sdk/rendering-cards/android/getting-started.md) | ![Buildstatus](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/17651.svg)
| iOS | [![CocoaPods](https://img.shields.io/cocoapods/v/AdaptiveCards.svg)](https://cocoapods.org/pods/AdaptiveCards) | [Quelle](https://github.com/Microsoft/AdaptiveCards/tree/master/source/ios) | [Dokumentation](../sdk/rendering-cards/ios/getting-started.md) |  ![Buildstatus](https://img.shields.io/vso/build/Microsoft/8d47e068-03c8-4cdc-aa9b-fc6929290322/16990.svg) |

## <a name="create-an-instance-of-the-renderer"></a>Erstellen einer Instanz der Renderers

Der nächste Schritt besteht darin, eine `AdaptiveCardRenderer`-Instanz zu erstellen. 

### <a name="hook-up-action-events"></a>Ankoppeln von Aktionselementen

Aktionen werden standardmäßig als Schaltflächen auf der Karte gerendert, allerdings obliegt es deiner App, für ein ordnungsgemäßes Verhalten zu sorgen. Jedes SDK verfügt über das Äquivalent eines `OnAction`-Ereignisses, die verarbeitet werden müssen.

* **Action.OpenUrl**: Öffnet die angegebene `url`.  
* **Action.Submit**: Akzeptiert das Ergebnis der Übermittlung und sendet es an die Quelle. Wie du das Ergebnis an die Quelle der Karte sendest, liegt allein in deinem Ermessen.
* **Action.ShowCard**: Ruft ein Dialogfeld auf und rendert die untergeordnete Karte in diesem Dialogfeld. Beachte, dass du dies nur verarbeiten musst, wenn `ShowCardActionMode` auf `popup` festgelegt ist.

## <a name="render-a-card"></a>Rendern einer Karte

Nach dem Abrufen einer Kartennutzlast rufst du einfach den Renderer auf und übergibst die Karte. Du erhältst ein natives Benutzeroberflächenobjekt, das aus den Karteninhalten besteht. Diese Benutzeroberfläche fügst du jetzt in deine App ein.

## <a name="customization"></a>Anpassung

Es gibt verschiedene Möglichkeiten, die Renderausgabe anzupassen. 

### <a name="hostconfig"></a>HostConfig

Eine [HostConfig](host-config.md) ist ein gemeinsam genutztes, plattformübergreifendes Konfigurationsobjekt, das die grundlegende Formatierung und das grundlegende Verhalten von Karten innerhalb deiner App steuert. Es definiert Aspekte wie Schriftgrößen, den Abstand zwischen Elementen, Farben, die Anzahl von unterstützten Aktionen usw. 

### <a name="native-platform-styling"></a>Native Plattformformatierung

In den meisten UI-Frameworks kannst du die gerenderte Karte mithilfe des nativen Stils des UI-Frameworks formatieren. In HTML kannst du z. B. CSS-Klassen für die HTML-Ausgabe angeben, in XAML kannst du ein benutzerdefiniertes ResourceDictionary übergeben, um die Ausgabe differenziert zu steuern.

### <a name="customize-per-element-rendering"></a>Anpassen des Renderns einzelner Elemente

Jedes SDK ermöglicht es, das Rendern eines beliebigen Objekts zu überschreiben oder sogar Unterstützung für vollständig neue, von dir definierte Elemente hinzuzufügen.  Du kannst z. B. den `Input.Date`-Renderer so ändern, dass dein eigenes benutzerdefiniertes Steuerelement ausgegeben wird, die restliche Ausgabe des Renderers aber unverändert bleibt. Du kannst auch Unterstützung für ein von dir definiertes `Rating`-Element hinzufügen.



