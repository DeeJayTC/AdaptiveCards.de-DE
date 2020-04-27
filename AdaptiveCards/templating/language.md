---
title: Vorlagensprache für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: ffd2ec065550f483bf602483eebf622565f7f47a
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82136176"
---
# <a name="adaptive-cards-template-language"></a><span data-ttu-id="8feed-102">Vorlagensprache für adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="8feed-102">Adaptive Cards Template Language</span></span>

<span data-ttu-id="8feed-103">Durch Vorlagen wird die Trennung von **Daten** und **Layout** auf Ihrer adaptiven Karte ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="8feed-103">Templating enables the separation of **data** from **layout** in your Adaptive Card.</span></span> <span data-ttu-id="8feed-104">Die Vorlagensprache ist die Syntax, die zum Erstellen einer Vorlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8feed-104">The template langauge is the syntax used to author a template.</span></span> 

> <span data-ttu-id="8feed-105">Hier finden Sie einen [Überblick über Vorlagen für adaptive Karten](index.md).</span><span class="sxs-lookup"><span data-stu-id="8feed-105">Please read this for an [overview of Adaptive Card Templating](index.md)</span></span>

> [!IMPORTANT] 
> 
> <span data-ttu-id="8feed-106">Diese Features befinden sich **in der Vorschauphase und können geändert werden**.</span><span class="sxs-lookup"><span data-stu-id="8feed-106">These features are **in preview and subject to change**.</span></span> <span data-ttu-id="8feed-107">Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.</span><span class="sxs-lookup"><span data-stu-id="8feed-107">Your feedback is not only welcome, but  critical to ensure we deliver the features **you** need.</span></span>

