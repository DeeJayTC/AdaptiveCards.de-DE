---
title: 'Host Konfiguration: .net html SDK'
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: a51b64f5f9783a187d7c3eb56c563a1d4497d3e2
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454993"
---
# <a name="host-config---net-html"></a>Host Konfiguration: .net-html

Eine [Hostkonfiguration](../../../rendering-cards/host-config.md) ist ein gemeinsam genutztes Konfigurationsobjekt, das von allen Renderern verstanden wird. Dadurch kannst du allgemeine Formatvorlagen (z. B. Schriftfamilie, Schriftgrad, Standardabstand) und Verhaltensweisen (z. B. die maximale Anzahl von Aktionen) definieren, die von jedem Plattformrenderer automatisch interpretiert werden. 

Das Ziel besteht darin, dass die von jedem Plattformrenderer generierte native Benutzeroberfläche ähnlich aussieht und dein Aufwand hierfür nur gering ist.

```csharp
// Construct programmatically
renderer.HostConfig = new AdaptiveHostConfig() 
{
    FontFamily = "Comic Sans",
    FontSizes = {
        Small = 15,
        Default = 20,
        Medium = 25,
        Large = 30,
        ExtraLarge= 40
    }
};

// Or parse from JSON
renderer.HostConfig  = AdaptiveHostConfig.FromJson(@"{
    ""fontFamily"": ""Comic Sans"",
    ""fontSizes"": {
        ""small"": 25,
        ""default"": 26,
        ""medium"": 27,
        ""large"": 28,
        ""extraLarge"": 29
    }
}");
```