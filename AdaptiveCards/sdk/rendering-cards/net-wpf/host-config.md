---
title: Hostkonfiguration – .NET WPF SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 9ca540cbbb445f306f073f1936af46f8c2def99b
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134307"
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
