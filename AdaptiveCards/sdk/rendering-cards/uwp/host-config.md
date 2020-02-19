---
title: Host Konfiguration-UWP SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 6f14830a643b064c6169cf3143bbc7cd4ce45937
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454973"
---
# <a name="host-config---uwp"></a><span data-ttu-id="bee0d-102">Host Konfiguration-UWP</span><span class="sxs-lookup"><span data-stu-id="bee0d-102">Host config - UWP</span></span>

<span data-ttu-id="bee0d-103">Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="bee0d-103">To customize the renderer you provide an instance of the HostConfig object.</span></span> <span data-ttu-id="bee0d-104">(Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../rendering-cards/host-config.md) .)</span><span class="sxs-lookup"><span data-stu-id="bee0d-104">(See [Host Config Schema](../../../rendering-cards/host-config.md) for the full description.)</span></span>

> <span data-ttu-id="bee0d-105">Das hostconfig-Objekt wird mit Standardwerten instanziiert, sodass Sie nur die Eigenschaften festlegen können, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="bee0d-105">The HostConfig object will be instantiated with defaults, so you can set just the properties you want to change.</span></span>

<span data-ttu-id="bee0d-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bee0d-106">Example:</span></span>

```csharp
var hostConfig = new AdaptiveHostConfig() 
{
    FontSizes = {
        Small = 15,
        Normal = 20,
        Medium = 25,
        Large = 30,
        ExtraLarge= 40
    }
};
renderer.HostConfig = hostConfig;
```

> <span data-ttu-id="bee0d-107">Alternativ können Sie die hostconfig aus einer JSON-Zeichenfolge laden.</span><span class="sxs-lookup"><span data-stu-id="bee0d-107">Alternatively, you can load the HostConfig from a JSON string.</span></span>

<span data-ttu-id="bee0d-108">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bee0d-108">Example:</span></span>

```csharp
var hostConfig = AdaptiveHostConfig.FromJsonString(jsonString); 

renderer.HostConfig = hostConfig;
```

<span data-ttu-id="bee0d-109">Wenn Sie Sie an den uwprenderer übergeben, legen Sie die Standard Host Konfiguration fest, die für jede von Ihnen renderkarte verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bee0d-109">When you pass it in to the UWPRenderer you are setting the default HostConfig to use for every card you render.</span></span>