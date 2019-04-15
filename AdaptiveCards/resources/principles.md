---
title: Motivation und Prinzipien
author: matthidinger
ms.author: mahiding
ms.date: 5/14/2018
ms.topic: article
ms.openlocfilehash: 78fe44463c4ddb832ba0cc72d456b6d21518bac4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553152"
---
# <a name="motivations-and-principles"></a>Motivation und Prinzipien

Unten sind die Motivation und Prinzipien Govering die Weiterentwicklung von Adaptive Card Format.

## <a name="motivations-behind-the-format"></a>Motivation hinter das format

Anfang 2016 haben mehrere Teams bei Microsoft (einschließlich Outlook, Windows und der Bot-Framework) feststellen, dass sie alle wollten etwas sehr ähnliche ("Karten") und wurden jeweils ihre eigenen Lösungen unabhängig voneinander entwerfen:

- Windows weist ein eigenen Live-Kacheln und Benachrichtigungen-format
-  Das Bot Framework wurde eine Reihe von vordefinierten Karte Vorlagen verwenden, die Entwickler beim Senden von Nachrichten von Bot auswählen können
- Outlook wurde ein eigene MessageCard-Format für das Feature für Aktionen erfordernde Nachrichten verwenden.

Zur gleichen Zeit wurden andere Plattformen wie z. B. Linie, FaceBook Messenger, Slack und mehr eigenen proprietären "Karte"-Format definieren. Einige Microsoft-Mitarbeiter sich gesammelt und Schritte zu einem Kartenformat aus einer einzigen, öffnen und einen Satz von SDKs zu definieren, die:

- Den Austausch von Karten zwischen Hosts würde erleichtern.
- Jedem Host, um die Steuerung des Designs von Karten, um sicherzustellen, dass visuelle Konsistenz beibehalten können
- Würde eine hostanwendung zum Anzeigen von Karten mit minimalem Aufwand über bereit zu verwendenden SDKs erleichtern
- Wert würde auch an Drittanbieter bereitstellen und schließlich erhalten übernommen weit von der Branche

## <a name="principles-governing-adaptive-cards"></a>Grundregeln für mit Adaptive Cards

1.  **Adaptive Karte ist eine _einfache_ und _deklarative_ Kartenformat**

    1.  Es ist nicht als HTML- oder XAML ersetzen/Alternative vorgesehen.
    2.  Es gibt **keine "Code hinter"** mit Adaptive Cards
        1. Autoren von Karte können nicht benutzerdefinierte/beliebigen Code einbetten, mit deren Nutzlasten, und ein Adaptive Card-Host muss daher nie zum Ausführen von Code von Dritten
        2. Informationstechnologie und die Interaktivität werden ausschließlich über deklaratives Markup erreicht.
    3.  Dadurch wird sichergestellt, dass der Aufwand erforderlich, erstellen Sie eine Adaptive Card-SDK für eine neue Plattform angemessene bleibt

2.  **Die Adaptive Card-Format kann nicht die Verwendung der eine bestimmte zugrunde liegende Technologie erzwingen.**

    1.  Das Format für die Adaptive Card basiert nicht auf JavaScript C#, Python oder einer anderen Sprache
    2.  Auf ähnliche Weise abhängig nicht sie HTML oder XAML oder ein anderes Grafik/UI-framework
    3.  Auf diese Weise kann mit Adaptive Cards systemintern auf jeder Plattform für gerendert werden, solange ein Renderer vorhanden ist.

3.  **Das Adaptive Card-Format ist ein _freigegebene Eigenschaft_**

    1.  Zusammen mit der SDKs zur Verfügung ist das Format open Source- und seine Community; hier Evolution gesteuert werden.
    2.  Das Format ist daher nicht im Besitz oder durch ein ein-Team gesteuert

4.  **Das Format für die Adaptive Card dient nicht "nur für die Verwendung der von Microsoft"**

    1.  Stattdessen dient er dem entsprechend der Anforderungen einer Vielzahl von Anwendungen und Anwendungsfällen

