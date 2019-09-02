---
title: Beweggründe und Prinzipien
author: matthidinger
ms.author: mahiding
ms.date: 5/14/2018
ms.topic: article
ms.openlocfilehash: 78fe44463c4ddb832ba0cc72d456b6d21518bac4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553152"
---
# <a name="motivations-and-principles"></a>Beweggründe und Prinzipien

Im Folgenden findest du die Beweggründe und Prinzipien, die die Entwicklung der adaptiven Karten prägen.

## <a name="motivations-behind-the-format"></a>Beweggründe für das Format

Anfang 2016 wurde verschiedenen Teams bei Microsoft (u. a. den Teams für Outlook, Windows und das Bot Framework) bewusst, dass sie alle etwas sehr Ähnliches („Karten“) wünschten und dass jedes Team unabhängig von den anderen seine eigene Lösung entwarf:

- Windows verfügte über ein eigenes Format mit Livekacheln und Benachrichtigungen.
-  Das Bot Framework verwendete eine Reihe vordefinierter Kartenvorlagen, aus denen Entwickler beim Senden von Botnachrichten auswählen konnten.
- In Outlook kam ein eigenes MessageCard-Format für das Feature „Aktionen erfordernde Nachrichten“ zum Einsatz.

Gleichzeitig wurde auch für Plattformen wie LINE, Facebook Messenger, Slack und viele weitere ein jeweils eigenes, proprietäres „Kartenformat“ definiert. Also haben sich ein paar Microsoft-Mitarbeiter zusammengesetzt und damit begonnen, ein einzelnes, offenes Kartenformat sowie eine Reihe von SDKs zu definieren. Folgende Anforderungen sollten erfüllt werden:

- Der Austausch von Karten zwischen Hosts sollte erleichtert werden.
- Jeder Host sollte die Kontrolle über die Formatierung der Karten erhalten, um visuelle Konsistenz sicherzustellen.
- Mit einsatzbereiten SDKs sollte es Hostanwendungen erleichtert werden, Karten mit minimalem Aufwand anzuzeigen.
- So sollte auch ein Mehrwert für Drittanbieter entstehen, damit das Format letztendlich branchenweit übernommen würde.

## <a name="principles-governing-adaptive-cards"></a>Die Prinzipien hinter adaptiven Karten

1.  **Adaptive Karten sind ein _einfaches_ und _deklaratives_ Kartenformat.**

    1.  Sie sind nicht als Ersatz oder Alternative für HTML oder XAML gedacht.
    2.  Bei adaptiven Karten gibt es **kein CodeBehind**.
        1. Kartenersteller können keinen benutzerdefinierten oder beliebigen Code in ihre Nutzlasten einbetten, daher muss ein Host für adaptive Karten niemals Drittanbietercode ausführen.
        2. Dynamik und Interaktivität werden ausschließlich über deklaratives Markup erzielt.
    3.  So ist sichergestellt, dass der Aufwand für die Erstellung eines SDKs für adaptive Karten für eine neue Plattform in angemessenem Rahmen bleibt.

2.  **Das Format der adaptiven Karten kann nicht die Verwendung einer bestimmten zugrunde liegenden Technologie vorschreiben.**

    1.  Das Format der adaptiven Karten basiert nicht auf JavaScript, C#, Python oder einer anderen Sprache.
    2.  Es ist auch nicht von HTML, XAML oder einem anderen grafischen oder Benutzeroberflächenformat abhängig.
    3.  So können adaptive Karten nativ auf jeder Plattform gerendert, sofern ein Renderer vorhanden ist.

3.  **Das Format der adaptiven Karten ist eine _freigegebene Eigenschaft_.**

    1.  Das Format sowie die zugehörigen SDKs ist Open Source, und die Entwicklung erfolgt in der Community.
    2.  Daher ist das Format nicht im Besitz eines bestimmten Teams und wird von keinem Team gesteuert.

4.  **Adaptive Karten sind nicht „nur zur Verwendung durch Microsoft“ konzipiert.**

    1.  Stattdessen erfüllt es die Anforderungen einer Vielzahl von Anwendungen und Anwendungsfällen.

