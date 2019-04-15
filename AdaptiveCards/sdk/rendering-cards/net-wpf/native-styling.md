---
title: Native Stil - WPF-SDK für .NET
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
# <a name="native-styling---net-wpf"></a>Native formatieren – WPF für .NET

Während der Host-Konfiguration die meisten haben, erhalten Sie die Art und Weise gibt es auf jeder Plattform, ist es wahrscheinlich, dass Sie einige native Formatierungen auf jeder Plattform zu tun hat. 

WPF vereinfacht, sodass Sie einem ResourceDictionary für detaillierte Formatierung, Verhalten, Animationen usw. zu übergeben.

| Element | Namen |
|---|---|
| AdaptiveCard | Adaptive.Card| 
| Action.OpenUrl  | Adaptive.Action.OpenUrl  |
| Action.ShowCard | Adaptive.Action.ShowCard |
| Action.Submit  | Adaptive.Action.Submit  |
| Column | Adaptive.Column, Adaptive.Action.Tap |
| ColumnSet | Adaptive.ColumnSet, Adaptive.VerticalSeparator |
| Container | Adaptive.Container|
| Input.ChoiceSet | Adaptive.Input.ChoiceSet,  Adaptive.Input.ChoiceSet.ComboBox, Adaptive.Input.ChoiceSet.CheckBox,  Adaptive.Input.ChoiceSet.Radio,  Adaptive.Input.ChoiceSet.ComboBoxItem |
| Input.Date | Adaptive.Input.Text.Date
| Input.Number | Adaptive.Input.Text.Number |
| Input.Text | Adaptive.Input.Text |
| Input.Time | Adaptive.Input.Text.Time |
| Input.Toggle| Adaptive.Input.Toggle|
| Bild  | Adaptive.Image |
| ImageSet  | Adaptive.ImageSet |
| FactSet | Adaptive.FactSet, Adaptive.Fact.Title, Adaptive.Fact.Value |
| TextBlock  | Adaptive.TextBlock |

Dieses Beispiel XAML Ressourcenverzeichnis, das den Hintergrund des TextBlocks mit allen auf Hellblau festgelegt. Es ist sinnvoll, dass als dieser fortgeschrittene 😁

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
> **Ein Hinweis zum serverseitigen imagegenerierung** der WPF-Renderer stellt eine `RenderCardToImageAsync` -Methode, die für die Generierung von serverseitigen Images verwendet werden kann. Sie müssen nur verwenden, die `ResourcesPath` Eigenschaft, wenn in dieser Umgebung verwendet. Finden Sie unter den [Image Rendering](../net-image/getting-started.md) Weitere Dokumentation