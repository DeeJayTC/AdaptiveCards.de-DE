---
title: Erste Schritte
author: matthidinger
ms.author: mahiding
ms.date: 11/9/2017
ms.topic: article
ms.openlocfilehash: c9a0ad07ba5fefbcdc35239591c02fe0720b5b66
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "77454843"
---
# <a name="getting-started"></a>Erste Schritte 

Eine adaptive Karte ist ein JSON-serialisiertes Kartenobjektmodell.

## <a name="adaptive-card-structure"></a>Struktur von adaptiven Karten

Die grundlegende Struktur einer Karte ist wie folgt:

* `AdaptiveCard`: Das Stammobjekt beschreibt die adaptive Karte, u. a. ihre Elementzusammensetzung, ihre Aktionen, wie sie gesprochen werden soll und die zum Rendern erforderliche Schemaversion.
* `body`: Der Text der Karte besteht aus Bausteinen, die auch als `elements` bezeichnet werden. Elemente können in nahezu unbegrenzten Anordnungen zusammengesetzt werden, um viele Typen von Karten zu erstellen. 
* `actions`: Viele Karten haben einen Satz von Aktionen, die ein Benutzer ausführen kann. Diese Eigenschaft beschreibt die Aktionen, die in der Regel in einer „Aktionsleiste“ am unteren Rand gerendert werden.

### <a name="example-card"></a>Beispielkarte

Diese Beispielkarte enthält eine einzelne Textzeile gefolgt von einem Bild.

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

## <a name="type-property"></a>`Type`-Eigenschaft

Jedes Element verfügt über eine `type`-Eigenschaft, die angibt, um welche Art von Objekt es sich handelt. Auf der oben gezeigten Karte siehst du zwei Elemente: `TextBlock` und `Image`.

Alle Elemente einer adaptiven Karte sind **vertikal gestapelt** und **auf die Breite des übergeordneten Elements erweitert**  (wie bei `display: block` in HTML). Mit `ColumnSet` kannst du jedoch nebeneinander angeordnete Containerspalten erstellen.

## <a name="adaptive-elements"></a>Adaptive Elemente

Die grundlegenden Elemente sind:

* **TextBlock**: Fügt einen Textblock mit Eigenschaften hinzu, die steuern, wie der Text aussieht.
* **Image**: Fügt ein Bild mit Eigenschaften hinzu, die steuern, wie das Bild aussieht.

## <a name="container-elements"></a>Containerelemente

Karten verfügen unter Umständen auch über Container, die eine Sammlung untergeordneter Elemente anordnen.

* **Container**: Definiert eine Auflistung von Elementen.
* **ColumnSet/Column**: Definiert eine Sammlung von Spalten, jede Spalte ist ein Container.
* **FactSet**: Container mit Fakten
* **ImageSet**: Container mit Bildern, damit die Benutzeroberfläche für die Sammlung von Bildern einen entsprechenden Bilderkatalog anzeigen kann

## <a name="input-elements"></a>Eingabeelemente

Mit Eingabeelementen kannst du die native Benutzeroberfläche zum Erstellen einfacher Formulare auffordern:

* **Input.Text**: Abrufen von Textinhalt vom Benutzer
* **Input.Date**: Abrufen eines Datums vom Benutzer
* **Input.Time**: Abrufen einer Uhrzeit vom Benutzer
* **Input.Number**: Abrufen einer Nummer vom Benutzer
* **Input.ChoiceSet**: Bereitstellen von Auswahlmöglichkeiten, aus denen der Benutzer wählen kann
* **Input.Toggle**: Bereitstellen einer Auswahl aus zwei Elementen, aus denen der Benutzer wählen kann

## <a name="actions"></a>Aktionen

Aktionen fügen der Karte Schaltflächen hinzu. Diese können eine Reihe von Aktionen ausführen, wie etwa das Öffnen einer URL oder das Senden von Daten.

* **Action.OpenUrl**: Die Schaltfläche öffnet eine externe URL zur Ansicht.
* **Action.ShowCard**: Fordert eine untergeordnete Karte an, die dem Benutzer angezeigt wird.
* **Action.Submit**: Fordert an, dass alle Eingabeelemente in einem Objekt zusammengefasst werden, das dir anschließend über eine von der Hostanwendung definierte Methode geschickt wird.

> **Example Action.Submit**: „Action.Submit“ sendet per Skype eine Bot Framework-Botaktivität zurück an den Bot mit der **Value**-Eigenschaft, die ein Objekt mit allen Eingabedaten dazu enthält.

## <a name="learn-more"></a>Weitere Informationen

* Lass dich von den [Beispielkarten](http://adaptivecards.io/samples/) inspirieren.
* Durchsuche die verfügbaren Elemente mit dem [Schema-Explorer](http://adaptivecards.io/explorer)
* Erstelle eine Karte mit dem [interaktiven Visualizer](http://adaptivecards.io/visualizer/)
* [Wende dich an uns](http://adaptivecards.io/connect), wenn du Feedback hast.
