---
title: Implementieren eines Renderers
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: 607ce40e70e0e54e61a572853a521d2dd70a5c23
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "77454913"
---
# <a name="adaptive-card-renderer-specification"></a>Spezifikation eines Renderers für adaptive Karten

Die folgende Spezifikation beschreibt die Implementierung eines Renderers für adaptive Karten auf einer beliebigen Benutzeroberflächenplattform.

> [!IMPORTANT]
> 
> Dieser Inhalt ist noch nicht final. Schau später wieder rein.

## <a name="sdk-versioning"></a>SDK-Versionsverwaltung

1. Haupt- und Nebenversion des SDKs **SOLLTEN** der `schema`-Version entsprechen. 
1. Patch und Build **SOLLTEN** für Rendererupdates angegeben werden, die keine Schemaänderungen umfassen.

## <a name="parsing-json"></a>Analysieren von JSON

### <a name="error-conditions"></a>Fehlerbedingungen
1. Ein Parser **MUSS** prüfen, ob es sich um gültigen JSON-Inhalt handelt.
1. Ein Parser **MUSS** eine Überprüfung anhand des Schemas (erforderliche Eigenschaften usw.) ausführen.
1. Die oben genannten Fehler **MÜSSEN** der Host-App gemeldet werden (als Ausnahme oder eine entsprechende Angabe).

### <a name="unknown-types"></a>Unbekannte Typen
1. Wenn unbekannte „Typen“ ermittelt werden, **MÜSSEN DIESE AUS DEM ERGEBNIS GELÖSCHT** werden.
1. Alle Änderungen der Nutzlast (wie oben) **SOLLTEN** der Host-App als Warnungen gemeldet werden.

### <a name="unknown-properties"></a>Unbekannte Eigenschaften
1. Ein Parser **MUSS** **zusätzliche** Eigenschaften in Elementen einschließen.

### <a name="additional-considerations"></a>Weitere Überlegungen
1. Die Eigenschaft `speak` kann SSML-Markup enthalten und **MUSS** wie angegeben an die Host-App zurückgegeben werden.

## <a name="parsing-host-config"></a>Analyse der Hostkonfiguration
1. TODO

## <a name="versioning"></a>Versionsverwaltung

1. Ein Renderer **MUSS** eine bestimmte Version des Schemas implementieren. 
1. Der `AdaptiveCard`-Konstruktor **MUSS** der Eigenschaft `version` einen Standardwert basierend auf der aktuellen Schemaversion zuweisen. 
1. Wenn ein Renderer eine `version`-Eigenschaft in einer `AdaptiveCard` findet, die höher ist als die unterstützte Version, **MUSS** er stattdessen den `fallbackText` zurückgeben.

## <a name="rendering"></a>Rendering

Eine `AdaptiveCard` besteht aus einem `body`- und einem `actions`-Element. Der `body` ist eine Sammlung von `CardElement`-Elementen, die von einem Renderer enumeriert und in der entsprechenden Reihenfolge gerendert werden. 

1. Jedes Element **MUSS** auf die Breite des übergeordneten Elements gestreckt werden (ähnlich wie bei `display: block` in HTML).
1. Ein Renderer **MUSS** unbekannte Elementtypen ignorieren und mit dem Rest der Nutzlast fortfahren.

### <a name="spacing-and-separators"></a>Abstände und Trennzeichen

1. Die `spacing`-Eigenschaft jedes Elements wirkt sich darauf aus, wie viel Abstand zwischen dem **AKTUELLEN** Element und dem Element **DAVOR** vorhanden ist.
1. Ein Abstand **DARF NUR DANN** angewendet werden, wenn vor dem Element tatsächlich ein anderes Element vorhanden ist. (Diese Eigenschaft gilt also nicht für das erste Element in einem Array).
1. Ein Renderer **MUSS** den zu verwendenden Abstand aus `hostConfig` für den Enumerationswert ablesen, der auf das aktuelle Element angewendet wird.
1. Wenn das Element den `separator`-Wert `true` aufweist, **MUSS** eine sichtbare Linie zwischen dem aktuellen Element und dem Element davor gezeichnet werden.
1. Die Trennlinie **MUSS** mithilfe der Eigenschaft `container.style.default.foregroundColor` gezeichnet werden.
1. Eine Trennlinie **DARF NUR** gezeichnet werden, wenn das Element **NICHT** das erste Element im Array ist.

### <a name="columns"></a>Spalten

1. `Column` `width` **MUSS** als „auto“, „stretch“ oder als gewichtetes Verhältnis interpretiert werden.

