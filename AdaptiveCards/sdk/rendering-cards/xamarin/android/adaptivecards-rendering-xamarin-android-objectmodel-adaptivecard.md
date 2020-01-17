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
# <a name="adaptivecard"></a><span data-ttu-id="10786-102">AdaptiveCard</span><span class="sxs-lookup"><span data-stu-id="10786-102">AdaptiveCard</span></span>

```csharp
public class AdaptiveCard : Java.Lang.Object 
```

<span data-ttu-id="10786-103">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="10786-103">**Namespace**</span></span>

```csharp
namespace AdaptiveCards.Rendering.Xamarin.Android.ObjectModel
```

## <a name="summary"></a><span data-ttu-id="10786-104">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="10786-104">Summary</span></span>

| <span data-ttu-id="10786-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="10786-105">Attributes</span></span> | |
| ---- | --- |
| <span data-ttu-id="10786-106">„Aktionen“</span><span class="sxs-lookup"><span data-stu-id="10786-106">Actions</span></span> | <span data-ttu-id="10786-107">Die Aktionen, die auf der Aktionsleiste der Karte angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="10786-107">The Actions to show in the card’s action bar.</span></span> |
| <span data-ttu-id="10786-108">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="10786-108">BackgroundImage</span></span> | <span data-ttu-id="10786-109">Gibt das Hintergrundbild der Karte an.</span><span class="sxs-lookup"><span data-stu-id="10786-109">Specifies the background image of the card.</span></span> |
| <span data-ttu-id="10786-110">Textkörper</span><span class="sxs-lookup"><span data-stu-id="10786-110">Body</span></span> | <span data-ttu-id="10786-111">Die Kartenelemente, die im primären Kartenbereich angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="10786-111">The card elements to show in the primary card region.</span></span> |
| <span data-ttu-id="10786-112">ElementType</span><span class="sxs-lookup"><span data-stu-id="10786-112">ElementType</span></span> | <span data-ttu-id="10786-113">Muss "adaptivecard" lauten.</span><span class="sxs-lookup"><span data-stu-id="10786-113">Must be "AdaptiveCard".</span></span> |
| <span data-ttu-id="10786-114">Fallbacktext</span><span class="sxs-lookup"><span data-stu-id="10786-114">FallbackText</span></span> | <span data-ttu-id="10786-115">Text, der angezeigt wird, wenn der Client die angegebene Version nicht unterstützt (kann markdown enthalten).</span><span class="sxs-lookup"><span data-stu-id="10786-115">Text shown when the client doesn’t support the version specified (may contain markdown).</span></span> |
| <span data-ttu-id="10786-116">Höhe</span><span class="sxs-lookup"><span data-stu-id="10786-116">Height</span></span> | |
| <span data-ttu-id="10786-117">Inputnecessityindicator</span><span class="sxs-lookup"><span data-stu-id="10786-117">InputNecessityIndicators</span></span> | |
| <span data-ttu-id="10786-118">Sprachen</span><span class="sxs-lookup"><span data-stu-id="10786-118">Language</span></span> | <span data-ttu-id="10786-119">Die in der Karte verwendete ISO-639-1-Sprache mit 2 Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="10786-119">The 2-letter ISO-639-1 language used in the card.</span></span> <span data-ttu-id="10786-120">Wird zum Lokalisieren von Datums-/Uhrzeitfunktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="10786-120">Used to localize any date/time functions.</span></span> |
| <span data-ttu-id="10786-121">MinHeight</span><span class="sxs-lookup"><span data-stu-id="10786-121">MinHeight</span></span> | <span data-ttu-id="10786-122">Gibt die minimale Höhe der Karte an.</span><span class="sxs-lookup"><span data-stu-id="10786-122">Specifies the minimum height of the card.</span></span> |
| <span data-ttu-id="10786-123">SelectAction</span><span class="sxs-lookup"><span data-stu-id="10786-123">SelectAction</span></span> | <span data-ttu-id="10786-124">Eine Aktion, die aufgerufen wird, wenn die Karte angetippt oder ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="10786-124">An Action that will be invoked when the card is tapped or selected.</span></span> <span data-ttu-id="10786-125">Action. showcard wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10786-125">Action.ShowCard is not supported.</span></span> |
| <span data-ttu-id="10786-126">Speak</span><span class="sxs-lookup"><span data-stu-id="10786-126">Speak</span></span> | <span data-ttu-id="10786-127">Gibt an, was für diese gesamte Karte gesprochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="10786-127">Specifies what should be spoken for this entire card.</span></span> <span data-ttu-id="10786-128">Dies ist ein einfacher Text oder ein SSML-Fragment.</span><span class="sxs-lookup"><span data-stu-id="10786-128">This is simple text or SSML fragment.</span></span> |
| <span data-ttu-id="10786-129">Format</span><span class="sxs-lookup"><span data-stu-id="10786-129">Style</span></span> | |
| <span data-ttu-id="10786-130">Version</span><span class="sxs-lookup"><span data-stu-id="10786-130">Version</span></span> | <span data-ttu-id="10786-131">Schema Version, die für diese Karte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="10786-131">Schema version that this card requires.</span></span> <span data-ttu-id="10786-132">Wenn ein Client niedriger als diese Version ist, wird der fallbacktext gerendert.</span><span class="sxs-lookup"><span data-stu-id="10786-132">If a client is lower than this version, the fallbackText will be rendered.</span></span> <span data-ttu-id="10786-133">Hinweis: für Karten innerhalb einer Action. showcard ist keine Version erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10786-133">NOTE: Version is not required for cards within an Action.ShowCard.</span></span> <span data-ttu-id="10786-134">Dies ist jedoch für die Karte der obersten Ebene erforderlich.</span><span class="sxs-lookup"><span data-stu-id="10786-134">However, it is required for the top-level card.</span></span> |
| <span data-ttu-id="10786-135">VerticalContentAlignment</span><span class="sxs-lookup"><span data-stu-id="10786-135">VerticalContentAlignment</span></span> | <span data-ttu-id="10786-136">Definiert, wie der Inhalt vertikal innerhalb des Containers ausgerichtet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10786-136">Defines how the content should be aligned vertically within the container.</span></span> <span data-ttu-id="10786-137">Nur relevant für Karten mit fester Höhe oder Karten mit einer angegebenen MinHeight-Angabe.</span><span class="sxs-lookup"><span data-stu-id="10786-137">Only relevant for fixed-height cards, or cards with a minHeight specified.</span></span> |