5.  **Die _Adaptive Card Working Group_ steuert die Weiterentwicklung des Formats.**

    1.  Diese Arbeitsgruppe besteht aus einer Reihe von Microsoft-Mitarbeitern, die maßgeblich zum Erfolg des Formats beitragen.
    2.  Die Arbeitsgruppe trifft sich einmal in der Woche (zurzeit montags). Während dieser Meetings werden Featurevorschläge geprüft, offene Probleme diskutiert und selektiert, und es wird der Gesamtfortschritt bei vNext-Arbeitselementen nachverfolgt.
    3.  Die Arbeitsgruppe nutzt das Feedback aus der gesamten Community, einschließlich interner Microsoft-Teams, um zu entscheiden, wie sich das Format weiterentwickelt.
        1. Jeder kann sich durch Eröffnen von Issues in GitHub an der Arbeitsgruppe beteiligen (siehe unten).
        2. Issues bzw. Featureanforderungen, die der tatsächlichen Nutzung des Formats entspringen (entweder als Host oder als Ersteller von Karten) haben den größten Einfluss auf die Zukunft des Formats.
    4.  Vorgeschlagene neue Features müssen folgende Anforderungen erfüllen, um von der Arbeitsgruppe berücksichtigt zu werden:
        1. Sie müssen durch reale Anwendungsfälle gerechtfertigt sein.
        2. Sie müssen eine funktionale Spezifikation aufweisen.
    5.  Genehmigte neue Features werden zum Backlog hinzugefügt und für vNext in Betracht gezogen.
        1. Neue Features werden anhand verschiedener Kriterien priorisiert. Hierzu gehören der Umfang der Szenarien, die durch dieses Feature ermöglicht werden, die Komplexität, die Verwaltungsfreundlichkeit und einige weitere.
        2. Wenn du nicht sicher bist, lass es sein! Es ist viel einfacher, ein gut konzipiertes Feature zu einem späteren Zeitpunkt einzuführen, als für immer mit einem Fehler zu leben.
    6.  Alle neuen Features werden in allen unterstützten SDKs implementiert.
    7.  Alle neuen Features werden dokumentiert und mit einer Testkarte verknüpft, die im Ordner mit Beispielen veröffentlicht wird.
    8.  Neue Versionen des Formats und der SDKs durchlaufen eine Betaphase.
    9.  Der Releasezeitplan für Schema- und SDK-Versionen einer adaptiven Karte basiert auf der Qualität, nicht auf einem bestimmten Datum.

6.  **Interoperabilität**
    1.  Karten, die anhand eines dokumentierten Formats erstellt werden (also nicht mithilfe von hostspezifischen Erweiterungen), werden auf jedem Host ordnungsgemäß gerendert, der adaptive Karten unterstützt.
    2.  Für diese Prinzipien gelten nur folgende Ausnahmen:
        1.  Einige Hosts erlauben möglicherweise keine Interaktivität und rendern daher weder Eingaben noch Aktionen.
        2.  Die Ausführung von Action.Submit-Aktionen erfolgt nur über den Host, und nicht alle Hosts verarbeiten notwendigerweise alle Action.Submit-Nutzlasten. Darüber hinaus unterstützen einige Hosts möglicherweise überhaupt keine Action.Submit-Aktionen.

7.  **Das Format muss erweiterbar sein.**

    1.  Hosts müssen die Möglichkeit haben, Unterstützung für benutzerdefinierte Elemente oder Aktionen hinzuzufügen, die die Funktionalität des Formats übersteigen.
    2.  Dies ist besonders wichtig bei Aktionen, da verschiedene Hosts nicht unbedingt den gleichen Satz Aktionen unterstützen.
    3.  Diese Hinzufügungen werden über den Host gesteuert.
        1. Sie sind keine *De-facto*-Hinzufügung zur Spezifikation von adaptiven Karten.
        2. Daher ist eine Nutzlast, die diese Karten verwendet, mit dem normalen Format der adaptiven Karten nicht kompatibel.
        3. Sie können jedoch der Arbeitsgruppe vorgestellt und als neue Features für eine zukünftige Version des Formats vorgeschlagen werden, wie in Punkt 5 beschrieben.

8.  **Kartenersteller besitzen den Inhalt, Host-App das Erscheinungsbild und Verhalten.**

    1.  Host-Apps erzwingen ihren Stil, daher sehen Karten so aus und verhalten sich so, als seien sie native Erweiterungen der App-Funktionalität.
    2.  Kartenersteller können den Stil zwar angeben, aber nur über semantische Ausdrücke wie Farben, Größen usw.

9.  **Für die beliebtesten Entwicklerplattformen werden SDKs bereitgestellt.**

    1.  SDKs vereinfachen das Rendern von Nutzlasten von adaptiven Karten auf jedem Host.
    2.  So wird sowohl für Entwickler von Drittanbietern als auch für Microsoft-Teams ein möglichst einfacher Einstieg sichergestellt.
