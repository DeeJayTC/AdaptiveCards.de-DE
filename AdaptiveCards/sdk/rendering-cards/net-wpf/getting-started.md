---
title: .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: a3f63fc812c97014af06dd1a197b24c5d07361c2
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553622"
---
# <a name="getting-started---net-wpf"></a>Erste Schritte – WPF für .NET

Wie wir im beschrieben [Einstieg](../../../authoring-cards/getting-started.md) Seite eine Adaptive Card ist ein JSON-serialisierten Karte-Objektmodell. Diese Bibliothek erleichtert es, diesen JSON-Code in WPF-UI zu rendern, die Sie in Ihrer app verwenden können.

## <a name="nuget-install"></a>Installieren von NuGet

[![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a>Verbesserte Eingabepaket für Xceed

Diese optionale Paket verbessert die Adaptive Card-Input-Steuerelemente über die WPF standardmäßig bietet. Es besteht eine Abhängigkeit `Extended.Wpf.Toolkit`

[![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a>Beispiel für WPF-Schnellansicht

![Screenshot der Schnellansicht](../../../resources/media/tools/wpfvisualizer.png)

Die [WPF-Schnellansicht Beispiel](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) können Sie Karten mit WPF visuell darstellen.  Ein `Host Config` Editor zum Bearbeiten und Anzeigen von Host-Konfigurationseinstellungen integriert ist. Speichern Sie diese Einstellungen als JSON, sie in das Rendering in Ihrer Anwendung verwenden.

## <a name="next-steps"></a>Nächste Schritte

Finden Sie unter [rendern eine Karte](render-a-card.md) für die nächsten Schritte.