&nbsp;

<span data-ttu-id="10786-138">**Öffentliche Konstruktoren**</span><span class="sxs-lookup"><span data-stu-id="10786-138">**Public Constructors**</span></span>

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
| <span data-ttu-id="10786-139">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="10786-139">Public methods</span></span> | |
| --- | ---- |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion)```](#deserializefromstring0) |
| ```static ParseResult``` | [```DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)```](#deserializefromstring1) |
| ```static AdaptiveCard``` | [```MakeFallbackTextCard(string fallbackText, string language, string speak)```](#makefallbacktextcard) |
| ```string``` | [```Serialize()```](#serialize) |
| ```JsonValue``` | [```SerializeToJsonValue()```](#serializetojsonvalue) |

&nbsp;
## <a name="public-constructors"></a><span data-ttu-id="10786-140">Öffentliche Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="10786-140">Public Constructors</span></span>
---

### <a id="ctor0"></a><span data-ttu-id="10786-141">Adaptivecard</span><span class="sxs-lookup"><span data-stu-id="10786-141">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="10786-142">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-142">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="10786-143">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-143">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-144">-Version</span><span class="sxs-lookup"><span data-stu-id="10786-144">version</span></span> | ```string``` |
| <span data-ttu-id="10786-145">fallbacktext</span><span class="sxs-lookup"><span data-stu-id="10786-145">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="10786-146">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="10786-146">backgroundImage</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| <span data-ttu-id="10786-147">Format</span><span class="sxs-lookup"><span data-stu-id="10786-147">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="10786-148">speak</span><span class="sxs-lookup"><span data-stu-id="10786-148">speak</span></span> | ```string``` |
| <span data-ttu-id="10786-149">language</span><span class="sxs-lookup"><span data-stu-id="10786-149">language</span></span> | ```string``` |
| <span data-ttu-id="10786-150">verticalContentAlignment</span><span class="sxs-lookup"><span data-stu-id="10786-150">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="10786-151">height</span><span class="sxs-lookup"><span data-stu-id="10786-151">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="10786-152">minHeight</span><span class="sxs-lookup"><span data-stu-id="10786-152">minHeight</span></span> | ```long``` |

&nbsp;&nbsp;

### <a id="ctor1"></a><span data-ttu-id="10786-153">Adaptivecard</span><span class="sxs-lookup"><span data-stu-id="10786-153">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="10786-154">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-154">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="10786-155">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-155">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-156">-Version</span><span class="sxs-lookup"><span data-stu-id="10786-156">version</span></span> | ```string``` |
| <span data-ttu-id="10786-157">fallbacktext</span><span class="sxs-lookup"><span data-stu-id="10786-157">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="10786-158">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="10786-158">backgroundImage</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BackgroundImage``` |
| <span data-ttu-id="10786-159">Format</span><span class="sxs-lookup"><span data-stu-id="10786-159">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="10786-160">speak</span><span class="sxs-lookup"><span data-stu-id="10786-160">speak</span></span> | ```string``` |
| <span data-ttu-id="10786-161">language</span><span class="sxs-lookup"><span data-stu-id="10786-161">language</span></span> | ```string``` |
| <span data-ttu-id="10786-162">verticalContentAlignment</span><span class="sxs-lookup"><span data-stu-id="10786-162">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="10786-163">height</span><span class="sxs-lookup"><span data-stu-id="10786-163">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="10786-164">minHeight</span><span class="sxs-lookup"><span data-stu-id="10786-164">minHeight</span></span> | ```long``` |
| <span data-ttu-id="10786-165">body</span><span class="sxs-lookup"><span data-stu-id="10786-165">body</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| <span data-ttu-id="10786-166">Aktionen</span><span class="sxs-lookup"><span data-stu-id="10786-166">actions</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;&nbsp;

