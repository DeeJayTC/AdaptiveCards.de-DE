---
title: Host-Konfiguration – .NET WPF-SDK
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: c3414860ee9822a02dbf36ff11fd83488fedf34e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552912"
---
# <a name="host-config---net-wpf"></a>Host-Konfiguration – WPF für .NET

Ein [Hosts Config](../../../rendering-cards/host-config.md) ist eine Konfiguration für shared-Objekt, das Verstehen von allen Renderern. Dadurch können Sie allgemeine Formatvorlagen (z. B. Schriftfamilie, Schriftgrößen, Abstände Standard) und Verhaltensweisen (z. B. maximale Anzahl von Aktionen), die automatisch mit jeder Plattform Renderer interpretiert werden, zu definieren. 

Das Ziel ist, dass von jeder Plattform Renderer generierten systemeigene Benutzeroberfläche sehr ähnlich, mit minimalem Aufwand ihrerseits aussieht.

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