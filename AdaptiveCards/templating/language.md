---
title: Vorlagensprache für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 08/01/2019
ms.topic: article
ms.openlocfilehash: 2c583f774451e60f825cd8fd2c38f2ea34c2f8de
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145400"
---
# <a name="adaptive-cards-template-language"></a>Vorlagensprache für adaptive Karten

Durch Vorlagen wird die Trennung von **Daten** und **Layout** auf Ihrer adaptiven Karte ermöglicht. Die Vorlagensprache ist die Syntax, die zum Erstellen einer Vorlage verwendet wird. 

> Hier finden Sie einen [Überblick über Vorlagen für adaptive Karten](index.md).

> [!IMPORTANT] 
> 
> Diese Features befinden sich **in der Vorschauphase und können geändert werden**. Ihr Feedback ist nicht nur willkommen, sondern wichtig, um sicherzustellen, dass **wir** Ihnen die benötigten Features bieten.

Wenn Sie eine Vorlage erstellen, können Sie die Daten inline mit der `AdaptiveCard`-Nutzlast oder zur Laufzeit mithilfe der [Vorlagen-SDKs](sdk.md) angeben.

## <a name="specify-data-within-the-card"></a>Daten innerhalb der Karte angeben

Um Daten direkt innerhalb der Kartennutzlast bereitzustellen, fügen Sie Ihrer `AdaptiveCard` einfach ein `$data`-Attribut hinzu (siehe unten).

## <a name="binding-to-the-data"></a>Bindung an Daten

Sie können eine Bindung an Daten innerhalb von `body` oder `actions` der Karte herstellen.

* Die Bindungssyntax beginnt mit `{` und endet mit `}`. Beispiel: `{myProperty}`
* Punkt-Notation für den Zugriff auf untergeordnete Objekte
* Indexersyntax zum Abrufen von Eigenschaften nach Schlüsseln oder Elementen in einem Array
* Ordnungsgemäße NULL-Behandlung für tiefen Hierarchien
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

## <a name="separating-the-template-from-the-data"></a>Trennen von Vorlage und Daten

Alternativ (und wahrscheinlicher) erstellen Sie eine wiederverwendbare Karte „Vorlage“ ohne Daten. Diese Vorlage kann als Datei gespeichert und dem Quellsteuerelement hinzugefügt werden.

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

Laden Sie die Daten dann zur Laufzeit, und stellen Sie sie mithilfe des [Vorlagen-SDKs](sdk.md) bereit.

**JavaScript-Beispiel**

