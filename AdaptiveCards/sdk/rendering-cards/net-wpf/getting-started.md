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
# <a name="getting-started---net-wpf"></a><span data-ttu-id="cb14f-102">Getting Started (.net WPF)</span><span class="sxs-lookup"><span data-stu-id="cb14f-102">Getting started - .NET WPF</span></span>

<span data-ttu-id="cb14f-103">Wie auf der Seite mit den ersten Schritten beschrieben, handelt es sich bei einer adaptiven [Karte um ein](../../../authoring-cards/getting-started.md) JSON-serialisiertes Karten Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="cb14f-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="cb14f-104">Diese Bibliothek erleichtert das Rendering dieses JSON-Code in der WPF-Benutzeroberfläche, die Sie in Ihrer APP verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cb14f-104">This library makes it easy to render that JSON into WPF UI that you can use within your app.</span></span>

## <a name="nuget-install"></a><span data-ttu-id="cb14f-105">Nuget-Installation</span><span class="sxs-lookup"><span data-stu-id="cb14f-105">NuGet install</span></span>

<span data-ttu-id="cb14f-106">[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span><span class="sxs-lookup"><span data-stu-id="cb14f-106">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf
```

### <a name="xceed-enhanced-input-package"></a><span data-ttu-id="cb14f-107">Xceed Enhanced Input Package</span><span class="sxs-lookup"><span data-stu-id="cb14f-107">Xceed enhanced input package</span></span>

<span data-ttu-id="cb14f-108">Mithilfe dieses optionalen Pakets werden die Eingabesteuerelemente der adaptiven Karte erweitert, die über die Standard-WPF hinausgehen.</span><span class="sxs-lookup"><span data-stu-id="cb14f-108">This optional package enhances the Adaptive Card Input controls beyond what WPF provides out of the box.</span></span> <span data-ttu-id="cb14f-109">Sie hat eine Abhängigkeit von `Extended.Wpf.Toolkit`</span><span class="sxs-lookup"><span data-stu-id="cb14f-109">It has a dependency on `Extended.Wpf.Toolkit`</span></span>

<span data-ttu-id="cb14f-110">[![NuGet-Installation](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span><span class="sxs-lookup"><span data-stu-id="cb14f-110">[![Nuget install](https://img.shields.io/nuget/vpre/AdaptiveCards.Rendering.Wpf.Xceed.svg)](https://www.nuget.org/packages/AdaptiveCards.Rendering.Wpf.Xceed)</span></span>

```console
Install-Package AdaptiveCards.Rendering.Wpf.Xceed
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="cb14f-111">Beispiel: WPF-Visualisierer</span><span class="sxs-lookup"><span data-stu-id="cb14f-111">WPF Visualizer Sample</span></span>

![Bildschirm Abbildung von Visualisierungen](../../../resources/media/tools/wpfvisualizer.png)

<span data-ttu-id="cb14f-113">Mit dem Beispiel für eine [WPF](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) -Schnellansicht können Sie Karten mithilfe von WPF visualisieren.</span><span class="sxs-lookup"><span data-stu-id="cb14f-113">The [WPF Visualizer sample](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF.</span></span>  <span data-ttu-id="cb14f-114">Ein `Host Config`-Editor ist zum Bearbeiten und Anzeigen von Hostkonfigurationseinstellungen integriert.</span><span class="sxs-lookup"><span data-stu-id="cb14f-114">A `Host Config` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="cb14f-115">Speichere diese Einstellungen als JSON, um sie zum Rendern in deiner Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb14f-115">Save these settings as a JSON to use them in rendering in your application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb14f-116">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cb14f-116">Next steps</span></span>

<span data-ttu-id="cb14f-117">Informationen zu den nächsten Schritten findest du unter [Rendern einer Karte](render-a-card.md).</span><span class="sxs-lookup"><span data-stu-id="cb14f-117">See [Render a card](render-a-card.md) for the next steps!</span></span>
