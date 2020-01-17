---
title: Adaptivecardrenderer-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: c90fb22f60fa75a37b6372c2660f8599535fd961
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146064"
---
# <a name="adaptivecardrenderer"></a>Adaptivecardrenderer

```csharp
public class AdaptiveCardRenderer : global::Java.Lang.Object
```

**Namespace**
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer
```

### <a name="summary"></a>Zusammenfassung

| Öffentliche Methoden | |
| --- | ---- |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler)```](#render0) |
| ```RenderedAdaptiveCard``` | [```Render (Context context, FragmentManager fragmentManager, AdaptiveCard adaptiveCard, ICardActionHandler cardActionHandler, HostConfig hostConfig)```](#render1) |

## <a name="public-methods"></a>Öffentliche Methoden

---

### <a id="render0"></a>Bieten
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public RenderedAdaptiveCard Render (Context context, 
                                    FragmentManager fragmentManager, 
                                    AdaptiveCard adaptiveCard,
                                    ICardActionHandler cardActionHandler)
```

Rendert die angegebene Adaptive Karte mit Standardwerten für die Host Konfiguration.

| Parameter | |
| --- | --- |
| context | ```Android.Content.Context``` |
| fragmentmanager | ```Android.Support.V4.App.FragmentManager``` |
| adaptivecard | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| cardhandhandler | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |

| Rückgabe |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a>Beispiel

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler);
```

---

### <a id="render1"></a>Bieten
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
RenderedAdaptiveCard Render (Context context, 
                            FragmentManager fragmentManager, 
                            AdaptiveCard adaptiveCard, 
                            ICardActionHandler cardActionHandler, 
                            HostConfig hostConfig)
```

Rendert die angegebene Adaptive Karte mithilfe der angegebenen Host Konfiguration.

| Parameter | |
| --- | --- |
| context | ```Android.Content.Context``` |
| fragmentmanager | ```Android.Support.V4.App.FragmentManager``` |
| adaptivecard | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard```](adaptivecards-rendering-xamarin-android-objectmodel-adaptivecard.md) |
| cardhandhandler | [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.ActionHandler.ICardActionHandler```](adaptivecards-renderin-xamarin-android-renderer-actionhandler-icardactionhandler.md) |
| hostconfig | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HostConfig``` |

| Rückgabe | |
| --- | --- |
| [```AdaptiveCards.Rendering.Xamarin.Android.Renderer.RenderedAdaptiveCard```](adaptivecards-rendering-xamarin-android-renderer-renderedadaptivecard.md) | |

#### <a name="sample"></a>Beispiel

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.Instance.Render(context, SupportFragmentManager, parseResult.AdaptiveCard, cardActionHandler, hostConfig);
```