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
# <a name="feature-registration"></a>Funktions Registrierung

```csharp
public class FeatureRegistration : Java.Lang.Object 
```

**Namespace**
```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a>Zusammenfassung

| Öffentliche Methoden | |
| --- | ---- |
| ```void``` | [```AddFeature(string featureName, string featureVersion)```](#addfeature) |
| ```string``` | [```GetFeatureVersion(string featureName)```](#getfeatureversion) |
| ```void``` | [```RemoveFeature (string featureName)```](#removefeature) |

## <a name="public-methods"></a>Öffentliche Methoden

---

### <a id="addfeature"></a>Addfeature
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public void AddFeature (string featureName, 
                        string featureVersion)
```

Fügt der rendererfunktionsregistrierung eine Funktion mit dem Namen und der Version hinzu.

| Parameter | |
| --- | --- |
| featureName | ```string``` |
| Featureversion | ```string``` |

#### <a name="sample"></a>Beispiel

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
CardRendererRegistration.Instance.RegisterFeatureRegistration(featureRegistration);
```

---

### <a id="getfeatureversion"></a>Getfeatureversion
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public string GetFeatureVersion (string featureName)
```

Ruft die Version für eine angegebene Funktion ab. 

| Parameter | |
| --- | --- |
| featureName | ```string``` |

| Rückgabe | |
| --- | --- |
| ```string``` | Funktions Version für die angegebene Funktion |

#### <a name="sample"></a>Beispiel

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
string featureVersion = featureRegistration.GetFeatureVersion("MyFeature"); // 1.2.0
```

---

### <a id="removefeature"></a>Removefeature
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public void RemoveFeature (string featureName)
```

Entfernt die angegebene Funktion aus dem Funktions Wörterbuch.

| Parameter | |
| --- | --- |
| featureName | ```string``` |

#### <a name="sample"></a>Beispiel

```csharp
FeatureRegistration featureRegistration = new FeatureRegistration();
featureRegistration.AddFeature("MyFeature", "1.2.0");
featureRegistration.RemoveFeature("MyFeature");
```