### <a id="ctor2"></a><span data-ttu-id="10786-167">Adaptivecard</span><span class="sxs-lookup"><span data-stu-id="10786-167">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="10786-168">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-168">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="10786-169">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-169">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-170">-Version</span><span class="sxs-lookup"><span data-stu-id="10786-170">version</span></span> | ```string``` |
| <span data-ttu-id="10786-171">fallbacktext</span><span class="sxs-lookup"><span data-stu-id="10786-171">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="10786-172">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="10786-172">backgroundImage</span></span> | ```string``` |
| <span data-ttu-id="10786-173">Format</span><span class="sxs-lookup"><span data-stu-id="10786-173">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="10786-174">speak</span><span class="sxs-lookup"><span data-stu-id="10786-174">speak</span></span> | ```string``` |
| <span data-ttu-id="10786-175">language</span><span class="sxs-lookup"><span data-stu-id="10786-175">language</span></span> | ```string``` |
| <span data-ttu-id="10786-176">verticalContentAlignment</span><span class="sxs-lookup"><span data-stu-id="10786-176">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="10786-177">height</span><span class="sxs-lookup"><span data-stu-id="10786-177">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="10786-178">minHeight</span><span class="sxs-lookup"><span data-stu-id="10786-178">minHeight</span></span> | ```long``` |

&nbsp;&nbsp;

### <a id="ctor3"></a><span data-ttu-id="10786-179">Adaptivecard</span><span class="sxs-lookup"><span data-stu-id="10786-179">AdaptiveCard</span></span>
<p style='text-align:right'><span data-ttu-id="10786-180">In Version 0,1 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-180">Added in version 0.1</span></span></p>

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

