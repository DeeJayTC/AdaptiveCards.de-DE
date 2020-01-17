---
title: Host config-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 554b32d9d088e82fb0fd48bec4b94340e843abeb
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146124"
---
# <a name="host-config---android"></a><span data-ttu-id="f139d-102">Host Konfiguration-Android</span><span class="sxs-lookup"><span data-stu-id="f139d-102">Host config - Android</span></span>

<span data-ttu-id="f139d-103">Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="f139d-103">To customize the renderer you provide an instance of the HostConfig object.</span></span> <span data-ttu-id="f139d-104">(Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../../rendering-cards/host-config.md) .)</span><span class="sxs-lookup"><span data-stu-id="f139d-104">(See [Host Config Schema](../../../../rendering-cards/host-config.md) for the full description.)</span></span>

<span data-ttu-id="f139d-105">Um ein ```HostConfig```-Objekt aus einer Zeichenfolge zu erstellen, verwenden Sie die ```DeserializeFromString```-Methode wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f139d-105">To create a ```HostConfig``` object from a string, use the ```DeserializeFromString``` method like this:</span></span>

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

HostConfig Config = HostConfig.DeserializeFromString(configJson);
```