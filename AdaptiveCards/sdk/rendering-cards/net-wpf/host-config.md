---
title: Hostkonfiguration – .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 65e68c2c3e7fa244ba790afc3749912937ea8470
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454033"
---
# <a name="host-config---net-wpf"></a>Hostkonfiguration – .NET WPF

Eine [Hostkonfiguration](../../../rendering-cards/host-config.md) ist ein gemeinsam genutztes Konfigurationsobjekt, das von allen Renderern verstanden wird. Dadurch kannst du allgemeine Formatvorlagen (z. B. Schriftfamilie, Schriftgrad, Standardabstand) und Verhaltensweisen (z. B. die maximale Anzahl von Aktionen) definieren, die von jedem Plattformrenderer automatisch interpretiert werden. 

Das Ziel besteht darin, dass die von jedem Plattformrenderer generierte native Benutzeroberfläche ähnlich aussieht und dein Aufwand hierfür nur gering ist.

```csharp
// Construct programmatically
renderer.HostConfig = new AdaptiveHostConfig()
{
    FontStyles = new FontStylesConfig()
    {
        Default = new FontStyleConfig()
        {
            FontFamily = "Consolas",
            FontSizes = {
                Small = 15,
                Default = 20,
                Medium = 25,
                Large = 30,
                ExtraLarge= 40
            }
        },
    }
};

// Or parse from JSON
renderer.HostConfig = AdaptiveHostConfig.FromJson(@"{
    ""fontStyles"": {
        ""default"": {
            ""fontFamily"": ""Consolas"",
            ""fontSizes"": {
                ""small"": 15,
                ""default"": 20,
                ""medium"": 25,
                ""large"": 30,
                ""extraLarge"": 40
            }
        }
    }}");
```
