---
title: Renderedadaptivecard-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 608b28638ce6ed0a218cfc8dbbe73f22de1ab8cb
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145994"
---
# <a name="renderedadaptivecard"></a>Renderedadaptivecard

```csharp
public class RenderedAdaptiveCard : Java.Lang.Object
```

**Namespace**

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a>Zusammenfassung

| Attribute | |
| ---- | --- |
| AdaptiveCard | Logische Darstellung der gerenderten adaptiven Karte. |
| Eingaben | Das Wörterbuch des Eingabe Elements und der vom Benutzer hinzugefügten Informationen. |
| „Ansicht” | Visuelles Ergebnis aus dem Renderingprozess. |
| Warnungen | Liste der Warnungen, die vom Renderingprozess erzeugt werden. |

&nbsp;

| Öffentliche Methoden | |
| --- | ---- |
| ```void``` | [```AddWarning AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning warning)```](#addwarning) |

## <a name="public-methods"></a>Öffentliche Methoden

---

### <a id="addwarning"></a>Addwarning
<p style='text-align:right'>In Version 0,1 hinzugefügt</p>

```csharp
public void AddWarning (AdaptiveWarning warning)

```

Fügt der Warnungs Liste eine Warnung hinzu.

| Parameter | |
| --- | --- |
| Warnung | ```AdaptiveCards.Rendering.Xamarin.Android.Renderer.AdaptiveWarning``` |
