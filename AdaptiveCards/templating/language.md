---
title: Vorlagen Sprache für Adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 42a1f43fbcfe1416820637af750acc960b9effde
ms.sourcegitcommit: 16a274ce5596001a1c5ab252d9d2a3db6a5a9a0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73750398"
---
# <a name="adaptive-cards-template-language"></a>Vorlagen Sprache für Adaptive Karten

Durch Vorlagen wird die Trennung von **Daten** vom **Layout** in der adaptiven Karte ermöglicht. Die Vorlagen Sprache ist die Syntax, die zum Erstellen einer Vorlage verwendet wird. 

> Eine Übersicht über die Vorlagen für [Adaptive Karten](index.md) finden Sie unter.

> [!IMPORTANT] 
> 
> Diese Features befinden sich **in der Vorschauphase und können geändert werden**. Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.

Beim Erstellen einer Vorlage können Sie die Daten Inline mit der `AdaptiveCard` Nutzlast oder zur Laufzeit mithilfe der Vorlagen- [sdche](sdk.md)angeben.

## <a name="specify-data-within-the-card"></a>Daten innerhalb der Karte angeben

Um Daten direkt innerhalb der Karten Nutzlast bereitzustellen, fügen Sie Ihrem `AdaptiveCard` einfach ein `$data` Attribut hinzu (siehe unten).

## <a name="binding-to-the-data"></a>Binden an die Daten

Sie können eine Bindung an die Daten innerhalb der `body` oder `actions` der Karte herstellen.

* Die Bindungs Syntax beginnt mit `{` und endet mit `}`. Beispielsweise `{myProperty}`
* Punkt Schreibweise für den Zugriff auf untergeordnete Objekte
* Indexer-Syntax zum Abrufen von Eigenschaften nach Schlüsseln oder Elementen in einem Array
* Ordnungsgemäße NULL-Behandlung für Deep-Hierarchien
* *Dokumentation zur Escapesyntax in Kürze verfügbar*

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

## <a name="separating-the-template-from-the-data"></a>Trennen der Vorlage von den Daten

Alternativ (und wahrscheinlicher) erstellen Sie eine wiederverwendbare Karte "Template", ohne die Daten einzubeziehen. Diese Vorlage kann als Datei gespeichert und der Quell Code Verwaltung hinzugefügt werden.

**EmployeeCardTemplate.json**

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

Anschließend können Sie die Daten mit den Vorlagen- [sdchen](sdk.md)laden und zur Laufzeit bereitstellen.

**JavaScript-Beispiel**

