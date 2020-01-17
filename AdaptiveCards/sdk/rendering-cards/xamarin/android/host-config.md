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
# <a name="host-config---android"></a>Host Konfiguration-Android

Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an. (Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../../rendering-cards/host-config.md) .)

Um ein ```HostConfig```-Objekt aus einer Zeichenfolge zu erstellen, verwenden Sie die ```DeserializeFromString```-Methode wie folgt:

```csharp
using AdaptiveCards.Rendering.Xamarin.Android.ObjectModel;
// ...

HostConfig Config = HostConfig.DeserializeFromString(configJson);
```