| <span data-ttu-id="10786-181">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-181">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-182">-Version</span><span class="sxs-lookup"><span data-stu-id="10786-182">version</span></span> | ```string``` |
| <span data-ttu-id="10786-183">fallbacktext</span><span class="sxs-lookup"><span data-stu-id="10786-183">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="10786-184">backgroundImage</span><span class="sxs-lookup"><span data-stu-id="10786-184">backgroundImage</span></span> | ```string``` |
| <span data-ttu-id="10786-185">Format</span><span class="sxs-lookup"><span data-stu-id="10786-185">style</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ContainerStyle``` |
| <span data-ttu-id="10786-186">speak</span><span class="sxs-lookup"><span data-stu-id="10786-186">speak</span></span> | ```string``` |
| <span data-ttu-id="10786-187">language</span><span class="sxs-lookup"><span data-stu-id="10786-187">language</span></span> | ```string``` |
| <span data-ttu-id="10786-188">verticalContentAlignment</span><span class="sxs-lookup"><span data-stu-id="10786-188">verticalContentAlignment</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.VerticalContentAlignment``` |
| <span data-ttu-id="10786-189">height</span><span class="sxs-lookup"><span data-stu-id="10786-189">height</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.HeightType``` |
| <span data-ttu-id="10786-190">minHeight</span><span class="sxs-lookup"><span data-stu-id="10786-190">minHeight</span></span> | ```long``` |
| <span data-ttu-id="10786-191">body</span><span class="sxs-lookup"><span data-stu-id="10786-191">body</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseCardElementVector``` |
| <span data-ttu-id="10786-192">Aktionen</span><span class="sxs-lookup"><span data-stu-id="10786-192">actions</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.BaseActionElementVector``` |

&nbsp;

## <a name="public-methods"></a><span data-ttu-id="10786-193">Öffentliche Methoden</span><span class="sxs-lookup"><span data-stu-id="10786-193">Public Methods</span></span>
---
### <a id="deserializefromstring0"></a><span data-ttu-id="10786-194">Deserializefromstring</span><span class="sxs-lookup"><span data-stu-id="10786-194">DeserializeFromString</span></span>
<p style='text-align:right'><span data-ttu-id="10786-195">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-195">Added in version 0.1.0</span></span></p>

```csharp
public static ParseResult DeserializeFromString (string jsonString, string rendererVersion)
```

<span data-ttu-id="10786-196">Deserialisiert die angegebene Adaptive Karte als JSON-Zeichenfolge für die angegebene rendererversion.</span><span class="sxs-lookup"><span data-stu-id="10786-196">Deserializes the given adaptive card as a json string for the specified renderer version.</span></span>

| <span data-ttu-id="10786-197">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-197">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-198">jsonString</span><span class="sxs-lookup"><span data-stu-id="10786-198">jsonString</span></span> | ```string``` |
| <span data-ttu-id="10786-199">rendererversion</span><span class="sxs-lookup"><span data-stu-id="10786-199">rendererVersion</span></span> | ```string``` |

| <span data-ttu-id="10786-200">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="10786-200">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a><span data-ttu-id="10786-201">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10786-201">Sample</span></span>

```csharp
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version);
```

--- 
### <a id="deserializefromstring1"></a><span data-ttu-id="10786-202">Deserializefromstring</span><span class="sxs-lookup"><span data-stu-id="10786-202">DeserializeFromString</span></span>
<p style='text-align:right'><span data-ttu-id="10786-203">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-203">Added in version 0.1.0</span></span></p>

```csharp
public static ParseResult DeserializeFromString(string jsonString, string rendererVersion, ParseContext context)
```

<span data-ttu-id="10786-204">Deserialisiert die angegebene Adaptive Karte als JSON-Zeichenfolge für die angegebene rendererversion unter Verwendung eines [Objekttext]() -Objekts, um die benutzerdefinierte Element Verarbeitung zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="10786-204">Deserializes the given adaptive card as a json string for the specified renderer version using a [ParseContext]() object to handle custom element parsing.</span></span>

| <span data-ttu-id="10786-205">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-205">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-206">jsonString</span><span class="sxs-lookup"><span data-stu-id="10786-206">jsonString</span></span> | ```string``` |
| <span data-ttu-id="10786-207">rendererversion</span><span class="sxs-lookup"><span data-stu-id="10786-207">rendererVersion</span></span> | ```string``` |
| <span data-ttu-id="10786-208">context</span><span class="sxs-lookup"><span data-stu-id="10786-208">context</span></span> | ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseContext``` |

