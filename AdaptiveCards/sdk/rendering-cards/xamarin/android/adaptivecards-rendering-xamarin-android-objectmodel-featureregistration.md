---
title: Featureregistration-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: c1975197996e54626b464abe9181f0b02895ee4d
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146144"
---
# <a name="feature-registration"></a><span data-ttu-id="c54af-102">Funktions Registrierung</span><span class="sxs-lookup"><span data-stu-id="c54af-102">Feature Registration</span></span>

```csharp
public class FeatureRegistration : Java.Lang.Object 
```

<span data-ttu-id="c54af-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="c54af-103">**Namespace**</span></span>
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a><span data-ttu-id="c54af-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="c54af-104">Summary</span></span>

| <span data-ttu-id="c54af-105">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="c54af-105">Public methods</span></span> | |
| --- | ---- |
| ```void``` | [```AddFeature(string featureName, string featureVersion)```](#addfeature) |
| ```string``` | [```GetFeatureVersion(string featureName)```](#getfeatureversion) |
| ```void``` | [```RemoveFeature (string featureName)```](#removefeature) |

## <a name="public-methods"></a><span data-ttu-id="c54af-106">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="c54af-106">Public Methods</span></span>

---

### <a id="addfeature"></a><span data-ttu-id="c54af-107">Addfeature</span><span class="sxs-lookup"><span data-stu-id="c54af-107">AddFeature</span></span>
<p style='text-align:right'><span data-ttu-id="c54af-108">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c54af-108">Added in version 0.1.0</span></span></p>

```csharp
public void AddFeature (string featureName, 
                        string featureVersion)
```

<span data-ttu-id="c54af-109">Fügt der rendererfunktionsregistrierung eine Funktion mit dem Namen und der Version hinzu.</span><span class="sxs-lookup"><span data-stu-id="c54af-109">Adds a feature containing its name and version to the renderer feature registration.</span></span>

| <span data-ttu-id="c54af-110">Parameter</span><span class="sxs-lookup"><span data-stu-id="c54af-110">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="c54af-111">featureName</span><span class="sxs-lookup"><span data-stu-id="c54af-111">featureName</span></span> | ```string``` |
| <span data-ttu-id="c54af-112">Featureversion</span><span class="sxs-lookup"><span data-stu-id="c54af-112">featureVersion</span></span> | ```string``` |

#### <a name="sample"></a><span data-ttu-id="c54af-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54af-113">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```

---

### <a id="getfeatureversion"></a><span data-ttu-id="c54af-114">Getfeatureversion</span><span class="sxs-lookup"><span data-stu-id="c54af-114">GetFeatureVersion</span></span>
<p style='text-align:right'><span data-ttu-id="c54af-115">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c54af-115">Added in version 0.1.0</span></span></p>

```csharp
public string GetFeatureVersion (string featureName)
```

<span data-ttu-id="c54af-116">Ruft die Version für eine angegebene Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="c54af-116">Retrieves the version for a given feature.</span></span> 

| <span data-ttu-id="c54af-117">Parameter</span><span class="sxs-lookup"><span data-stu-id="c54af-117">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="c54af-118">featureName</span><span class="sxs-lookup"><span data-stu-id="c54af-118">featureName</span></span> | ```string``` |

| <span data-ttu-id="c54af-119">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="c54af-119">Returns</span></span> | |
| --- | --- |
| ```string``` | <span data-ttu-id="c54af-120">Funktions Version für die angegebene Funktion</span><span class="sxs-lookup"><span data-stu-id="c54af-120">Feature version for the given feature</span></span> |

#### <a name="sample"></a><span data-ttu-id="c54af-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54af-121">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
string featureVersion = featureRegistration.GetFeatureVersion("MyFeature"); // 1.2.0
```

---

### <a id="removefeature"></a><span data-ttu-id="c54af-122">Removefeature</span><span class="sxs-lookup"><span data-stu-id="c54af-122">RemoveFeature</span></span>
<p style='text-align:right'><span data-ttu-id="c54af-123">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="c54af-123">Added in version 0.1.0</span></span></p>

```csharp
public void RemoveFeature (string featureName)
```

<span data-ttu-id="c54af-124">Entfernt die angegebene Funktion aus dem Funktions Wörterbuch.</span><span class="sxs-lookup"><span data-stu-id="c54af-124">Removes the given feature from the feature dictionary.</span></span>

| <span data-ttu-id="c54af-125">Parameter</span><span class="sxs-lookup"><span data-stu-id="c54af-125">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="c54af-126">featureName</span><span class="sxs-lookup"><span data-stu-id="c54af-126">featureName</span></span> | ```string``` |

#### <a name="sample"></a><span data-ttu-id="c54af-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c54af-127">Sample</span></span>

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
featureRegistration.RemoveFeature("MyFeature");
```