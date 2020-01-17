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
# <a name="cardrendererregistration"></a><span data-ttu-id="4d8a5-102">Cardrendererregistration</span><span class="sxs-lookup"><span data-stu-id="4d8a5-102">CardRendererRegistration</span></span>

```csharp
public class CardRendererRegistration : Java.Lang.Object
```

<span data-ttu-id="4d8a5-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="4d8a5-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.Renderer.Registration
```

### <a name="summary"></a><span data-ttu-id="4d8a5-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="4d8a5-104">Summary</span></span>

| <span data-ttu-id="4d8a5-105">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="4d8a5-105">Public methods</span></span> | |
| --- | ---- |
| ```void``` | [```RegisterFeatureRegistration (FeatureRegistration featureRegistration)```](#registerfeatureregistration) |

## <a name="public-methods"></a><span data-ttu-id="4d8a5-106">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="4d8a5-106">Public Methods</span></span>

--- 

### <a id="registerfeatureregistration"></a><span data-ttu-id="4d8a5-107">Registerfeatureregistration</span><span class="sxs-lookup"><span data-stu-id="4d8a5-107">RegisterFeatureRegistration</span></span>
<p style='text-align:right'><span data-ttu-id="4d8a5-108">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="4d8a5-108">Added in version 0.1.0</span></span></p>

```csharp
public void RegisterFeatureRegistration (FeatureRegistration featureRegistration)
```

<span data-ttu-id="4d8a5-109">Registriert ein [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) -Objekt, das der Karten-Renderer verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="4d8a5-109">Registers a [```FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) object for the card renderer to use.</span></span>

| <span data-ttu-id="4d8a5-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d8a5-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="4d8a5-111">featureregistration</span><span class="sxs-lookup"><span data-stu-id="4d8a5-111">featureRegistration</span></span> | [```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.FeatureRegistration```](adaptivecards-rendering-xamarin-android-objectmodel-featureregistration.md) |

#### <a name="sample"></a><span data-ttu-id="4d8a5-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d8a5-112">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```