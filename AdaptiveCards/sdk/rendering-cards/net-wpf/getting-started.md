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
# <a name="getting-started---net-wpf"></a><span data-ttu-id="c045d-102">Erste Schritte – WPF für .NET</span><span class="sxs-lookup"><span data-stu-id="c045d-102">Getting started - .NET WPF</span></span>

<span data-ttu-id="c045d-103">Wie wir im beschrieben [Einstieg](../../../authoring-cards/getting-started.md) Seite eine Adaptive Card ist ein JSON-serialisierten Karte-Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="c045d-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="c045d-104">Diese Bibliothek erleichtert es, diesen JSON-Code in WPF-UI zu rendern, die Sie in Ihrer app verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c045d-104">This library makes it easy to render that JSON into WPF UI that you can use within your app.</span></span>

## <a name="nuget-install"></a><span data-ttu-id="c045d-105">Installieren von NuGet</span><span class="sxs-lookup"><span data-stu-id="c045d-105">NuGet install</span></span>

<span data-ttu-id="c045d-106">[![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span><span class="sxs-lookup"><span data-stu-id="c045d-106">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a><span data-ttu-id="c045d-107">Verbesserte Eingabepaket für Xceed</span><span class="sxs-lookup"><span data-stu-id="c045d-107">Xceed enhanced input package</span></span>

<span data-ttu-id="c045d-108">Diese optionale Paket verbessert die Adaptive Card-Input-Steuerelemente über die WPF standardmäßig bietet.</span><span class="sxs-lookup"><span data-stu-id="c045d-108">This optional package enhances the Adaptive Card Input controls beyond what WPF provides out of the box.</span></span> <span data-ttu-id="c045d-109">Es besteht eine Abhängigkeit `Extended.Wpf.Toolkit`</span><span class="sxs-lookup"><span data-stu-id="c045d-109">It has a dependency on `Extended.Wpf.Toolkit`</span></span>

<span data-ttu-id="c045d-110">[![Installieren von NuGet](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span><span class="sxs-lookup"><span data-stu-id="c045d-110">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="c045d-111">Beispiel für WPF-Schnellansicht</span><span class="sxs-lookup"><span data-stu-id="c045d-111">WPF Visualizer Sample</span></span>

![Screenshot der Schnellansicht](../../../resources/media/tools/wpfvisualizer.png)

<span data-ttu-id="c045d-113">Die [WPF-Schnellansicht Beispiel](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) können Sie Karten mit WPF visuell darstellen.</span><span class="sxs-lookup"><span data-stu-id="c045d-113">The [WPF Visualizer sample](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF.</span></span>  <span data-ttu-id="c045d-114">Ein `Host Config` Editor zum Bearbeiten und Anzeigen von Host-Konfigurationseinstellungen integriert ist.</span><span class="sxs-lookup"><span data-stu-id="c045d-114">A `Host Config` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="c045d-115">Speichern Sie diese Einstellungen als JSON, sie in das Rendering in Ihrer Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c045d-115">Save these settings as a JSON to use them in rendering in your application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c045d-116">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c045d-116">Next steps</span></span>

<span data-ttu-id="c045d-117">Finden Sie unter [rendern eine Karte](render-a-card.md) für die nächsten Schritte.</span><span class="sxs-lookup"><span data-stu-id="c045d-117">See [Render a card](render-a-card.md) for the next steps!</span></span>
