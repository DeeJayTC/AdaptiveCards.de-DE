---
title: Roadmap für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 05/16/2018
ms.topic: article
ms.openlocfilehash: f879c164b3471347ba8fa058827b3d79b09be4cd
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138003"
---
# <a name="future-work"></a>Die Zukunft

Wir haben zwar bereits großartige Fortschritte beim Definieren von adaptiven Karten erzielt, aber es ist immer noch sehr viel zu tun. Wir hoffen, dass wir durch die Unterstützung aktiver Entwicklercommunitys wie Botness und toller Partner wie Slack und Kik ein herausragendes Ökosystem aus plattformübergreifenden Karten aufbauen können.

## <a name="roadmap"></a>Roadmap

[Hier](https://portal.productboard.com/adaptivecards/1-adaptive-cards-portal/tabs/1-backlog) findest du unsere aktuelle (nicht endgültige) Roadmap. Beachte bitte, dass sich alle Elemente dieser Roadmap ändern können und dass für kein Element garantiert werden kann, dass es tatsächlich ausgeliefert wird.

## <a name="future-ideas"></a>Ideen für die Zukunft

Im Folgenden findest du einige unserer Ideen für die Zukunft – alles noch in der Brainstormingphase. Wenn dich eine dieser Ideen interessiert, freuen wir uns über einen Kommentar.

### <a name="great-looking-cards-from-data"></a>Optimal entworfene Karten aus Daten

Wir wissen, dass viele Kartenersteller bereits über klar definierte Daten hinter ihren Karten verfügen. Wir möchten ein Vorlagenmodell erkunden, das es ermöglicht, Karten (server- oder clientseitig) basierend auf solchen Daten und einem Repository mit klar definierten und anpassbaren Vorlagen zu generieren.

### <a name="make-cards-responsive"></a>Reaktionsfähiges Layout für Karten

Das Kartenlayout sollte sich dem verfügbaren Platz anpassen können. Adaptive Karten können sich auf viele verschiedene Geräte, Benutzeroberflächen und UI-Frameworks anpassen, sind aber noch nicht reaktionsfähig. Es müssen zusätzliche Eigenschaften für Elemente definiert werden, die es Kartenerstellern ermöglichen, die notwendigen Hinweise an die Renderingbibliotheken zu übermitteln, sodass diese das Layout auf intelligente Weise anpassen können und die Absicht der Karte erhalten bleibt.

### <a name="responsive-exploration"></a>Reaktionsschnelle Erkundung

* Eine **importance**-Eigenschaft liefert Hinweise zur Wichtigkeit des Inhalts. Weniger wichtige Inhalte können verworfen werden, um den verfügbaren Platz für wichtige Inhalte zu nutzen.
* **constraints**- und **policy**-Eigenschaften beschreiben, was passieren soll, wenn Einschränkungen nicht erfüllt werden können. 
  * Inhalt kann ausgeblendet oder auf eine kleinere Größe reduziert werden.
  * Bei Überschreitung eines bestimmten Schwellenwerts kann `columnSet` in ein Spaltenkarussell geändert werden.

### <a name="new-element-types"></a>Neue Elementtypen

* Landkarten/Stadtpläne – Einbetten einer Landkarte oder eines Stadtplans mit interaktiven Funktionen oder Fallback auf eine Bitmap
* *Welche Elemente benötigst du oder hättest du gerne?*

### <a name="new-rendering-libraries"></a>Neue Renderingbibliotheken

* React?
* Xamarin?
* *Mit welchen Frameworks möchtest du arbeiten?*