| <span data-ttu-id="10786-209">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="10786-209">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.ParseResult``` | |

#### <a name="sample"></a><span data-ttu-id="10786-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10786-210">Sample</span></span>

```csharp
ParseContext parseContext = new ParseContext(elementParserRegistration, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.Version, parseContext);
```

---

### <a id="makefallbacktextcard"></a><span data-ttu-id="10786-211">Makefallbacktextcard</span><span class="sxs-lookup"><span data-stu-id="10786-211">MakeFallbackTextCard</span></span>
<p style='text-align:right'><span data-ttu-id="10786-212">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-212">Added in version 0.1.0</span></span></p>

```csharp
public static AdaptiveCard MakeFallbackTextCard (string fallbackText, string language, string speak)
```

<span data-ttu-id="10786-213">Deserialisiert die angegebene Adaptive Karte als JSON-Zeichenfolge für die angegebene rendererversion.</span><span class="sxs-lookup"><span data-stu-id="10786-213">Deserializes the given adaptive card as a json string for the specified renderer version.</span></span>

| <span data-ttu-id="10786-214">Parameter</span><span class="sxs-lookup"><span data-stu-id="10786-214">Parameters</span></span> | |
| --- | --- |
| <span data-ttu-id="10786-215">fallbacktext</span><span class="sxs-lookup"><span data-stu-id="10786-215">fallbackText</span></span> | ```string``` |
| <span data-ttu-id="10786-216">language</span><span class="sxs-lookup"><span data-stu-id="10786-216">language</span></span> | ```string``` |
| <span data-ttu-id="10786-217">speak</span><span class="sxs-lookup"><span data-stu-id="10786-217">speak</span></span> | ```string``` |

| <span data-ttu-id="10786-218">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="10786-218">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.AdaptiveCard``` | <span data-ttu-id="10786-219">Adaptive Karte, die den Fall Back Text für eine nicht renderbare Karte enthält</span><span class="sxs-lookup"><span data-stu-id="10786-219">Adaptive card that contains the fallback text for an unrendereable card</span></span> |

#### <a name="sample"></a><span data-ttu-id="10786-220">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10786-220">Sample</span></span>

```csharp
AdaptiveCard adaptiveCard = AdaptiveCard.MakeFallbackTextCard("This card failed to render", "es", "Unrendereable card");
```

---

### <a id="serialize"></a><span data-ttu-id="10786-221">Serialisieren</span><span class="sxs-lookup"><span data-stu-id="10786-221">Serialize</span></span>
<p style='text-align:right'><span data-ttu-id="10786-222">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-222">Added in version 0.1.0</span></span></p>

```csharp
public string Serialize ()
```

<span data-ttu-id="10786-223">Serialisiert die Adaptive Karte in Ihre JSON-Zeichen folgen Form.</span><span class="sxs-lookup"><span data-stu-id="10786-223">Serializes the adaptive card into it's json string form.</span></span>

| <span data-ttu-id="10786-224">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="10786-224">Returns</span></span> | |
| --- | --- |
| ```string``` | <span data-ttu-id="10786-225">Adaptive Karte als JSON-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="10786-225">Adaptive card as a json string</span></span> |

#### <a name="sample"></a><span data-ttu-id="10786-226">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10786-226">Sample</span></span>

```csharp
string jsonString = parseResult.AdaptiveCard.Serialize();
```

---

### <a id="serializetojsonvalue"></a><span data-ttu-id="10786-227">Serializetojsonvalue</span><span class="sxs-lookup"><span data-stu-id="10786-227">SerializeToJsonValue</span></span>
<p style='text-align:right'><span data-ttu-id="10786-228">In Version 0.1.0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="10786-228">Added in version 0.1.0</span></span></p>

```csharp
public JsonValue SerializeToJsonValue ()
```

<span data-ttu-id="10786-229">Serialisiert die Adaptive Karte in ein JSON-Wertobjekt.</span><span class="sxs-lookup"><span data-stu-id="10786-229">Serializes the adaptive card into a json value object.</span></span>

| <span data-ttu-id="10786-230">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="10786-230">Returns</span></span> | |
| --- | --- |
| ```AdaptiveCards.Rendering.Xamarin.Android.ObjectModel.JsonValue``` | |

#### <a name="sample"></a><span data-ttu-id="10786-231">Beispiel</span><span class="sxs-lookup"><span data-stu-id="10786-231">Sample</span></span>

```csharp
JsonValue value = parseResult.AdaptiveCard.SerializeToJsonValue();
```