### <a name="textblock"></a>TextBlock

1. Ein TextBlock **MUSS** eine einzelne Zeile aufnehmen, sofern die `wrap`-Eigenschaft nicht `true` lautet. 
1. Der Textblock **SOLLTE** überschüssigen Text abschneiden und Auslassungspunkte (...) anzeigen.

#### <a name="markdown"></a>Markdown

1. Adaptive Karten lassen eine Teilmenge von Markdown zu und **SOLLTEN** in `TextBlock` unterstützt werden. 
1. Weitere Informationen findest du unter [Markdownanforderungen](../authoring-cards/text-features.md).

#### <a name="formatting-functions"></a>Formatierungsfunktionen

1. `TextBlock` ermöglicht [Formatierungsfunktionen für DATUM und UHRZEIT](../authoring-cards/text-features.md), die in jedem Renderer unterstützt werden **MÜSSEN**.
1. **BEI ALLEN FEHLERN MUSS** die unformatierte Zeichenfolge auf der Karte angezeigt werden. Es wird keine benutzerfreundliche Meldung angezeigt. (Ziel hierbei ist es, den Entwickler sofort darauf aufmerksam zu machen, dass ein Problem vorliegt).

1. TODO: Einschließen von regulären Ausdrücken

### <a name="images"></a>Abbilder

1. Ein Renderer **SOLLTE** Host-Apps informieren, wenn alle HTTP-Bilder heruntergeladen wurden und die Karte „vollständig gerendert“ ist.
1. Ein Renderer **MUSS** beim Herunterladen von HTTP-Bildern den Hostkonfigurationsparameter `maxImageSize` überprüfen.
1. Ein Renderer **MUSS**`.png` und `.jpeg` unterstützen.
1. Ein Renderer **SOLLTE**`.gif`-Bilder unterstützen.

### <a name="host-config"></a>Hostkonfiguration

* TODO: Wie sollten die Standardwerte lauten? Sollten diese überall freigegeben werden? Sollten wir eine gemeinsame hostConfig.json-Datei in den Binärdateien einbetten?
* TODO: Ich denke, HostConfig sollte auch für die Analyse versioniert werden?

[`HostConfig`](host-config.md) ist ein gemeinsam genutztes Konfigurationsobjekt, das angibt, wie ein Renderer für adaptive Karten eine Benutzeroberfläche generiert.  

So können plattformunabhängige Eigenschaften für Renderer auf verschiedenen Plattformen und Geräten freigegeben werden. Zudem können Tools erstellt werden, die dir eine Vorstellung vom Aussehen und Verhalten einer Karte in einer bestimmten Umgebung vermitteln.

1. Renderer **MÜSSEN** einen **HostConfig**-Parameter für Host-Apps verfügbar machen.
1. Alle Elemente **MÜSSEN** entsprechend ihren jeweiligen HostConfig-Einstellungen formatiert werden.

### <a name="native-platform-styling"></a>Native Plattformformatierung

1. Jeder Elementtyp **SOLLTE** eine native Plattformformatierung mit dem generierten Benutzeroberflächenelement anfügen. In HTML haben wir beispielsweise eine CSS-Klasse zu den Elementtypen hinzugefügt, und in XAML weisen wir einen bestimmten Stil zu.

## <a name="extensibility"></a>Erweiterbarkeit 

1. Ein Renderer **MUSS** es Host-Apps ermöglichen, standardmäßige Elementrenderer zu überschreiben. Beispiel: Ersetzen des Renderns von `TextBlock` durch eigene Logik.
1. Ein Renderer **MUSS** es Host-Apps ermöglichen, benutzerdefinierte Elementtypen zu registrieren. Beispiel: Hinzufügen von Unterstützung für ein benutzerdefiniertes `Rating`-Element.
1. Ein Renderer **MUSS** es Host-Apps ermöglichen, Unterstützung für ein Standardelement zu entfernen. Beispiel: Entfernen von `Action.Submit`, wenn die Unterstützung nicht gewünscht ist.

## <a name="actions"></a>Aktionen

1. Ein Renderer **DARF KEINE** Aktionen rendern, wenn das `supportsInteractivity`-Element in der HostConfig `false` ist.
1. Die `actions`-Eigenschaft **MUSS** als Schaltflächen auf einer Form von Aktionsleiste gerendert werden, üblicherweise am unteren Rand der Karte. 
1. Wenn eine Schaltfläche aktiviert wird, **MUSS** die Host-App das Ereignis verarbeiten können. 
1. Das Ereignis **MUSS** alle zugeordneten Eigenschaften mit der Aktion übergeben.
1. Das Ereignis **MUSS** die ausgeführte `AdaptiveCard` übergeben.

