---
title: 'Adaptive Karten: Übersicht'
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 8d9e30d4e188a1f0a9d10a9a4821f78b9b3b2f57
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134209"
---
# <a name="adaptive-cards-overview"></a>Adaptive Karten: Übersicht 

Adaptive Karten sind ein offenes Kartenaustauschformat, mit dem Entwickler UI-Inhalte auf einheitliche und konsistente Weise austauschen können.

<video controls width="100%" poster="./content/videoposter.png">
    <source src="https://adaptivecardsblob.blob.core.windows.net/assets/AdaptiveCardsOverviewVideo.mp4" type="video/mp4">
</video>

## <a name="how-they-work"></a>Funktionsweise

[**Kartenautoren**](authoring-cards/getting-started.md) beschreiben ihre Inhalte als ein einfaches JSON-Objekt. Dieser Inhalt kann dann systemintern in einer [**Hostanwendung**](rendering-cards/getting-started.md) gerendert werden und passt sich automatisch an das Erscheinungsbild des Hosts an.

Contoso Bot kann beispielsweise eine adaptive Karte über Bot Framework erstellen, die bei der Übermittlung an Skype das Erscheinungsbild einer Skype-Karte annimmt. Wenn die gleiche Nutzlast an Microsoft Teams gesendet wird, nimmt die das Erscheinungsbild von Microsoft Teams an. Da immer mehr Host-Apps beginnen, Adaptive Karten zu unterstützen, wird dieselbe Nutzlast automatisch in diesen Anwendungen bereitgestellt, wobei die Darstellung wie speziell für die jeweilige App konzipiert erscheint.

Benutzer haben den Vorteil, dass sich alles vertraut anfühlt. Hosts haben den Vorteil, die Benutzerfreundlichkeit steuern zu können. Und Kartenautoren haben den Vorteil, dass ihre Inhalte ohne zusätzlichen Aufwand eine größere Reichweite erhalten.

## <a name="goals"></a>Ziele 

Ziele für adaptive Karten:

* **Portierbar** zu jeder App, jedem Gerät und jedem Benutzeroberflächenframework
* **Offen**: Bibliotheken und das Schema sind Open Source und freigegeben.
* **Niedrige Kosten**: Einfach zu definieren und einfach zu nutzen
* **Ausdrucksstark**: Ausgerichtet auf die lange Reihe von Inhalten, die Entwickler erstellen möchten
* **Rein deklarativ**: Code ist nicht erforderlich oder zulässig.
* **Automatisch formatiert**: angepasst an die Benutzeroberfläche der Hostanwendung und Markenrichtlinien

## <a name="for-card-authors"></a>Für Kartenautoren
Adaptive Karten eignen sich hervorragend für Kartenautoren:

* **Ein Schema**: Sie arbeiten mit nur einem Format, sodass die Kosten für das Erstellen einer Karte minimiert und die Anzahl der Verwendungsmöglichkeiten maximiert werden.
* **Umfangreicherer Ausdruck**:Ihr Inhalt kann besser daran ausgerichtet werden, was Sie sagen möchten, da Sie über eine reichhaltigere Palette an Nuancen verfügen.
* **Große Reichweite**: Ihre Inhalte funktionieren für eine breitere Gruppe von Anwendungen, ohne dass Sie neue Schemata erlernen müssen.
* **Eingabesteuerelemente**: Ihre Karte kann Eingabesteuerelemente zum Erfassen von Informationen zum Benutzer beinhalten, der die Karte anzeigt.
* **Bessere Tools**: Ein offenes Karten-Ökosystem bedeutet bessere Tools, die von allen gemeinsam verwendet werden.

## <a name="for-experience-owners"></a>Für Besitzer von Benutzerumgebungen
Wenn Sie ein App-Entwickler sind, der ein Ökosystem mit Inhalten von Drittanbietern nutzen möchte, werden Sie Adaptive Karten lieben:

* **Einheitliche Benutzerumgebung**: Sie garantieren eine einheitliche Umgebung für Ihre Benutzer, da Sie die Formatvorlagen der gerenderten Karte besitzen.
* **Native Leistung**: Sie profitieren von nativer Leistung, da sie direkt auf Ihr Benutzeroberflächenframework ausgerichtet ist.
* **Sicher**: Inhalte werden über sichere Nutzlasten bereitgestellt, sodass Sie Ihr Benutzeroberflächenframework nicht für Rohmarkup und -skripting öffnen müssen.
* **Einfache Implementierung**: Sie erhalten vordefinierte Bibliotheken, die mühelos auf jeder von Ihnen unterstützten Plattform integriert werden können. 
* **Kostenlose Dokumentation:** Sie sparen Zeit, weil Sie kein proprietäres Schema entwerfen, implementieren und dokumentieren müssen.
* **Freigegebene Tools**: Sie sparen Zeit, da Sie keine benutzerdefinierten Tools erstellen müssen.

## <a name="core-design-principles"></a>Wichtigste Designprinzipien 

Adaptive Karten werden durch eine Reihe von [Leitprinzipien](resources/principles.md) gesteuert, die sich für die Einhaltung des Designs als nützlich erwiesen haben. 

### <a name="semantic-instead-of-pixel-perfect"></a>Semantik statt Pixelpräzision
Wir haben uns beim Layout so stark wie möglich um semantische Werte und Konzepte im Gegensatz zu reiner Pixelperfektion bemüht. Beispiele für semantische Ausdrücke finden sich in Farben, Größen und Elementen wie „FactSet“ und „ImageSet“. Diese ermöglichen es der Host-Anwendung, bessere Entscheidungen über das tatsächliche Erscheinungsbild zu treffen.

### <a name="card-authors-own-the-content-host-app-owns-the-look-and-feel"></a>Kartenautoren besitzen den Inhalt, die Host-App das Erscheinungsbild.
Die Kartenautoren besitzen ihre beabsichtigte Aussage, die anzeigende Anwendung besitzt jedoch Erscheinungsbild der Karte im Kontext ihrer Anwendung.

### <a name="keep-it-simple-but-expressive"></a>Halten Sie es einfach, aber ausdrucksstark.
Wir möchten, dass Adaptive Karten ausdrucksstark und universell einsetzbar sind, möchten aber kein Benutzeroberflächenframework erstellen.  Das Ziel ist die Erstellung einer Zwischenebene, die „aussagekräftig genug“ ist, so wie Markdown aussagekräftig genug für Dokumente ist.

Durch den Schwerpunkt auf Einfachheit und Aussagekraft hat Markdown eine einfache und konsistente Beschreibung von Dokumentinhalt erstellt.  Wir sind der Meinung, dass Adaptive Karten auf die gleiche Weise ein einfaches, ausdrucksstarkes Mittel zur Beschreibung von Karteninhalten darstellen können.

### <a name="when-in-doubt-keep-it-out"></a>Im Zweifelsfall weglassen
Es ist einfacher, etwas nachträglich hinzuzufügen, als mit einem Fehler zu leben. Wenn wir darüber diskutiert haben, ob wir etwas hinzufügen sollten oder nicht, haben wir uns entschieden, es wegzulassen.  Es ist immer einfacher, eine Eigenschaft hinzuzufügen, als mit einer Vorgängerversion zu leben, von der wir uns wünschen, dass wir sie nicht unterstützen müssten.


## <a name="build-2018-session"></a>Build 2018-Sitzung

Die folgende Sitzung auf der Build 2018 stellt Adaptive Karten in Bots, Cortana, Outlook und Windows vor. 

<iframe src="https://medius.studios.ms/Embed/Video/BRK2401?SFYT=true" width="960" height="540" allowFullScreen frameBorder="0"></iframe>