<span data-ttu-id="8feed-108">Wenn Sie eine Vorlage erstellen, können Sie die Daten inline mit der `AdaptiveCard`-Nutzlast oder zur Laufzeit mithilfe der [Vorlagen-SDKs](sdk.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="8feed-108">When authoring a template you can specify the data inline with the `AdaptiveCard` payload, or at runtime using the [Templating SDKs](sdk.md).</span></span>

## <a name="specify-data-within-the-card"></a><span data-ttu-id="8feed-109">Daten innerhalb der Karte angeben</span><span class="sxs-lookup"><span data-stu-id="8feed-109">Specify data within the card</span></span>

<span data-ttu-id="8feed-110">Um Daten direkt innerhalb der Kartennutzlast bereitzustellen, fügen Sie Ihrer `$data` einfach ein `AdaptiveCard`-Attribut hinzu (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="8feed-110">To provide data directly within the card payload, simply add a `$data` attribute to your `AdaptiveCard` (seen below).</span></span>

## <a name="binding-to-the-data"></a><span data-ttu-id="8feed-111">Bindung an Daten</span><span class="sxs-lookup"><span data-stu-id="8feed-111">Binding to the data</span></span>

<span data-ttu-id="8feed-112">Sie können eine Bindung an Daten innerhalb von `body` oder `actions` der Karte herstellen.</span><span class="sxs-lookup"><span data-stu-id="8feed-112">You can bind to the data within the `body` or `actions` of the card.</span></span>

* <span data-ttu-id="8feed-113">Die Bindungssyntax beginnt mit `{` und endet mit `}`.</span><span class="sxs-lookup"><span data-stu-id="8feed-113">Binding syntax starts with `{` and ends with `}`.</span></span> <span data-ttu-id="8feed-114">Beispiel: `{myProperty}`</span><span class="sxs-lookup"><span data-stu-id="8feed-114">E.g., `{myProperty}`</span></span>
* <span data-ttu-id="8feed-115">Punkt-Notation für den Zugriff auf untergeordnete Objekte</span><span class="sxs-lookup"><span data-stu-id="8feed-115">Dot-notation to access sub-objects</span></span>
* <span data-ttu-id="8feed-116">Indexersyntax zum Abrufen von Eigenschaften nach Schlüsseln oder Elementen in einem Array</span><span class="sxs-lookup"><span data-stu-id="8feed-116">Indexer syntax to retrieve properties by key or items in an array</span></span>
* <span data-ttu-id="8feed-117">Ordnungsgemäße NULL-Behandlung für tiefen Hierarchien</span><span class="sxs-lookup"><span data-stu-id="8feed-117">Graceful null handling for deep hierarchies</span></span>
* <span data-ttu-id="8feed-118">*Dokumentation zur Escapesyntax in Kürze verfügbar*</span><span class="sxs-lookup"><span data-stu-id="8feed-118">*Escape syntax documentation to come soon*</span></span>

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

## <a name="separating-the-template-from-the-data"></a><span data-ttu-id="8feed-119">Trennen von Vorlage und Daten</span><span class="sxs-lookup"><span data-stu-id="8feed-119">Separating the template from the data</span></span>

<span data-ttu-id="8feed-120">Alternativ (und wahrscheinlicher) erstellen Sie eine wiederverwendbare Karte „Vorlage“ ohne Daten.</span><span class="sxs-lookup"><span data-stu-id="8feed-120">Alternatively (and more likely), you will create a re-usable card "template" without including the data.</span></span> <span data-ttu-id="8feed-121">Diese Vorlage kann als Datei gespeichert und dem Quellsteuerelement hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8feed-121">This template could be stored as a file and added to source control.</span></span>

<span data-ttu-id="8feed-122">**EmployeeCardTemplate.json**</span><span class="sxs-lookup"><span data-stu-id="8feed-122">**EmployeeCardTemplate.json**</span></span>

```json
{
    "type": "AdaptiveCard",
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

<span data-ttu-id="8feed-123">Laden Sie die Daten dann zur Laufzeit, und stellen Sie sie mithilfe des [Vorlagen-SDKs](sdk.md) bereit.</span><span class="sxs-lookup"><span data-stu-id="8feed-123">Then load it up and provide the data at runtime using the [Templating SDKs](sdk.md).</span></span>

<span data-ttu-id="8feed-124">**JavaScript-Beispiel**</span><span class="sxs-lookup"><span data-stu-id="8feed-124">**JavaScript example**</span></span>

<span data-ttu-id="8feed-125">Verwenden des Pakets [adaptivecards-templating](https://npmjs.com/package/adaptivecards-templating).</span><span class="sxs-lookup"><span data-stu-id="8feed-125">Using the [adaptivecards-templating](https://npmjs.com/package/adaptivecards-templating) package.</span></span>

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

## <a name="designer-support"></a><span data-ttu-id="8feed-126">Designerunterstützung</span><span class="sxs-lookup"><span data-stu-id="8feed-126">Designer Support</span></span>

<span data-ttu-id="8feed-127">Der Designer für adaptive Karten wurde aktualisiert, um Vorlagen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8feed-127">The Adaptive Card Designer has been updated to support templating.</span></span> 

> <span data-ttu-id="8feed-128">Jetzt testen unter: **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**</span><span class="sxs-lookup"><span data-stu-id="8feed-128">Try it out at: **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**</span></span>

<span data-ttu-id="8feed-129">[![Abbildung](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="8feed-129">[![image](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)</span></span>

* <span data-ttu-id="8feed-130">**Beispieldaten-Editor** – Geben Sie hier Beispieldaten an, um die datengebundene Karte im Vorschaumodus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8feed-130">**Sample Data Editor** - Specify sample data here to view the data-bound card when in "Preview Mode."</span></span> <span data-ttu-id="8feed-131">In diesem Bereich gibt es eine kleine Schaltfläche, zum Auffüllen der Datenstruktur mit den vorhandenen Beispieldaten.</span><span class="sxs-lookup"><span data-stu-id="8feed-131">There is a small button in this pane to populate the Data Structure from the existing sample data.</span></span>
* <span data-ttu-id="8feed-132">**Datenstruktur** – Dies ist die Struktur der Beispieldaten.</span><span class="sxs-lookup"><span data-stu-id="8feed-132">**Data Structure** - This is the structure of your sample data.</span></span> <span data-ttu-id="8feed-133">Felder können auf die Entwurfsoberfläche gezogen werden, um eine Bindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8feed-133">Fields can be dragged onto the design surface to create a binding to them</span></span> 
* <span data-ttu-id="8feed-134">**Vorschaumodus** – Klicken Sie auf die Symbolleistenschaltfläche, um zwischen der „edit-experience“ und der „sample-data-preview“ zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8feed-134">**Preview Mode** - Press the toolbar button to toggle between the edit-experience and the sample-data-preview experience</span></span>
* <span data-ttu-id="8feed-135">**Beispiel öffnen** – Klicken Sie auf diese Schaltfläche, um verschiedene Beispielnutzlasten zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8feed-135">**Open Sample** - click this button to open various sample payloads</span></span>

## <a name="advanced-binding"></a><span data-ttu-id="8feed-136">Erweiterte Bindung</span><span class="sxs-lookup"><span data-stu-id="8feed-136">Advanced binding</span></span>

### <a name="binding-scopes"></a><span data-ttu-id="8feed-137">Bindungsbereiche</span><span class="sxs-lookup"><span data-stu-id="8feed-137">Binding scopes</span></span>

<span data-ttu-id="8feed-138">Für den Zugriff auf verschiedene Bindungsbereiche sind einige reservierte Schlüsselwörter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8feed-138">There are a few reserved keywords to access various binding scopes.</span></span> 

<span data-ttu-id="8feed-139">*Hinweis:* Nicht alle diese Schlüsselwörter sind in der Vorschau implementiert.</span><span class="sxs-lookup"><span data-stu-id="8feed-139">*Note:* not all of these are implemented in the preview.</span></span>

```json
{
    "{<property>}": "Implicitly binds to `$data.<property>`",
    "$data": "The current data object",
    "$root": "The root data object. Useful when iterating to escape to parent object",
    "$index": "The current index when iterating",
    "$host": "Access properties of the host *(not working yet)*"
}
```

### <a name="assigning-a-data-context-to-elements"></a><span data-ttu-id="8feed-140">Zuweisen eines Datenkontexts zu Elementen</span><span class="sxs-lookup"><span data-stu-id="8feed-140">Assigning a data context to elements</span></span>

<span data-ttu-id="8feed-141">Wenn Sie einem Element einen „Datenkontext“ zuweisen möchten, fügen Sie dem-Element ein `$data`-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="8feed-141">To assign a "data context" to any element add a `$data` attribute to the element.</span></span>

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

## <a name="repeating-items-in-an-array"></a><span data-ttu-id="8feed-142">Wiederholen von Elementen in einem Array</span><span class="sxs-lookup"><span data-stu-id="8feed-142">Repeating items in an array</span></span>

<span data-ttu-id="8feed-143">Dieser Teil hat etwas von „dunkler Magie“.</span><span class="sxs-lookup"><span data-stu-id="8feed-143">This part is a bit of "dark magic".</span></span> <span data-ttu-id="8feed-144">Feedback willkommen.</span><span class="sxs-lookup"><span data-stu-id="8feed-144">Feedback welcome.</span></span>

* <span data-ttu-id="8feed-145">Wenn die `$data`-Eigenschaft eines „Adaptive Karte“-Elements an ein **-Array** gebunden ist, dann wird das **-Element selbst für jedes Element im Array wiederholt.**</span><span class="sxs-lookup"><span data-stu-id="8feed-145">If an Adaptive Card element's `$data` property is bound to an **array**, then the **element itself will be repeated for each item in the array.**</span></span> 
* <span data-ttu-id="8feed-146">Alle in Eigenschaftswerten verwendeten Bindungsausdrücke (`{myProperty}`) werden auf das **einzelne Element** innerhalb des Arrays festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8feed-146">Any binding expressions (`{myProperty}`) used in property values will be scoped to the **individual item** within the array.</span></span>
* <span data-ttu-id="8feed-147">Wenn Sie eine Bindung an ein Array von Zeichenfolgen herstellen, verwenden Sie `{$data}`, um auf das einzelne Zeichenfolgenelement zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8feed-147">If binding to an array of strings, use `{$data}` to access the individual string element.</span></span> <span data-ttu-id="8feed-148">Beispiel: `"text": "{$data}"`</span><span class="sxs-lookup"><span data-stu-id="8feed-148">E.g., `"text": "{$data}"`</span></span>

<span data-ttu-id="8feed-149">Der `TextBlock` unten wird beispielsweise dreimal wiederholt, da sein `$data`-Objekt ein Array ist.</span><span class="sxs-lookup"><span data-stu-id="8feed-149">For example, the `TextBlock` below will be repeated 3 times since it's `$data` is an array.</span></span> <span data-ttu-id="8feed-150">Beachten Sie, dass die `text`-Eigenschaft an die `name`-Eigenschaft eines einzelnen Objekts innerhalb des Arrays gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="8feed-150">Notice how the `text` property is bound to the `name` property of an individual object within the array.</span></span> 

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

<span data-ttu-id="8feed-151">**Ergebnis:**</span><span class="sxs-lookup"><span data-stu-id="8feed-151">**Resulting in:**</span></span>

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

## <a name="functions"></a><span data-ttu-id="8feed-152">Funktionen</span><span class="sxs-lookup"><span data-stu-id="8feed-152">Functions</span></span>

<span data-ttu-id="8feed-153">Keine Vorlagensprache kommt ohne einige Hilfsfunktionen aus.</span><span class="sxs-lookup"><span data-stu-id="8feed-153">No templating language is complete without some helper functions.</span></span> <span data-ttu-id="8feed-154">Wir werden einen Standardsatz von Funktionen bereitstellen, die mit jedem SDK verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8feed-154">We will provide a standard set of functions that work on every SDK.</span></span> 

<span data-ttu-id="8feed-155">Die hier verwendete Syntax ist noch in der Schwebe, also kehren Sie bald zurück. Hier ist aber schon ein erster Einstieg in das, was wir planen:</span><span class="sxs-lookup"><span data-stu-id="8feed-155">The syntax here is still up in the air so please check back soon, but here's a start of what we're planning:</span></span>

### <a name="string-functions"></a><span data-ttu-id="8feed-156">Zeichenfolgenfunktionen</span><span class="sxs-lookup"><span data-stu-id="8feed-156">String functions</span></span>

* <span data-ttu-id="8feed-157">substr</span><span class="sxs-lookup"><span data-stu-id="8feed-157">substr</span></span>
* <span data-ttu-id="8feed-158">indexOf *(noch nicht funktionsfähig)*</span><span class="sxs-lookup"><span data-stu-id="8feed-158">indexOf *(not working yet)*</span></span>
* <span data-ttu-id="8feed-159">toUpper *(noch nicht funktionsfähig)*</span><span class="sxs-lookup"><span data-stu-id="8feed-159">toUpper *(not working yet)*</span></span>
* <span data-ttu-id="8feed-160">toLower *(noch nicht funktionsfähig)*</span><span class="sxs-lookup"><span data-stu-id="8feed-160">toLower *(not working yet)*</span></span>

### <a name="number-functions"></a><span data-ttu-id="8feed-161">Number-Funktionen</span><span class="sxs-lookup"><span data-stu-id="8feed-161">Number functions</span></span>

* <span data-ttu-id="8feed-162">Formatierung (Währung, Dezimal usw.) *(noch nicht funktionsfähig)*</span><span class="sxs-lookup"><span data-stu-id="8feed-162">Formatting (currency, decimal, etc) *(not working yet)*</span></span>

### <a name="date-functions"></a><span data-ttu-id="8feed-163">Datumsfunktionen</span><span class="sxs-lookup"><span data-stu-id="8feed-163">Date functions</span></span>

* <span data-ttu-id="8feed-164">Parsen bekannter Datumszeichenfolgen-Formate *(noch nicht funktionsfähig)*</span><span class="sxs-lookup"><span data-stu-id="8feed-164">Parsing well-known date string formats *(not working yet)*</span></span>
* <span data-ttu-id="8feed-165">Formatierung für bekannte Datums-/Uhrzeitdarstellungen *(noch nicht funktionsfähig)*</span><span class="sxs-lookup"><span data-stu-id="8feed-165">Formatting for well-known date/time representations *(not working yet)*</span></span>

### <a name="conditional-functions"></a><span data-ttu-id="8feed-166">Bedingte Funktionen</span><span class="sxs-lookup"><span data-stu-id="8feed-166">Conditional functions</span></span>

* <span data-ttu-id="8feed-167">if(*expression*, *trueValue*, *falseValue*)</span><span class="sxs-lookup"><span data-stu-id="8feed-167">if(*expression*, *trueValue*, *falseValue*)</span></span>

<span data-ttu-id="8feed-168">**`if`-Beispiel**</span><span class="sxs-lookup"><span data-stu-id="8feed-168">**`if` example**</span></span>

```json
{
    "type": "TextBlock",
    "color": "{if(priceChange >= 0, 'good', 'attention')}"
}
```

### <a name="data-manipulation"></a><span data-ttu-id="8feed-169">Datenbearbeitung</span><span class="sxs-lookup"><span data-stu-id="8feed-169">Data manipulation</span></span>

* <span data-ttu-id="8feed-170">JSON.parse – Möglichkeit, eine JSON-Zeichenfolge zu parsen</span><span class="sxs-lookup"><span data-stu-id="8feed-170">JSON.parse - ability to parse a JSON string</span></span> 

<span data-ttu-id="8feed-171">**`JSON.parse`-Beispiel**</span><span class="sxs-lookup"><span data-stu-id="8feed-171">**`JSON.parse` example**</span></span>

<span data-ttu-id="8feed-172">Dies ist eine Azure DevOps-Antwort, bei der die `message`-Eigenschaft eine serialisierte JSON-Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="8feed-172">This is an Azure DevOps response where the `message` property is a JSON-serialized string.</span></span> <span data-ttu-id="8feed-173">Um auf Werte innerhalb der Zeichenfolge zuzugreifen, muss die Funktion `JSON.parse` in der Vorlage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8feed-173">In order to access values within the string, we need to use the `JSON.parse` function in our template.</span></span>

<span data-ttu-id="8feed-174">**Daten**</span><span class="sxs-lookup"><span data-stu-id="8feed-174">**Data**</span></span> 

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

<span data-ttu-id="8feed-175">**Nutzung**</span><span class="sxs-lookup"><span data-stu-id="8feed-175">**Usage**</span></span>

```json
{
    "type": "TextBlock",
    "text": "{JSON.parse(message).releaseName}"
}
```

<span data-ttu-id="8feed-176">**Ergebnis**</span><span class="sxs-lookup"><span data-stu-id="8feed-176">**Resulting In**</span></span>

```json
{
    "type": "TextBlock",
    "text": "Release-104"
}
```

### <a name="custom-functions"></a><span data-ttu-id="8feed-177">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="8feed-177">Custom functions</span></span>

<span data-ttu-id="8feed-178">Wir möchten sicherstellen, dass Hosts benutzerdefinierte Funktionen hinzufügen können. Daher wird eine robuste Fallbackunterstützung für nicht unterstützte Funktionen benötigt.</span><span class="sxs-lookup"><span data-stu-id="8feed-178">We want to make sure Hosts can add custom functions, which means we need robust support for fallback support if a function isn't supported.</span></span> <span data-ttu-id="8feed-179">Dies wird derzeit noch untersucht.</span><span class="sxs-lookup"><span data-stu-id="8feed-179">We are still evaluating this.</span></span>

## <a name="conditional-layout"></a><span data-ttu-id="8feed-180">Bedingtes Layout</span><span class="sxs-lookup"><span data-stu-id="8feed-180">Conditional layout</span></span>

<span data-ttu-id="8feed-181">Um ein komplettes Element zu entfernen, wenn eine Bedingung erfüllt ist, verwenden Sie die `$when`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8feed-181">To drop an entire element if a condition is met, use the `$when` property.</span></span> <span data-ttu-id="8feed-182">Wird `$when` zu `false` ausgewertet, wird das Element dem Benutzer nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8feed-182">If `$when` evaluates to `false` the element will not appear to the user.</span></span>

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

### <a name="composing-templates"></a><span data-ttu-id="8feed-183">Zusammensetzen von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="8feed-183">Composing templates</span></span>

<span data-ttu-id="8feed-184">Derzeit wird das Zusammenstellen von Vorlagenteilen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8feed-184">Currently there is no support for composing template "parts" together.</span></span> <span data-ttu-id="8feed-185">Wir untersuchen jedoch Optionen und hoffen, bald mehr berichten zu können.</span><span class="sxs-lookup"><span data-stu-id="8feed-185">But we are exploring options and hope to share more soon.</span></span> <span data-ttu-id="8feed-186">Alle Ideen sind willkommen!</span><span class="sxs-lookup"><span data-stu-id="8feed-186">Any thoughts here welcome!</span></span>


## <a name="examples"></a><span data-ttu-id="8feed-187">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8feed-187">Examples</span></span>

<span data-ttu-id="8feed-188">Durchsuchen Sie die aktualisierte [Beispielseite](https://adaptivecards.io/samples), um alle möglichen neuen Kartenvorlagen zu erkunden.</span><span class="sxs-lookup"><span data-stu-id="8feed-188">Browse the updated [Samples page](https://adaptivecards.io/samples) to explore all sorts of new templated cards.</span></span>
