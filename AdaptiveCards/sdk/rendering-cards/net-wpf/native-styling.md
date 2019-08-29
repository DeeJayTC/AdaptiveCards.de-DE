---
title: 'Native Formatierung: .net WPF SDK'
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: ee5bec1a11f39ad69d40e57410c105b50ba45981
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552722"
---
# <a name="native-styling---net-wpf"></a>Native Formatierung: .net WPF

Obwohl die Host Konfiguration den größten Teil der einzelnen Plattformen bietet, ist es wahrscheinlich, dass Sie auf jeder Plattform eine native Formatierung ausführen müssen. 

WPF vereinfacht dies, indem es Ihnen ermöglicht wird, ein ResourceDictionary für differenzierte Formatierung, Verhalten, Animationen usw. zu übergeben.

| Element | Stilnamen |
|---|---|
| AdaptiveCard | Adaptive.Card| 
| Action.OpenUrl  | Adaptive.Action.OpenUrl  |
| Action. showcard | Adaptive.Action.ShowCard |
| Aktion. übermitteln  | Adaptive.Action.Submit  |
| Spalte | Adaptive. Column, Adaptive. Action. Tap |
| ColumnSet | Adaptive.ColumnSet, Adaptive.VerticalSeparator |
| Container | Adaptive. Container|
| Input.ChoiceSet | Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem |
| Input. Date | Adaptive.Input.Text.Date
| Eingabe. Zahl | Adaptive.Input.Text.Number |
| Input.Text | Adaptive. Input. Text |
| Eingabe. Zeit | Adaptive.Input.Text.Time |
| Eingabe. Umschalten| Adaptive.Input.Toggle|
| Bild  | Adaptive. Image |
| ImageSet  | Adaptive.ImageSet |
| FactSet | Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value |
| TextBlock  | Adaptive.TextBlock |

Dieses Beispiel-XAML-Ressourcen Wörterbuch, das den Hintergrund aller Textblöcke auf Aqua festlegt. Wahrscheinlich möchten Sie etwas höher als dieses😁

```xml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" 
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
    <Style x:Key="Adaptive.TextBlock" TargetType="TextBlock">
        <Setter Property="Background" Value="Aqua"></Setter>
    </Style>
</ResourceDictionary>
```
```csharp
// Use a ResourceDictionary instance
// DON'T use this property if rendering from a server
renderer.Resources = myResourceDictionary;

// ... or load it from a file path
// USE this if rendering from a server
renderer.ResourcesPath = <path-to-my-resource-dictionary.xaml>;
```

> [!IMPORTANT]
> **Hinweis zur serverseitigen Bildgenerierung** Der WPF-Renderer stellt `RenderCardToImageAsync` eine Methode bereit, die für die serverseitige Bildgenerierung verwendet werden kann. Sie müssen die `ResourcesPath` -Eigenschaft nur verwenden, wenn Sie in dieser Umgebung verwendet wird. Weitere Informationen finden Sie in den [Bild Rendering](../net-image/getting-started.md) -Dokumenten.