Verwenden des Pakets [adaptivecards-](https://npmjs.com/package/adaptivecards-templating) Vorlagen.

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

## <a name="designer-support"></a>Designer Unterstützung

Der adaptiver Karten-Designer wurde aktualisiert, um Vorlagen zu unterstützen. 

> Probieren Sie es aus:  **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**

[Bild ![](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)

* **Beispiel Daten-Editor** : Geben Sie hier Beispiel Daten an, um die Daten gebundene Karte im Vorschaumodus anzuzeigen. In diesem Bereich gibt es eine kleine Schaltfläche, um die Datenstruktur aus den vorhandenen Beispiel Daten aufzufüllen.
* **Datenstruktur** : Dies ist die Struktur der Beispiel Daten. Felder können auf die Entwurfs Oberfläche gezogen werden, um eine Bindung an Sie zu erstellen. 
* **Vorschaumodus** : Klicken Sie auf die Symbolleisten Schaltfläche, um zwischen den Funktionen "Bearbeiten" und "Sample-Data-Preview" zu wechseln.
* **Sample öffnen** : Klicken Sie auf diese Schaltfläche, um verschiedene Beispiel Nutzlasten zu öffnen.

## <a name="advanced-binding"></a>Erweiterte Bindung

### <a name="binding-scopes"></a>Bindungs Bereiche

Für den Zugriff auf verschiedene Bindungs Bereiche sind einige reservierte Schlüsselwörter verfügbar. 

*Hinweis:* nicht alle in der Vorschauversion sind implementiert.

```json
{
    "{<property>}": "Implicitly binds to `$data.<property>`",
    "$data": "The current data object",
    "$root": "The root data object. Useful when iterating to escape to parent object",
    "$index": "The current index when iterating",
    "$host": "Access properties of the host *(not working yet)*"
}
```

### <a name="assigning-a-data-context-to-elements"></a>Zuweisen eines Daten Kontexts zu Elementen

Wenn Sie einem Element einen "Datenkontext" zuweisen möchten, fügen Sie dem-Element ein `$data`-Attribut hinzu.

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

## <a name="repeating-items-in-an-array"></a>Wiederholen von Elementen in einem Array

Dieser Teil ist ein wenig "dunkle Magie". Feedback willkommen.

* Wenn die `$data`-Eigenschaft der Objekte auf ein **Array**festgelegt ist, **wird das Objekt selbst für jedes Element im Array wiederholt.** 
* Wenn Sie wiederholt werden, werden `$data`, die in Eigenschafts Bindungen verwendet werden, auf das **einzelne Element** innerhalb des Arrays festgelegt.

Beispielsweise wird das unten angegebene `TextBlock` dreimal wiederholt, da es `$data` ein Array ist. Beachten Sie, dass die `text`-Eigenschaft an die `name`-Eigenschaft eines einzelnen Objekts innerhalb des Arrays gebunden ist. 

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

**Ergebnis:**

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

## <a name="functions"></a>Funktionen

Keine Vorlagen Sprache ist ohne einige Hilfsfunktionen fertiggestellt. Wir werden einen Standardsatz von Funktionen bereitstellen, die für jedes SDK funktionieren. 

Die hier verwendete Syntax ist immer noch in der Luft, also schauen Sie es bald an, aber hier ist ein Einstieg in das, was wir planen:

### <a name="string-functions"></a>Zeichen folgen Funktionen

* substr
* IndexOf *(noch nicht funktioniert)*
* *ToUpper(noch nicht funktioniert)*
* ToLower *(noch nicht funktioniert)*

### <a name="number-functions"></a>Number-Funktionen

* Formatierung (Currency, Decimal usw.) *(noch nicht funktioniert)*

### <a name="date-functions"></a>Datumsfunktionen

* Die Verarbeitung von bekannten Datums Zeichen folgen Formaten *(noch nicht funktioniert)*
* Formatierung für bekannte Datums-/uhrzeitanstellungen *(noch nicht funktioniert)*

### <a name="conditional-functions"></a>Bedingte Funktionen

* if (*Ausdruck*, *TrueValue*, *FalseValue*)

**`if` Beispiel**

```json
{
    "type": "TextBlock",
    "color": "{if(priceChange >= 0, 'good', 'attention')}"
}
```

### <a name="data-manipulation"></a>Datenbearbeitung

* JSON. Analyse-Möglichkeit zum Analysieren einer JSON-Zeichenfolge 

**`JSON.parse` Beispiel**

Dies ist eine Azure devops-Antwort, bei der die `message`-Eigenschaft eine JSON-serialisierte Zeichenfolge ist. Um auf Werte innerhalb der Zeichenfolge zuzugreifen, muss die `JSON.parse`-Funktion in der Vorlage verwendet werden.

**Daten** 

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

**Nutzung**

```json
{
    "type": "TextBlock",
    "text": "{JSON.parse(message).releaseName}"
}
```

**Ergebnis**

```json
{
    "type": "TextBlock",
    "text": "Release-104"
}
```

### <a name="custom-functions"></a>Benutzerdefinierte Funktionen

Wir möchten sicherstellen, dass Hosts benutzerdefinierte Funktionen hinzufügen können. das bedeutet, dass wir eine robuste Unterstützung für die Ausweich Unterstützung benötigen, wenn eine Funktion nicht unterstützt wird Wir bewerten dies noch einmal.

## <a name="conditional-layout"></a>Bedingtes Layout

Wenn Sie ein gesamtes Element löschen möchten, wenn eine Bedingung erfüllt ist, verwenden Sie die `$when`-Eigenschaft. Wenn `$when` ausgewertet wird `false` wird das Element dem Benutzer nicht angezeigt.

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

### <a name="composing-templates"></a>Verfassen von Vorlagen

Derzeit wird das Zusammenstellen von Vorlagen "Parts" nicht unterstützt. Wir untersuchen jedoch die Optionen und hoffen, dass Sie bald mehr freigeben können. Hier sind alle Gedanken Willkommen!


## <a name="examples"></a>Beispiele

Durchsuchen Sie die aktualisierte Beispiel [Seite](https://adaptivecards.io/samples) , um alle möglichen neuen, auf Vorlagen basierenden Karten zu untersuchen.
