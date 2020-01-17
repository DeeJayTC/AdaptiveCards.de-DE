---
title: Vorlagen Sprache für Adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 2c583f774451e60f825cd8fd2c38f2ea34c2f8de
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145400"
---
# <a name="adaptive-cards-template-language"></a><span data-ttu-id="3c7f3-102">Vorlagen Sprache für Adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="3c7f3-102">Adaptive Cards Template Language</span></span>

<span data-ttu-id="3c7f3-103">Durch Vorlagen wird die Trennung von **Daten** vom **Layout** in der adaptiven Karte ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-103">Templating enables the separation of **data** from **layout** in your Adaptive Card.</span></span> <span data-ttu-id="3c7f3-104">Die Vorlagen Sprache ist die Syntax, die zum Erstellen einer Vorlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-104">The template langauge is the syntax used to author a template.</span></span> 

> <span data-ttu-id="3c7f3-105">Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-105">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="3c7f3-106">Diese Features befinden sich **in der Vorschauphase und können geändert werden**.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-106">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="3c7f3-107">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-107">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

<span data-ttu-id="3c7f3-108">Beim Erstellen einer Vorlage können Sie die Daten Inline mit der `AdaptiveCard` Nutzlast oder zur Laufzeit mithilfe der Vorlagen- [sdche](sdk.md)angeben.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-108">When authoring a template you can specify the data inline with the `AdaptiveCard` payload, or at runtime using the [Templating SDKs](sdk.md).</span></span>

## <a name="specify-data-within-the-card"></a><span data-ttu-id="3c7f3-109">Daten innerhalb der Karte angeben</span><span class="sxs-lookup"><span data-stu-id="3c7f3-109">Specify data within the card</span></span>