Verwenden des Pakets [adaptivecards-templating](https://npmjs.com/package/adaptivecards-templating).

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

## <a name="designer-support"></a>Designerunterstützung

Der Designer für adaptive Karten wurde aktualisiert, um Vorlagen zu unterstützen. 

> Jetzt testen unter: **[https://adaptivecards.io/designer](https://adaptivecards.io/designer)**

[![Abbildung](https://user-images.githubusercontent.com/1432195/53214462-88d46980-3601-11e9-908d-253a1bb940a8.png)](https://adaptivecards.io/designer)

* **Beispieldaten-Editor** – Geben Sie hier Beispieldaten an, um die datengebundene Karte im Vorschaumodus anzuzeigen. In diesem Bereich gibt es eine kleine Schaltfläche, zum Auffüllen der Datenstruktur mit den vorhandenen Beispieldaten.
* **Datenstruktur** – Dies ist die Struktur der Beispieldaten. Felder können auf die Entwurfsoberfläche gezogen werden, um eine Bindung zu erstellen. 
* **Vorschaumodus** – Klicken Sie auf die Symbolleistenschaltfläche, um zwischen der „edit-experience“ und der „sample-data-preview“ zu wechseln.
* **Beispiel öffnen** – Klicken Sie auf diese Schaltfläche, um verschiedene Beispielnutzlasten zu öffnen.

## <a name="advanced-binding"></a>Erweiterte Bindung

### <a name="binding-scopes"></a>Bindungsbereiche

Für den Zugriff auf verschiedene Bindungsbereiche sind einige reservierte Schlüsselwörter verfügbar. 

*Hinweis:* Nicht alle diese Schlüsselwörter sind in der Vorschau implementiert.

```json
{
    "{<property>}": "Implicitly binds to `$data.<property>`",
    "$data": "The current data object",
    "$root": "The root data object. Useful when iterating to escape to parent object",
    "$index": "The current index when iterating",
    "$host": "Access properties of the host *(not working yet)*"
}
```

### <a name="assigning-a-data-context-to-elements"></a>Zuweisen eines Datenkontexts zu Elementen

Wenn Sie einem Element einen „Datenkontext“ zuweisen möchten, fügen Sie dem-Element ein `$data`-Attribut hinzu.

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

Dieser Teil hat etwas von „dunkler Magie“. Feedback willkommen.

* Wenn die `$data`-Eigenschaft eines „Adaptive Karte“-Elements an ein **-Array** gebunden ist, dann wird das **-Element selbst für jedes Element im Array wiederholt.** 
* Alle in Eigenschaftswerten verwendeten Bindungsausdrücke (`{myProperty}`) werden auf das **einzelne Element** innerhalb des Arrays festgelegt.
* Wenn Sie eine Bindung an ein Array von Zeichenfolgen herstellen, verwenden Sie `{$data}`, um auf das einzelne Zeichenfolgenelement zuzugreifen. Beispiel: `"text": "{$data}"`

Der `TextBlock` unten wird beispielsweise dreimal wiederholt, da sein `$data`-Objekt ein Array ist. Beachten Sie, dass die `text`-Eigenschaft an die `name`-Eigenschaft eines einzelnen Objekts innerhalb des Arrays gebunden ist. 

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

Keine Vorlagensprache kommt ohne einige Hilfsfunktionen aus. Wir werden einen Standardsatz von Funktionen bereitstellen, die mit jedem SDK verwendet werden können. 

Die hier verwendete Syntax ist noch in der Schwebe, also kehren Sie bald zurück. Hier ist aber schon ein erster Einstieg in das, was wir planen:

### <a name="string-functions"></a>Zeichenfolgenfunktionen

* substr
* indexOf *(noch nicht funktionsfähig)*
* toUpper *(noch nicht funktionsfähig)*
* toLower *(noch nicht funktionsfähig)*

### <a name="number-functions"></a>Number-Funktionen

* Formatierung (Währung, Dezimal usw.) *(noch nicht funktionsfähig)*

### <a name="date-functions"></a>Datumsfunktionen

* Parsen bekannter Datumszeichenfolgen-Formate *(noch nicht funktionsfähig)*
* Formatierung für bekannte Datums-/Uhrzeitdarstellungen *(noch nicht funktionsfähig)*

### <a name="conditional-functions"></a>Bedingte Funktionen

* if(*expression*, *trueValue*, *falseValue*)

**`if`-Beispiel**

```json
{
    "type": "TextBlock",
    "color": "{if(priceChange >= 0, 'good', 'attention')}"
}
```

### <a name="data-manipulation"></a>Datenbearbeitung

* JSON.parse – Möglichkeit, eine JSON-Zeichenfolge zu parsen 

**`JSON.parse` Beispiel**

Dies ist eine Azure DevOps-Antwort, bei der die `message`-Eigenschaft eine serialisierte JSON-Zeichenfolge ist. Um auf Werte innerhalb der Zeichenfolge zuzugreifen, muss die Funktion `JSON.parse` in der Vorlage verwendet werden.

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

Wir möchten sicherstellen, dass Hosts benutzerdefinierte Funktionen hinzufügen können. Daher wird eine robuste Fallbackunterstützung für nicht unterstützte Funktionen benötigt. Dies wird derzeit noch untersucht.

## <a name="conditional-layout"></a>Bedingtes Layout

Um ein komplettes Element zu entfernen, wenn eine Bedingung erfüllt ist, verwenden Sie die `$when`-Eigenschaft. Wird `$when` zu `false` ausgewertet, wird das Element dem Benutzer nicht angezeigt.

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

### <a name="composing-templates"></a>Zusammensetzen von Vorlagen

Derzeit wird das Zusammenstellen von Vorlagenteilen nicht unterstützt. Wir untersuchen jedoch Optionen und hoffen, bald mehr berichten zu können. Alle Ideen sind willkommen!


## <a name="examples"></a>Beispiele

Durchsuchen Sie die aktualisierte [Beispielseite](https://adaptivecards.io/samples), um alle möglichen neuen Kartenvorlagen zu erkunden.
