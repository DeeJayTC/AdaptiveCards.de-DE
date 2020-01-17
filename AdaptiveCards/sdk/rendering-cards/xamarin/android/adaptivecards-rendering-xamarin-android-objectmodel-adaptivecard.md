---
title: Adaptivecard-Klasse-xamarin. Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 12/02/2019
ms.topic: article
ms.openlocfilehash: 0f64bf635023271d8b40bf55fce079300aae7652
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76146084"
---
# <a name="adaptivecard"></a>AdaptiveCard

```csharp
public class AdaptiveCard : Java.Lang.Object 
```

**Namespace**

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a>Zusammenfassung

| Attribute | |
| ---- | --- |
| „Aktionen“ | Die Aktionen, die auf der Aktionsleiste der Karte angezeigt werden sollen. |
| BackgroundImage | Gibt das Hintergrundbild der Karte an. |
| Textkörper | Die Kartenelemente, die im primären Kartenbereich angezeigt werden sollen. |
| ElementType | Muss "adaptivecard" lauten. |
| Fallbacktext | Text, der angezeigt wird, wenn der Client die angegebene Version nicht unterstützt (kann markdown enthalten). |
| Höhe | |
| Inputnecessityindicator | |
| Sprachen | Die in der Karte verwendete ISO-639-1-Sprache mit 2 Buchstaben. Wird zum Lokalisieren von Datums-/Uhrzeitfunktionen verwendet. |
| MinHeight | Gibt die minimale Höhe der Karte an. |
| SelectAction | Eine Aktion, die aufgerufen wird, wenn die Karte angetippt oder ausgewählt wird. Action. showcard wird nicht unterstützt. |
| Speak | Gibt an, was für diese gesamte Karte gesprochen werden soll. Dies ist ein einfacher Text oder ein SSML-Fragment. |
| Format | |
| Version | Schema Version, die für diese Karte erforderlich ist. Wenn ein Client niedriger als diese Version ist, wird der fallbacktext gerendert. Hinweis: für Karten innerhalb einer Action. showcard ist keine Version erforderlich. Dies ist jedoch für die Karte der obersten Ebene erforderlich. |
| VerticalContentAlignment | Definiert, wie der Inhalt vertikal innerhalb des Containers ausgerichtet werden soll. Nur relevant für Karten mit fester Höhe oder Karten mit einer angegebenen MinHeight-Angabe. |

&nbsp;

**Öffentliche Konstruktoren**

---

<a href="#ctor0"><div>
```csharp
AdaptiveCard(string version, string fallbackText, BackgroundImage backgroundImage, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight)
```
</div></a>

<a href="#ctor1"><div>
```csharp
AdaptiveCard(string version, string fallbackText, BackgroundImage backgroundImage, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight, BaseCardElementVector body, BaseActionElementVector actions)
```
</div></a>

<a href="#ctor2"><div>
```csharp
AdaptiveCard(string version, string fallbackText, string backgroundImageUrl, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight)
```
</div></a>

<a href="#ctor3"><div>
```csharp
AdaptiveCard(string version, string fallbackText, string backgroundImageUrl, ContainerStyle style, string speak, string language, VerticalContentAlignment verticalContentAlignment, HeightType height, long minHeight, BaseCardElementVector body, BaseActionElementVector actions)
```
</div></a>

