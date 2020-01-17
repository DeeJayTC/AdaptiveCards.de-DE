---
title: Cardrendererregistration-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 4254c1c3c0f275434fae2a92e20679b6fa136b16
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145984"
---
# <a name="cardrendererregistration"></a>Cardrendererregistration

```csharp
public class CardRendererRegistration : Java.Lang.Object
```

**Namespace**
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer.Registration
```

### <a name="summary"></a>Zusammenfassung

| Öffentliche Methoden | |
| --- | ---- |
| ```void``` | [```RegisterFeatureRegistration (FeatureRegistration featureRegistration)```](#registerfeatureregistration) |

## <a name="public-methods"></a>Öffentliche Methoden

--- 

### <a id="registerfeatureregistration"></a>Registerfeatureregistration
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public void RegisterFeatureRegistration (FeatureRegistration featureRegistration)
```

Registriert ein [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) -Objekt, das der Karten-Renderer verwenden soll.

| Parameter | |
| --- | --- |
| featureregistration | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) |

#### <a name="sample"></a>Beispiel

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```