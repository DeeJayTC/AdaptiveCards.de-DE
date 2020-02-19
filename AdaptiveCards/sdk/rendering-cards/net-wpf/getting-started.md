---
title: .net WPF-SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 999f8ac3cd6a18fbbfc8b8bbdcf47465d8bb314f
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454283"
---
# <a name="getting-started---net-wpf"></a>Getting Started (.net WPF)

Wie auf der Seite mit den ersten Schritten beschrieben, handelt es sich bei einer adaptiven [Karte um ein](../../../authoring-cards/getting-started.md) JSON-serialisiertes Karten Objektmodell. Diese Bibliothek erleichtert das Rendering dieses JSON-Code in der WPF-Benutzeroberfläche, die Sie in Ihrer APP verwenden können.

## <a name="nuget-install"></a>Nuget-Installation

[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a>Xceed Enhanced Input Package

Mithilfe dieses optionalen Pakets werden die Eingabesteuerelemente der adaptiven Karte erweitert, die über die Standard-WPF hinausgehen. Sie hat eine Abhängigkeit von `Extended.Wpf.Toolkit`

[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a>Beispiel: WPF-Visualisierer

![Bildschirm Abbildung von Visualisierungen](../../../resources/media/tools/wpfvisualizer.png)

Mit dem Beispiel für eine [WPF](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) -Schnellansicht können Sie Karten mithilfe von WPF visualisieren.  Ein `Host Config`-Editor ist zum Bearbeiten und Anzeigen von Hostkonfigurationseinstellungen integriert. Speichere diese Einstellungen als JSON, um sie zum Rendern in deiner Anwendung zu verwenden.

## <a name="next-steps"></a>Nächste Schritte

Informationen zu den nächsten Schritten findest du unter [Rendern einer Karte](render-a-card.md).