Action | Verhalten
--- | ---
**Action.OpenUrl** | Öffnet eine externe URL zur Anzeige.
**Action.ShowCard** | Fordert eine untergeordnete Karte an, die dem Benutzer angezeigt werden soll.
**Action.Submit** | Fordert an, dass alle Eingabeelemente in einem Objekt zusammengefasst werden, das dir anschließend über eine von der Hostanwendung definierte Methode gesendet wird.

### <a name="actionopenurl"></a>Action.OpenUrl
1. `Action.OpenUrl` **SOLLTE** eine URL mithilfe des nativen Plattformmechanismus öffnen.
1. Wenn dies nicht möglich ist, **MUSS** die Aktion ein Ereignis auslösen, damit die Host-App das Öffnen der URL verarbeitet. Dieses Ereignis **MUSS** es der Host-App ermöglichen, das Standardverhalten zu überschreiben, beispielsweise durch Öffnen der URL innerhalb der eigenen App.

### <a name="actionshowcard"></a>Action.ShowCard

1. `Action.ShowCard` **MUSS** auf irgendeine Weise unterstützt werden, basierend auf der HostConfig-Einstellung. Es gibt zwei Modi: Inline und Popup. Inlinekarten **SOLLTEN** die Sichtbarkeit der Karte automatisch umschalten. Im Popupmodus **SOLLTE** ein Ereignis ausgelöst werden, damit die Host-App die Karte auf irgendeine Weise anzeigt.

### <a name="actionsubmit"></a>Action.Submit

Die Submit-Aktion verhält sich wie eine Übermittlungsaktion in einem HTML-Formular, mit einer Ausnahme: In HTML wird typischerweise eine HTTP-POST-Aktion ausgelöst, bei adaptiven Karten dagegen bleibt der Host-App die Entscheidung überlassen, wie „submit“ zu interpretieren ist. 

1. Wenn ein Ereignis ausgelöst werden **MUSS**, tippt der Benutzer auf die aufgerufene Aktion.  
1. Die `data`-Eigenschaft **MUSS** in der Rückrufnutzlast enthalten sein.
1. Bei `Action.Submit`**MUSS** ein Renderer alle Eingaben auf der Karte erfassen und die zugehörigen Werte abrufen. 

### <a name="selectaction"></a>selectAction

1. Eine `selectAction` **DARF NICHT** als Berührungsziel gerendert werden, wenn das `supportedInteractivity`-Element der Hostkonfiguration `false` ist.
1. `Image`, `ColumnSet` und `Column` bieten eine `selectAction`-Eigenschaft, die ausgeführt werden **SOLLTE**, wenn sie von einem Benutzer z. B. durch Tippen auf das Element aufgerufen wird.

## <a name="inputs"></a>Eingaben

1. Ein Renderer **DARF KEINE** Eingaben rendern, wenn das `supportsInteractivity`-Element der HostConfig `false` ist.
2. Eingaben **SOLLTEN** mit der höchstmöglichen Genauigkeit gerendert werden. Ein `Input.Date`-Element beispielsweise sollte dem Benutzer idealerweise eine Datumsauswahl bieten. Wenn dies jedoch in deinem UI-Stapel nicht möglich ist, **MUSS** der Renderer ein Standardtextfeld rendern.
3. Ein Renderer **SOLLTE** nach Möglichkeit `placeholderText` anzeigen.
4. Ein Renderer **MUSS KEINE** Überprüfung der Eingabe implementieren. Benutzer von adaptiven Karten müssen die Überprüfung empfangener Daten auf ihrer Seite selbst planen.
5. Die Bindung von Eingabewerten **MUSS** ordnungsgemäß mit Escapezeichen versehen werden.

6. Das Objekt **MUSS** folgendermaßen an die Host-App zurückgegeben werden:

   Wir können keinerlei Zusagen hinsichtlich der Eingabeüberprüfung in adaptiven Karten machen, daher obliegt es dem Empfänger, Antworten ordnungsgemäß zu analysieren. „Input.Number“ könnte beispielsweise „Hallo“ zurückgeben, und die Empfänger müssen darauf vorbereitet sein.


## <a name="events"></a>Ereignisse

1. Ein Renderer **SOLLTE** ein Ereignis auslösen, wenn sich die Sichtbarkeit eines Elements geändert hat, sodass die Host-App die Karte an die richtige Position verschieben kann.
