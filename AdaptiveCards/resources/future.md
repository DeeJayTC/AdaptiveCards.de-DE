---
title: Mit Adaptive Cards-Roadmap
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: 6c6e14108caefa8dd1ff854b29d4651fe9b2d15c
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553482"
---
# <a name="future-work"></a>Zukünftige Arbeit

Während wir hervorragende Bearbeitung mit adaptive Cards definieren vorgenommen haben, ist immer noch viel zu tun. Unser Anliegen ist es, über aktive entwicklercommunitys wie Botness, und hervorragende Partner Wie Slack und Kik, wir eine hervorragende Ökosystem von Cross-Platform-Karten erstellen können.

## <a name="roadmap"></a>Roadmap

Sehen Sie unsere [aktuellen (nicht endgültige) Roadmap für die hier](https://github.com/Microsoft/AdaptiveCards/projects/8). Beachten Sie, dass alles hier unterliegt ist keine Garantie der Lieferung.

## <a name="future-ideas"></a>Zukünftige Ideen

Im folgenden werden einige zukünftigen Ideen, die wir erhalten haben, die einfach in der Phase Brainstorming sind. Wenn Sie eines dieser interessiert sind, informieren Sie uns in einem Kommentar.

### <a name="great-looking-cards-from-data"></a>Hervorragende aussehende Karten aus Daten

Wir wissen viele Karte-Autoren, die bereits über gut definierte Daten hinter ihren Karten verfügen. Ist unsere Absicht, die eine Vorlagenmodell zu durchsuchen, die ermöglichen Karten generiert werden (serverseitige oder clientseitige) anhand der Daten und ein Repository mit klar definierten und anpassbare Vorlagen.

### <a name="make-cards-responsive"></a>Stellen Sie Karten reagiert

Kartenlayouts sollte auf den verfügbaren Platz reagieren. Mit Adaptive Cards sind anwendbar, die auf verschiedenen Geräten, Ux-Stile und und Benutzeroberflächen-Frameworks, aber sie sind reaktiv noch nicht. Für Elemente die Producer Karte, um die erforderlichen Hinweise an, der Rendering-Bibliotheken bieten, sodass sie auf intelligente Weise das Layout auf eine Weise ändern können, die und die Absicht der Karte verwaltet zu ermöglichen, müssen zusätzliche Eigenschaften definiert werden.

### <a name="responsive-exploration"></a>Reaktionsfähige durchsuchen

* Hinzufügen einer **Wichtigkeit** Eigenschaft, die Wichtigkeit des Inhalts kommentiert. Weniger wichtig, dass der Inhalt gelöscht werden kann, um den verfügbaren Platz angepasst
* Hinzufügen **Einschränkungen** und **Richtlinie** Eigenschaften, die beschreibt, wie reagieren, wenn Einschränkungen nicht erfüllt werden können. 
  * Ausblenden von Inhalt, oder Inhalte auf kleinere Größe zu reduzieren.
  * Fügen Sie einen Schwellenwert, wenn überschritten, ändert sich `columnSet` , Karussell von Spalten.

### <a name="new-element-types"></a>Neue Elementtypen

* Maps? -eine Zuordnung in eine Karte mit Interaktivität oder Fallback auf die Bitmap einbetten
* *Welche Elemente Sie möchten oder müssen*?

### <a name="new-rendering-libraries"></a>Neue Rendering-Bibliotheken

* Reagieren?
* Xamarin?
* *Welche Frameworks sollen?*
