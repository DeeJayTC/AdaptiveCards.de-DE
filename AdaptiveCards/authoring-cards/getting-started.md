---
title: Erste Schritte
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: 9d363da0c10b242e23d2594984292fcc1f31382f
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552682"
---
# <a name="getting-started"></a>Erste Schritte 

Eine Adaptive Card handelt es sich um eine JSON-serialisierten Karte-Objektmodell.

## <a name="adaptive-card-structure"></a>Adaptive Card-Struktur

Die grundlegende Struktur einer Karte lautet wie folgt aus:

* `AdaptiveCard` -Das Stammobjekt beschreibt die AdaptiveCard selbst, wie z.B. die Zusammensetzung des Elements die Aktionen, wie sie gesprochene werden soll und die Schemaversion, die zum Rendern erforderlich.
* `body` -Der Text der Karte besteht aus Bausteinen – bekannt als `elements`. Elemente können in nahezu unbegrenzte Anordnungen viele Typen von Karten erstellen zusammengestellt werden. 
* `actions` – Für viele Karten, haben einen Satz von Aktionen, die ein Benutzer darauf ausführen kann. Diese Eigenschaft beschreibt die Aktionen, die in der Regel in "Aktionsleiste" am unteren Rand gerendert werden.

### <a name="example-card"></a>Beispiel-Karte

Diese Beispiel-Karte eine einzelne Textzeile gefolgt von einem Bild enthält.

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": [
        {
            "type": "TextBlock",
            "text": "Here is a ninja cat"
        },
        {
            "type": "Image",
            "url": "http://adaptivecards.io/content/cats/1.png"
        }
    ]
}
```

## <a name="type-property"></a>`Type` Eigenschaft

Jedes Element verfügt über eine `type` Eigenschaft, der angibt, welche Art von Objekt ist. Betrachten die oben genannten Karte, sehen Sie haben wir zwei Elementen, die eine `TextBlock` und `Image`.

Alle Elemente der Adaptive Card **vertikal gestapelt** und **erweitern, der die Breite des übergeordneten** (denken `display: block` im HTML-Format). Sie können jedoch eine `ColumnSet` , Seite-an-Seite-Spalten von Containern zu erstellen.

## <a name="adaptive-elements"></a>Adaptive Elemente

Die grundlegendsten Elemente sind:

* **TextBlock** -Fügt einen Block von Text mit Eigenschaften, die steuern, wie der Text aussieht
* **Image** -Fügt ein Bild mit Eigenschaften, die steuern, wie das Bild aussieht

## <a name="container-elements"></a>Containerelemente

Karten können auch Container verfügen, die eine Auflistung der untergeordneten Elemente anzuordnen.

* **Container** -definiert eine eine Auflistung von Elementen
* **Spaltensatz-Spalte** -definiert eine Auflistung von Spalten, jede Spalte ist ein Container
* **FactSet** -Container von Fakten
* **ImageSet** -von Containerimages, damit die Benutzeroberfläche entsprechende anzeigen kann Fotos Oberfläche für den Anwendungskatalog für eine Sammlung von Bildern.

## <a name="input-elements"></a>Input-Elemente

Input-Elemente können Sie native Benutzeroberfläche Erstellung einfacher Formulare anfordern:

* **Input.Text** -Text-Inhalt wird vom Benutzer abzurufen.
* **Input.Date** -erhalten Sie vom Benutzer ein Datum
* **Input.Time** -erhalten Sie eine Zeit vom Benutzer
* **Input.Number** – eine Anzahl vom Benutzer abrufen
* **Input.ChoiceSet** : Weisen Sie dem Benutzer eine Reihe von Auswahlmöglichkeiten und diese auswählen
* **Input.Toggle** : Weisen Sie dem Benutzer eine einzelne Auswahl zwischen zwei Elementen, und diese auswählen

## <a name="actions"></a>Aktionen

Aktionen Hinzufügen von Schaltflächen auf der Karte. Diese können eine Reihe von Aktionen, wie Sie eine URL öffnen oder Senden von Daten führen.

* **Action.OpenUrl** -die Schaltfläche öffnet eine externe URL für die Anzeige
* **Action.ShowCard** -Anforderungen von einer untergeordneten Karte, die dem Benutzer angezeigt werden.
* **Action.Submit** -stellen Sie für alle Elemente mit der Eingabe in ein Objekt gesammelt werden, um die über eine Methode, die von der hostanwendung definiert dann an Sie gesendet wird.

> **Beispiel-Action.Submit**: Mit Skype, ein Action.Submit sendet einen Bot Framework Bot Aktivität an den Bot mit den **Wert** Eigenschaft, die mit einem Objekt mit allen der Eingabedaten auf.

## <a name="learn-more"></a>Weitere Informationen

* [Beispiel-Karten Durchsuchen](http://adaptivecards.io/samples/) inspirieren
* Verwenden der [Schema-Explorer](http://adaptivecards.io/explorer) um die verfügbaren Elemente zu suchen.
* Erstellen einer Karte mit den [interaktive Schnellansicht](http://adaptivecards.io/visualizer/)
* [Kontakt aufnehmen](http://adaptivecards.io/connect) mit Sie haben Feedback