&nbsp;
| Öffentliche Methoden | |
| --- | ---- |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion)```](#deserializefromstring0) |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)```](#deserializefromstring1) |
| ```static AdaptiveCard``` | [```MakeFallbackTextCard(string fallbackText, string language, string speak)```](#makefallbacktextcard) |
| ```string``` | [```Serialize()```](#serialize) |
| ```JsonValue``` | [```SerializeToJsonValue()```](#serializetojsonvalue) |

&nbsp;
## <a name="public-constructors"></a>Öffentliche Konstruktoren
---

### <a id="ctor0"></a>Adaptivecard
<p style='text-align:right'>In Version 0,1 hinzugefügt</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    BackgroundImage backgroundImage, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment, 
                    HeightType height, 
                    long minHeight) 
```

| Parameter | |
| --- | --- |
| -Version | ```string``` |
| fallbacktext | ```string``` |
| backgroundImage | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| Format | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| verticalContentAlignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |

&nbsp;&nbsp;

### <a id="ctor1"></a>Adaptivecard
<p style='text-align:right'>In Version 0,1 hinzugefügt</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    BackgroundImage backgroundImage, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment, 
                    HeightType height, 
                    long minHeight, 
                    BaseCardElementVector body, 
                    BaseActionElementVector actions)
```

| Parameter | |
| --- | --- |
| -Version | ```string``` |
| fallbacktext | ```string``` |
| backgroundImage | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| Format | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| verticalContentAlignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |
| body | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| Aktionen | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;&nbsp;

### <a id="ctor2"></a>Adaptivecard
<p style='text-align:right'>In Version 0,1 hinzugefügt</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    string backgroundImageUrl, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment,
                    HeightType height, 
                    long minHeight) 
```

| Parameter | |
| --- | --- |
| -Version | ```string``` |
| fallbacktext | ```string``` |
| backgroundImage | ```string``` |
| Format | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| verticalContentAlignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |

&nbsp;&nbsp;

### <a id="ctor3"></a>Adaptivecard
<p style='text-align:right'>In Version 0,1 hinzugefügt</p>

```csharp
public AdaptiveCard (string version, 
                    string fallbackText, 
                    string backgroundImageUrl, 
                    ContainerStyle style, 
                    string speak, 
                    string language, 
                    VerticalContentAlignment verticalContentAlignment,
                    HeightType height, 
                    long minHeight, 
                    BaseCardElementVector body,
                    BaseActionElementVector actions)

```

| Parameter | |
| --- | --- |
| -Version | ```string``` |
| fallbacktext | ```string``` |
| backgroundImage | ```string``` |
| Format | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| speak | ```string``` |
| language | ```string``` |
| verticalContentAlignment | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| height | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| minHeight | ```long``` |
| body | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| Aktionen | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;

## <a name="public-methods"></a>Öffentliche Methoden
---
### <a id="deserializefromstring0"></a>Deserializefromstring
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public static ParseResult DeserializeFromString (string jsonString, string rendererVersion)
```

Deserialisiert die angegebene Adaptive Karte als JSON-Zeichenfolge für die angegebene rendererversion.

| Parameter | |
| --- | --- |
| jsonString | ```string``` |
| rendererversion | ```string``` |

| Rückgabe | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a>Beispiel

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
```

--- 
### <a id="deserializefromstring1"></a>Deserializefromstring
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public static ParseResult DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)
```

Deserialisiert die angegebene Adaptive Karte als JSON-Zeichenfolge für die angegebene rendererversion unter Verwendung eines [Objekttext]() -Objekts, um die benutzerdefinierte Element Verarbeitung zu verarbeiten.

| Parameter | |
| --- | --- |
| jsonString | ```string``` |
| rendererversion | ```string``` |
| context | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseContext``` |

| Rückgabe | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a>Beispiel

```csharp
ParseContext parseContext = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, parseContext);
```

---

### <a id="makefallbacktextcard"></a>Makefallbacktextcard
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public static AdaptiveCard MakeFallbackTextCard (string fallbackText, string language, string speak)
```

Deserialisiert die angegebene Adaptive Karte als JSON-Zeichenfolge für die angegebene rendererversion.

| Parameter | |
| --- | --- |
| fallbacktext | ```string``` |
| language | ```string``` |
| speak | ```string``` |

| Rückgabe | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard``` | Adaptive Karte, die den Fall Back Text für eine nicht renderbare Karte enthält |

#### <a name="sample"></a>Beispiel

```csharp
AdaptiveCard adaptiveCard = AdaptiveCard.MakeFallbackTextCard("This card failed to render", "es", "Unrendereable card");
```

---

### <a id="serialize"></a>Serialisieren
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public string Serialize ()
```

Serialisiert die Adaptive Karte in Ihre JSON-Zeichen folgen Form.

| Rückgabe | |
| --- | --- |
| ```string``` | Adaptive Karte als JSON-Zeichenfolge |

#### <a name="sample"></a>Beispiel

```csharp
string jsonString = parseResult.AdaptiveCard.Serialize();
```

---

### <a id="serializetojsonvalue"></a>Serializetojsonvalue
<p style='text-align:right'>In Version 0.1.0 hinzugefügt</p>

```csharp
public JsonValue SerializeToJsonValue ()
```

Serialisiert die Adaptive Karte in ein JSON-Wertobjekt.

| Rückgabe | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.JsonValue``` | |

#### <a name="sample"></a>Beispiel

```csharp
JsonValue value = parseResult.AdaptiveCard.SerializeToJsonValue();
```