5.  **Die _Adaptive Card Working Group_ steuert die Entwicklung des Formats**

    1.  Diese Arbeitsgruppe besteht aus einer Reihe von Microsoft-Mitarbeitern, die alle intensiv in den Erfolg des Formats
    2.  Die Arbeitsgruppe überprüft wöchentlichen Besprechungen (derzeit am Montag) während welches, die Feature Vorschläge überprüft, offenen Probleme sind erläutert und selektiert und Gesamtfortschritt für vNext-Arbeitselemente wird nachverfolgt.
    3.  Der Arbeitsgruppe verwendet aus dem Feedback von der Community insgesamt, einschließlich der internen Microsoft-Teams, um zu entscheiden, wie das Format entwickelt
        1. Jeder Benutzer kann in der Arbeitsgruppe durch Öffnen von Problemen auf GitHub (siehe unten) teilnehmen.
        2. Probleme und Feature-Anforderungen, die auf tatsächlichen Verbrauch von Framework mit Adaptive Cards (entweder als Host oder als der Autor einer Karte) haben die größten Auswirkungen auf die Zukunft des Formats
    4.  Von der Arbeitsgruppe, vorgeschlagene neue Features genehmigt werden:
        1. Muss durch reale Anwendungsfälle gerechtfertigt sein
        2. Eine Funktionsspezifikation benötigen
    5.  Genehmigtes neues Feature zum Backlog hinzugefügt und als für vNext
        1. Die Kriterien zum Priorisieren von neuen Features gehören die Bandbreite der Szenarien, die die Funktion ermöglicht, seine Komplexität/Verwaltbarkeit und vieles mehr
        2. Halten Sie im Zweifelsfall es heraus! Es ist viel einfacher, eine gut entworfene Funktion liegt, live mit einem Fehler immer einzuführen.
    6.  Alle neuen Features sind in allen unterstützten SDKs implementiert.
    7.  Alle neuen Features sind dokumentiert und eine Test-Karte, die im Ordner Samples veröffentlicht zugeordnet
    8.  Neue Versionen des Formats und der SDKs durchlaufen eine Betaphase
    9.  Den Zeitplan für die Adaptive Card-Schema und die SDK-Versionen die Version wird von der Qualität, die nicht Datum gesteuert.

6.  **Interoperabilität**
    1.  Karten in Übereinstimmung mit das dokumentierte Format (z. B. nicht mit jedem Host-spezifische Erweiterungen) erstellt werden in einem beliebigen Adaptive Card-fähigen Host ordnungsgemäß gerendert.
    2.  Die einzigen Ausnahmen von dieser Prinzipien sind:
        1.  Einige Hosts lassen möglicherweise keine Interaktivität und werden daher nicht gerendert, Eingaben und Aktionen
        2.  Ausführung von Aktionen für Action.Submit liegt im Ermessen des Hosts, und nicht alle Hosts alle Action.Submit Nutzlasten unbedingt ordnungsgemäß ausführt. Darüber hinaus können einige Hosts nicht Action.Submit überhaupt unterstützt

7.  **Das Format muss zu erweiterbar**

    1.  Hosts müssen die Freiheit, Hinzufügen von Unterstützung für benutzerdefinierte Elemente oder benutzerdefinierte Aktionen, die hinausgehen, was das Format kann
    2.  Dies ist besonders wichtig für Aktionen, wie verschiedene Hosts nicht unbedingt den gleichen Satz von Aktionen unterstützen
    3.  Diese Hinzufügungen sind nach dem Ermessen des Hosts
        1. Sind sie keine *facto* Ergänzung für die Adaptive Card-Spezifikation
        2. Daher stellen sie eine Nutzlast, die sie verwendet nicht kompatibel mit dem grundlegenden Adaptive Card-format
        3. Sie können jedoch werden der Gruppe "Arbeit" präsentiert und vorgeschlagenen als neue Features für eine zukünftige Version des Formats, wie in erster #5 beschrieben

8.  **Autoren von Karte besitzen, den Inhalt, Host-apps besitzen, das Aussehen und Verhalten**

    1.  Hosten von apps zu erzwingen, deren formatieren, sodass Karten gesucht werden und wie sie native Erweiterungen der app-Erfahrung sind
    2.  Smartcard-Autoren können weiterhin Formatierung, jedoch nur über die semantische Ausdrücke von Farben, Größen usw. angeben.

9.  **SDKs werden für die am häufigsten verwendeten Entwicklerplattformen angegeben werden**

    1.  SDKs vereinfachen das Adaptive Card-Nutzlasten in einem beliebigen Host zu rendern.
    2.  Dadurch wird sichergestellt, dass die Einstiegsschwelle so gering wie möglich für Entwickler von Drittanbietern und Microsoft Teams ist.