<span data-ttu-id="3c7f3-110">Um Daten direkt innerhalb der Karten Nutzlast bereitzustellen, fügen Sie Ihrem `AdaptiveCard` einfach ein `$data` Attribut hinzu (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="3c7f3-110">To provide data directly within the card payload, simply add a `$data` attribute to your `AdaptiveCard` (seen below).</span></span>

## <a name="binding-to-the-data"></a><span data-ttu-id="3c7f3-111">Binden an die Daten</span><span class="sxs-lookup"><span data-stu-id="3c7f3-111">Binding to the data</span></span>

<span data-ttu-id="3c7f3-112">Sie können eine Bindung an die Daten innerhalb der `body` oder `actions` der Karte herstellen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-112">You can bind to the data within the `body` or `actions` of the card.</span></span>

* <span data-ttu-id="3c7f3-113">Die Bindungs Syntax beginnt mit `{` und endet mit `}`.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-113">Binding syntax starts with `{` and ends with `}`.</span></span> <span data-ttu-id="3c7f3-114">Beispielsweise `{myProperty}`</span><span class="sxs-lookup"><span data-stu-id="3c7f3-114">E.g., `{myProperty}`</span></span>
* <span data-ttu-id="3c7f3-115">Punkt Schreibweise für den Zugriff auf untergeordnete Objekte</span><span class="sxs-lookup"><span data-stu-id="3c7f3-115">Dot-notation to access sub-objects</span></span>
* <span data-ttu-id="3c7f3-116">Indexer-Syntax zum Abrufen von Eigenschaften nach Schlüsseln oder Elementen in einem Array</span><span class="sxs-lookup"><span data-stu-id="3c7f3-116">Indexer syntax to retrieve properties by key or items in an array</span></span>
* <span data-ttu-id="3c7f3-117">Ordnungsgemäße NULL-Behandlung für Deep-Hierarchien</span><span class="sxs-lookup"><span data-stu-id="3c7f3-117">Graceful null handling for deep hierarchies</span></span>
* <span data-ttu-id="3c7f3-118">*Dokumentation zur Escapesyntax in Kürze verfügbar*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-118">*Escape syntax documentation to come soon*</span></span>

```json
{
    "type": "AdaptiveCard",
    "$data": {
        "employee": {
            "name": "Matt",
            "manager": { "name": "Thomas" },
            "peers": [{
                "name": "Andrew" 
            }, { 
                "name": "Lei"
            }, { 
                "name": "Mary Anne"
            }, { 
                "name": "Adam"
            }]
        }
    },
    "body": [
        {
            "type": "TextBlock",
            "text": "Hi {employee.name}! Here's a bit about your org..."
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: {employee.manager.name}"
        },
        {
            "type": "TextBlock",
            "text": "3 of your peers are: {employee.peers[0].name}, {employee.peers[1].name}, {employee.peers[2].name}"
        }
    ]
}
```

## <a name="separating-the-template-from-the-data"></a><span data-ttu-id="3c7f3-119">Trennen der Vorlage von den Daten</span><span class="sxs-lookup"><span data-stu-id="3c7f3-119">Separating the template from the data</span></span>

<span data-ttu-id="3c7f3-120">Alternativ (und wahrscheinlicher) erstellen Sie eine wiederverwendbare Karte "Template", ohne die Daten einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-120">Alternatively (and more likely), you will create a re-usable card "template" without including the data.</span></span> <span data-ttu-id="3c7f3-121">Diese Vorlage kann als Datei gespeichert und der Quell Code Verwaltung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-121">This template could be stored as a file and added to source control.</span></span>

<span data-ttu-id="3c7f3-122">**EmployeeCardTemplate.json**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-122">**EmployeeCardTemplate.json**</span></span>

```json
{
    "type": "AdaptivCard",
    "body": [
        {
            "type": "TextBlock",
            "text": "Hi {employee.name}! Here's a bit about your org..."
        },
        {
            "type": "TextBlock",
            "text": "Your manager is: {employee.manager.name}"
        },
        {
            "type": "TextBlock",
            "text": "3 of your peers are: {employee.peers[0].name}, {employee.peers[1].name}, {employee.peers[2].name}"
        }
    ]
}
```

<span data-ttu-id="3c7f3-123">Anschließend können Sie die Daten mit den Vorlagen- [sdchen](sdk.md)laden und zur Laufzeit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-123">Then load it up and provide the data at runtime using the [Templating SDKs](sdk.md).</span></span>

<span data-ttu-id="3c7f3-124">**JavaScript-Beispiel**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-124">**JavaScript example**</span></span>

<span data-ttu-id="3c7f3-125">Verwenden des Pakets [adaptivecards-](https://npmjs.com/package/adaptivecards-templating) Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-125">Using the [adaptivecards-templating](https://npmjs.com/package/adaptivecards-templating) package.</span></span>

```js
var template = new ACData.Template({ 
    // EmployeeCardTemplate goes here
});

// Specify data at runtime
var dataContext = new ACData.EvaluationContext();
dataContext.$root = {
    "employee": {
        "name": "Matt",
        "manager": { "name": "Thomas" },
        "peers": [{
            "name": "Andrew" 
        }, { 
            "name": "Lei"
        }, { 
            "name": "Mary Anne"
        }, { 
            "name": "Adam"
        }]
    }
};

var card = template.expand(dataContext);
// Now you have an AdaptiveCard ready to render!
```

## <a name="designer-support"></a><span data-ttu-id="3c7f3-126">Designer Unterstützung</span><span class="sxs-lookup"><span data-stu-id="3c7f3-126">Designer Support</span></span>

<span data-ttu-id="3c7f3-127">Der adaptiver Karten-Designer wurde aktualisiert, um Vorlagen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-127">The Adaptive Card Designer has been updated to support templating.</span></span> 

> <span data-ttu-id="3c7f3-128">Probieren Sie es aus:  **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-128">Try it out at: **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**</span></span>

<span data-ttu-id="3c7f3-129">[Bild ![](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="3c7f3-129">[![image](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)</span></span>

* <span data-ttu-id="3c7f3-130">**Beispiel Daten-Editor** : Geben Sie hier Beispiel Daten an, um die Daten gebundene Karte im Vorschaumodus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-130">**Sample Data Editor** - Specify sample data here to view the data-bound card when in "Preview Mode."</span></span> <span data-ttu-id="3c7f3-131">In diesem Bereich gibt es eine kleine Schaltfläche, um die Datenstruktur aus den vorhandenen Beispiel Daten aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-131">There is a small button in this pane to populate the Data Structure from the existing sample data.</span></span>
* <span data-ttu-id="3c7f3-132">**Datenstruktur** : Dies ist die Struktur der Beispiel Daten.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-132">**Data Structure** - This is the structure of your sample data.</span></span> <span data-ttu-id="3c7f3-133">Felder können auf die Entwurfs Oberfläche gezogen werden, um eine Bindung an Sie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-133">Fields can be dragged onto the design surface to create a binding to them</span></span> 
* <span data-ttu-id="3c7f3-134">**Vorschaumodus** : Klicken Sie auf die Symbolleisten Schaltfläche, um zwischen den Funktionen "Bearbeiten" und "Sample-Data-Preview" zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-134">**Preview Mode** - Press the toolbar button to toggle between the edit-experience and the sample-data-preview experience</span></span>
* <span data-ttu-id="3c7f3-135">**Sample öffnen** : Klicken Sie auf diese Schaltfläche, um verschiedene Beispiel Nutzlasten zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-135">**Open Sample** - click this button to open various sample payloads</span></span>

## <a name="advanced-binding"></a><span data-ttu-id="3c7f3-136">Erweiterte Bindung</span><span class="sxs-lookup"><span data-stu-id="3c7f3-136">Advanced binding</span></span>

### <a name="binding-scopes"></a><span data-ttu-id="3c7f3-137">Bindungs Bereiche</span><span class="sxs-lookup"><span data-stu-id="3c7f3-137">Binding scopes</span></span>

<span data-ttu-id="3c7f3-138">Für den Zugriff auf verschiedene Bindungs Bereiche sind einige reservierte Schlüsselwörter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-138">There are a few reserved keywords to access various binding scopes.</span></span> 

<span data-ttu-id="3c7f3-139">*Hinweis:* nicht alle in der Vorschauversion sind implementiert.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-139">*Note:* not all of these are implemented in the preview.</span></span>

```json
{
    "{<property>}": "Implicitly binds to `$data.<property>`",
    "$data": "The current data object",
    "$root": "The root data object. Useful when iterating to escape to parent object",
    "$index": "The current index when iterating",
    "$host": "Access properties of the host *(not working yet)*"
}
```

### <a name="assigning-a-data-context-to-elements"></a><span data-ttu-id="3c7f3-140">Zuweisen eines Daten Kontexts zu Elementen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-140">Assigning a data context to elements</span></span>

<span data-ttu-id="3c7f3-141">Wenn Sie einem Element einen "Datenkontext" zuweisen möchten, fügen Sie dem-Element ein `$data`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-141">To assign a "data context" to any element add a `$data` attribute to the element.</span></span>

```json
{
    "type": "Container",
    "$data": "{mySubObject}",
    "items": [
        {
            "type": "TextBlock",
            "text": "This TextBlock is now scoped directly to 'mySubObject': {mySubObjectProperty}"
        },
        {
            "type": "TextBlock",
            "text": "To break-out and access the root data, use: {$root}"
        }
    ]
}
```

## <a name="repeating-items-in-an-array"></a><span data-ttu-id="3c7f3-142">Wiederholen von Elementen in einem Array</span><span class="sxs-lookup"><span data-stu-id="3c7f3-142">Repeating items in an array</span></span>

<span data-ttu-id="3c7f3-143">Dieser Teil ist ein wenig "dunkle Magie".</span><span class="sxs-lookup"><span data-stu-id="3c7f3-143">This part is a bit of "dark magic".</span></span> <span data-ttu-id="3c7f3-144">Feedback willkommen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-144">Feedback welcome.</span></span>

* <span data-ttu-id="3c7f3-145">Wenn die `$data`-Eigenschaft eines adaptiven Karten Elements an ein **Array**gebunden ist, **wird das Element selbst für jedes Element im Array wiederholt.**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-145">If an Adaptive Card element's `$data` property is bound to an **array**, then the **element itself will be repeated for each item in the array.**</span></span> 
* <span data-ttu-id="3c7f3-146">Alle Bindungs Ausdrücke (`{myProperty}`), die in Eigenschafts Werten verwendet werden, werden auf das **einzelne Element** innerhalb des Arrays festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-146">Any binding expressions (`{myProperty}`) used in property values will be scoped to the **individual item** within the array.</span></span>
* <span data-ttu-id="3c7f3-147">Wenn Sie an ein Array von Zeichen folgen binden, verwenden Sie `{$data}`, um auf das einzelne Zeichen folgen Element zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-147">If binding to an array of strings, use `{$data}` to access the individual string element.</span></span> <span data-ttu-id="3c7f3-148">Beispielsweise `"text": "{$data}"`</span><span class="sxs-lookup"><span data-stu-id="3c7f3-148">E.g., `"text": "{$data}"`</span></span>

<span data-ttu-id="3c7f3-149">Beispielsweise wird das unten angegebene `TextBlock` dreimal wiederholt, da es `$data` ein Array ist.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-149">For example, the `TextBlock` below will be repeated 3 times since it's `$data` is an array.</span></span> <span data-ttu-id="3c7f3-150">Beachten Sie, dass die `text`-Eigenschaft an die `name`-Eigenschaft eines einzelnen Objekts innerhalb des Arrays gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-150">Notice how the `text` property is bound to the `name` property of an individual object within the array.</span></span> 

```json
{
    "type": "Container",
    "items": [
        {
            "type": "TextBlock",
            "$data": [
                { "name": "Matt" }, 
                { "name": "David" }, 
                { "name": "Thomas" }
            ],
            "text": "{name}"
        }
    ]
}
```

<span data-ttu-id="3c7f3-151">**Ergebnis:**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-151">**Resulting in:**</span></span>

```json
{
    "type": "Container",
    "items": [ 
        {
            "type": "TextBlock",
            "text": "Matt"
        },
        {
            "type": "TextBlock",
            "text": "David"
        }
        {
            "type": "TextBlock",
            "text": "Thomas"
        }
    ]
}
```

## <a name="functions"></a><span data-ttu-id="3c7f3-152">Funktionen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-152">Functions</span></span>

<span data-ttu-id="3c7f3-153">Keine Vorlagen Sprache ist ohne einige Hilfsfunktionen fertiggestellt.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-153">No templating language is complete without some helper functions.</span></span> <span data-ttu-id="3c7f3-154">Wir werden einen Standardsatz von Funktionen bereitstellen, die für jedes SDK funktionieren.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-154">We will provide a standard set of functions that work on every SDK.</span></span> 

<span data-ttu-id="3c7f3-155">Die hier verwendete Syntax ist immer noch in der Luft, also schauen Sie es bald an, aber hier ist ein Einstieg in das, was wir planen:</span><span class="sxs-lookup"><span data-stu-id="3c7f3-155">The syntax here is still up in the air so please check back soon, but here's a start of what we're planning:</span></span>

### <a name="string-functions"></a><span data-ttu-id="3c7f3-156">Zeichenfolgenfunktionen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-156">String functions</span></span>

* <span data-ttu-id="3c7f3-157">substr</span><span class="sxs-lookup"><span data-stu-id="3c7f3-157">substr</span></span>
* <span data-ttu-id="3c7f3-158">IndexOf *(noch nicht funktioniert)*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-158">indexOf *(not working yet)*</span></span>
* <span data-ttu-id="3c7f3-159">*ToUpper(noch nicht funktioniert)*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-159">toUpper *(not working yet)*</span></span>
* <span data-ttu-id="3c7f3-160">ToLower *(noch nicht funktioniert)*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-160">toLower *(not working yet)*</span></span>

### <a name="number-functions"></a><span data-ttu-id="3c7f3-161">Number-Funktionen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-161">Number functions</span></span>

* <span data-ttu-id="3c7f3-162">Formatierung (Currency, Decimal usw.) *(noch nicht funktioniert)*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-162">Formatting (currency, decimal, etc) *(not working yet)*</span></span>

### <a name="date-functions"></a><span data-ttu-id="3c7f3-163">Datumsfunktionen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-163">Date functions</span></span>

* <span data-ttu-id="3c7f3-164">Die Verarbeitung von bekannten Datums Zeichen folgen Formaten *(noch nicht funktioniert)*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-164">Parsing well-known date string formats *(not working yet)*</span></span>
* <span data-ttu-id="3c7f3-165">Formatierung für bekannte Datums-/uhrzeitanstellungen *(noch nicht funktioniert)*</span><span class="sxs-lookup"><span data-stu-id="3c7f3-165">Formatting for well-known date/time representations *(not working yet)*</span></span>

### <a name="conditional-functions"></a><span data-ttu-id="3c7f3-166">Bedingte Funktionen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-166">Conditional functions</span></span>

* <span data-ttu-id="3c7f3-167">if (*Ausdruck*, *TrueValue*, *FalseValue*)</span><span class="sxs-lookup"><span data-stu-id="3c7f3-167">if(*expression*, *trueValue*, *falseValue*)</span></span>

<span data-ttu-id="3c7f3-168">**`if` Beispiel**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-168">**`if` example**</span></span>

```json
{
    "type": "TextBlock",
    "color": "{if(priceChange >= 0, 'good', 'attention')}"
}
```

### <a name="data-manipulation"></a><span data-ttu-id="3c7f3-169">Datenmanipulation</span><span class="sxs-lookup"><span data-stu-id="3c7f3-169">Data manipulation</span></span>

* <span data-ttu-id="3c7f3-170">JSON. Analyse-Möglichkeit zum Analysieren einer JSON-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3c7f3-170">JSON.parse - ability to parse a JSON string</span></span> 

<span data-ttu-id="3c7f3-171">**`JSON.parse` Beispiel**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-171">**`JSON.parse` example**</span></span>

<span data-ttu-id="3c7f3-172">Dies ist eine Azure devops-Antwort, bei der die `message`-Eigenschaft eine JSON-serialisierte Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-172">This is an Azure DevOps response where the `message` property is a JSON-serialized string.</span></span> <span data-ttu-id="3c7f3-173">Um auf Werte innerhalb der Zeichenfolge zuzugreifen, muss die `JSON.parse`-Funktion in der Vorlage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-173">In order to access values within the string, we need to use the `JSON.parse` function in our template.</span></span>

<span data-ttu-id="3c7f3-174">**Daten**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-174">**Data**</span></span> 

```json
{
    "id": "1291525457129548",
    "status": 4,
    "author": "Matt Hidinger",
    "message": "{\"type\":\"Deployment\",\"buildId\":\"9542982\",\"releaseId\":\"129\",\"buildNumber\":\"20180504.3\",\"releaseName\":\"Release-104\",\"repoProvider\":\"GitHub\"}",
    "start_time": "2018-05-04T18:05:33.3087147Z",
    "end_time": "2018-05-04T18:05:33.3087147Z"
}
```

<span data-ttu-id="3c7f3-175">**Nutzung**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-175">**Usage**</span></span>

```json
{
    "type": "TextBlock",
    "text": "{JSON.parse(message).releaseName}"
}
```

<span data-ttu-id="3c7f3-176">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="3c7f3-176">**Resulting In**</span></span>

```json
{
    "type": "TextBlock",
    "text": "Release-104"
}
```

### <a name="custom-functions"></a><span data-ttu-id="3c7f3-177">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-177">Custom functions</span></span>

<span data-ttu-id="3c7f3-178">Wir möchten sicherstellen, dass Hosts benutzerdefinierte Funktionen hinzufügen können. das bedeutet, dass wir eine robuste Unterstützung für die Ausweich Unterstützung benötigen, wenn eine Funktion nicht unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="3c7f3-178">We want to make sure Hosts can add custom functions, which means we need robust support for fallback support if a function isn't supported.</span></span> <span data-ttu-id="3c7f3-179">Wir bewerten dies noch einmal.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-179">We are still evaluating this.</span></span>

## <a name="conditional-layout"></a><span data-ttu-id="3c7f3-180">Bedingtes Layout</span><span class="sxs-lookup"><span data-stu-id="3c7f3-180">Conditional layout</span></span>

<span data-ttu-id="3c7f3-181">Wenn Sie ein gesamtes Element löschen möchten, wenn eine Bedingung erfüllt ist, verwenden Sie die `$when`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-181">To drop an entire element if a condition is met, use the `$when` property.</span></span> <span data-ttu-id="3c7f3-182">Wenn `$when` ausgewertet wird `false` wird das Element dem Benutzer nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-182">If `$when` evaluates to `false` the element will not appear to the user.</span></span>

```json
{
    "type": "AdaptiveCard",
    "$data": {
        "price": "35"
    },
    "body": [
        {
            "type": "TextBlock",
            "$when": "{price > 30}",
            "text": "This thing is pricy!",
            "color": "attention",
        },
         {
            "type": "TextBlock",
            "$when": "{price <= 30}",
            "text": "Dang, this thing is cheap!",
            "color": "good"
        }
    ]
}
```

### <a name="composing-templates"></a><span data-ttu-id="3c7f3-183">Verfassen von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="3c7f3-183">Composing templates</span></span>

<span data-ttu-id="3c7f3-184">Derzeit wird das Zusammenstellen von Vorlagen "Parts" nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-184">Currently there is no support for composing template "parts" together.</span></span> <span data-ttu-id="3c7f3-185">Wir untersuchen jedoch die Optionen und hoffen, dass Sie bald mehr freigeben können.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-185">But we are exploring options and hope to share more soon.</span></span> <span data-ttu-id="3c7f3-186">Hier sind alle Gedanken Willkommen!</span><span class="sxs-lookup"><span data-stu-id="3c7f3-186">Any thoughts here welcome!</span></span>


## <a name="examples"></a><span data-ttu-id="3c7f3-187">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3c7f3-187">Examples</span></span>

<span data-ttu-id="3c7f3-188">Durchsuchen Sie die aktualisierte Beispiel [Seite](https://adaptivecards.io/samples) , um alle möglichen neuen, auf Vorlagen basierenden Karten zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="3c7f3-188">Browse the updated [Samples page](https://adaptivecards.io/samples) to explore all sorts of new templated cards.</span></span>
