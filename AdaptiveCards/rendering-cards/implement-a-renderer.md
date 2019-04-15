---
title: Implementieren eines Renderers
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: 3c79d768d5c979626b66614a1856ad6c2e390805
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552552"
---
# <a name="adaptive-card-renderer-specification"></a>Adaptive Card Renderer-Spezifikation

Die folgende Spezifikation wird beschrieben, wie eine Adaptive Card-Renderer auf alle UI-Plattform implementieren.

> [!IMPORTANT]
> 
> Dieser Inhalt ist noch nicht abgeschlossen. Später wieder.

## <a name="sdk-versioning"></a>SDK-Versionskontrolle

1. Die SDK-Version für Haupt- und Nebenversionsnummern **sollte** entsprechen den `schema` Version. 
1. Patch/Build **sollte** für Renderer müssen Updates, die schemaänderungen nicht verwendet werden.

## <a name="parsing-json"></a>JSON-Analyse

### <a name="error-conditions"></a>Fehlerbedingungen
1. Ein Parser **müssen** überprüfen Sie, dass es sich um gültigen JSON-Inhalt ist
1. Ein Parser **müssen** überprüfen mithilfe des Schemas (erforderlichen Eigenschaften usw.)
1. Die oben genannten Fehler **müssen** gemeldet werden, für die Host-app (Ausnahme oder Äquivalent)

### <a name="unknown-types"></a>Unbekannte Typen
1. Wenn unbekannte "Typen" auftreten, werden sie **müssen gelöscht werden,** aus dem Ergebnis
1. Alle Änderungen der Nutzlast (wie weiter oben) **sollte** als Warnungen an, die Host-app gemeldet werden

### <a name="unknown-properties"></a>Eigenschaften von Unbekannter
1. Ein Parser **müssen** enthalten **zusätzliche** Eigenschaften für Elemente

### <a name="additional-considerations"></a>Weitere Aspekte
1. Die `speak` -Eigenschaft kann die SSML-Code enthalten und **müssen** zurückgegeben werden, für die Host-app, die als angegeben

## <a name="parsing-host-config"></a>Analysieren der Host-Konfiguration
1. TODO

## <a name="versioning"></a>Versionskontrolle

1. Ein Renderer **müssen** implementieren Sie eine bestimmte Version des Schemas. 
1. Die `AdaptiveCard` Konstruktor **müssen** geben die `version` Eigenschaft ein Standardwert auf der aktuellen Schemaversion basierend 
1. Wenn ein Renderer auftritt ein `version` -Eigenschaft in der `AdaptiveCard` ist höher als die unterstützte Version, es **müssen** Zurückgeben der `fallbackText` stattdessen.

## <a name="rendering"></a>Rendering

Ein `AdaptiveCard` besteht aus einem `body` und `actions`. Die `body` ist eine Sammlung von `CardElement`s, die ein Renderer aufgelistet und in der Reihenfolge gerendert. 

1. Jedes Element **müssen** Stretch der Breite seines übergeordneten Elements (denken `display: block` im HTML-Format).
1. Ein Renderer **müssen** unbekannte Elementtypen ignorieren und fortfahren, Rendern den Rest der Nutzlast.

### <a name="spacing-and-separators"></a>Abstand und Trennzeichen

1. Die `spacing` Eigenschaft für jedes Element wirkt sich auf den Abstand zwischen den **aktuelle** -Element und der **vor** es.
1. Der Abstand **muss nur** angewendet, wenn tatsächlich ein Element mit dem vorhergehenden. (Z. B. nicht auf das erste Element in einem Array anwenden)
1. Ein Renderer **müssen** suchen Sie die Menge des Speicherplatzes für die Verwendung von der `hostConfig` Abstand für den Enum-Wert, der auf das aktuelle Element angewendet.
1. Wenn das Element verfügt ein `separator` Wert `true`, klicken Sie dann eine sichtbare Zeile **müssen** zwischen dem aktuellen Element und vor es gezeichnet werden.
1. Trennlinie **müssen** werden gezeichnet wird, mit der `container.style.default.foregroundColor`.
1. Ein Trennzeichen **muss nur** gezeichnet werden, wenn das Element **IS NOT** die zuerst im Array.

### <a name="columns"></a>Spalten

1. `Column` `width` **MUSS** von "Auto", "stretch" oder ein Verhältnis von gewichteten interpretiert werden.

### <a name="textblock"></a>TextBlock

1. Ein TextBlock-Element **müssen** dauern, bis eine einzelne Zeile, wenn die `wrap` Eigenschaft `true`. 
1. Der TextBlock **sollte** überschüssige Text mit einem Auslassungszeichen (...) kürzen

#### <a name="markdown"></a>Markdown

1. Mit Adaptive Cards können für eine Teilmenge von Markdown und **sollte** in unterstützt `TextBlock`. 
1. Siehe vollständige [Markdown-Anforderungen](../authoring-cards/text-features.md)

#### <a name="formatting-functions"></a>Formatierungsoptionen

1. `TextBlock` ermöglicht das [DATUMS-und UHRZEITFORMATIERUNG Funktionen](../authoring-cards/text-features.md) , **müssen** auf jeder Renderer unterstützt werden.
1. **ALLE Fehler müssen** die unformatierte Zeichenfolge in der Karte angezeigt. Keine Meldung versucht. (Das Ziel, die mit den Entwickler es sofort aufmerksam zu machen ist ein Problem aufgetreten.)

1. TODO: Einschließen von regex

### <a name="images"></a>Abbilder

1. Ein Renderer **sollte** zulassen apps hosten, wissen Sie, wenn alle HTTP-Images heruntergeladen wurden und dass die Karte "vollständig Rendererd"
1. Ein Renderer **müssen** überprüfen Sie die Hosts Config `maxImageSize` Param beim Herunterladen von HTTP-Images
1. Ein Renderer **müssen** unterstützen `.png` und `.jpeg`
1. Ein Renderer **sollte** unterstützen `.gif` Images

### <a name="host-config"></a>Host-Konfiguration

* TODO: Was sollten folgende Standardwerte verwendet werden? Sollten sie sie freigeben? Sollten wir eine gemeinsame hostConfig.json-Datei in den Binärdateien einbetten?
* TODO: Ich denke, dass HostConfig sowie für die Analyse mit Versionsangaben versehen werden muss?

[`HostConfig`](host-config.md) ist eine Konfiguration für shared-Objekt, das angibt, wie eine Adaptive Card Renderer UI generiert.  

Dadurch können die Eigenschaften, die plattformunabhängig von Renderern, die auf verschiedenen Plattformen und Geräten gemeinsam verwendet werden. Darüber hinaus können Tools erstellt werden, wodurch Sie sich ein Überblick über das Aussehen und Verhalten, die Karte müssten für eine bestimmte Umgebung.

1. Renderer **müssen** verfügbar zu machen eine **Hosts Config** Parameter zum Hosten von apps
1. Alle Elemente **müssen** formatiert werden, entsprechend ihrer jeweiligen Einstellungen für die Host-Konfiguration

### <a name="native-platform-styling"></a>Systemeigene Plattform erstellen

1. Der Typ jedes Elements **sollte** fügen Sie einen native Plattform-Stil mit dem generierten UI-Element. Z. B. in HTML wir eine CSS-Klasse hinzugefügt, um den Elementtypen, und in XAML, die wir weisen eines bestimmten Format.

## <a name="extensibility"></a>Erweiterungen 

1. Ein Renderer **müssen** Host Apps Zugriff auf Standard-Element-Renderer zu überschreiben. Ersetzen Sie z. B. `TextBlock` rendering mit ihrer eigenen Logik.
1. Ein Renderer **müssen** Host Apps Zugriff auf benutzerdefinierte Elementtypen zu registrieren. Z. B. Hinzufügen von Unterstützung für eine benutzerdefinierte `Rating` Element
1. Ein Renderer **müssen** ermöglichen apps hosten, um Unterstützung für eine Default-Element zu entfernen. Entfernen Sie z. B. `Action.Submit` bei Bedarf unterstützt nicht.

## <a name="actions"></a>Aktionen

1. Wenn HostConfig `supportsInteractivity` ist `false`, einen Renderer **darf keinen** Maßnahmen, die zu rendern.
1. Die `actions` Eigenschaft **müssen** als Schaltflächen in einer Art Aktionsleiste in der Regel am unteren Rand der Karte gerendert werden. 
1. Wenn eine Schaltfläche getippt wird es **müssen** ermöglichen die Host-app zum Behandeln des Ereignisses. 
1. Das Ereignis **müssen** Bahn entlang allen zugehörigen Eigenschaften mit der Aktion
1. Das Ereignis **müssen** übergibt die `AdaptiveCard` die ausgeführt wurde

Aktion | Verhalten
--- | ---
**Action.OpenUrl** | Öffnen Sie eine externe URL für die Anzeige
**Action.ShowCard** | Fordert eine untergeordnete Karte, die dem Benutzer angezeigt werden.
**Action.Submit** | Stellen Sie für alle Elemente mit der Eingabe in ein Objekt gesammelt werden, um die über eine Methode, die von der hostanwendung definiert dann an Sie gesendet wird.

### <a name="actionopenurl"></a>Action.OpenUrl
1. `Action.OpenUrl` **SOLLTE** öffnen Sie eine URL mit der nativen Plattform-Mechanismus
1. Wenn dies nicht möglich ist es **müssen** Auslösen eines Ereignisses für die Host-app, behandeln Sie die URL öffnen. Dieses Ereignis **müssen** Host-app das Standardverhalten außer Kraft setzen können. Beispielsweise können sie die URL in ihre eigene app zu öffnen.

### <a name="actionshowcard"></a>Action.ShowCard

1. `Action.ShowCard` **MUSS** in irgendeiner Form, die entsprechend der HostConfig unterstützt werden. Es gibt zwei Modi: Inline, und den popupausrichtungspunkt. Inline-Karten **sollte** ein-oder ausblenden, Karte automatisch. Im Modus "Popup" ein Ereignis **sollte** ausgelöst werden, für die Host-app auf die Karte auf irgendeine Weise anzeigen.

### <a name="actionsubmit"></a>Action.Submit

Die Aktion senden verhält sich wie ein HTML-Formular übermitteln, mit dem Unterschied, dass, in dem HTML in der Regel HTTP Post auf, mit Adaptive Cards löst sie bis zu verlassen jeder Host-app, um zu bestimmen, was "Absenden" bedeutet, dass sie. 

1. Wenn dies **müssen** lösen ein Ereignis der Benutzer tippt der Invokved Aktion.  
1. Die `data` Eigenschaft **müssen** in die Rückruf-Nutzlast enthalten sein.
1. Für `Action.Submit`, einen Renderer **müssen** sammeln Sie alle Eingaben auf der Karte und deren Werte abrufen. 

### <a name="selectaction"></a>selectAction

1. Wenn Hosts Config `supportedInteractivity` ist `false` ein `selectAction` **darf nicht** als Touch-Ziel gerendert.
1. `Image`, `ColumnSet`, und `Column` bieten eine `selectAction` -Eigenschaft, die **sollte** ausgeführt werden, wenn der Benutzer, z. B. ruft durch Tippen auf das Element.

## <a name="inputs"></a>Eingaben

1. Wenn HostConfig `supportsInteractivity` ist `false` einen Renderer **darf keinen** Eingaben zu rendern.
2. Eingaben **sollte** Rendern mit der höchsten Genauigkeit möglich. Z. B. eine `Input.Date` würde im Idealfall eine Datumsauswahl für einem Benutzer, aber wenn ist dies nicht möglich für Ihre UI-Stack, und klicken Sie dann auf den Renderer bieten **müssen** ein Fallback auf das ein normales Textfeld zu rendern.
3. Ein Renderer **sollte** Anzeigen der `placeholderText` möglichst
4. Ein Renderer **nicht** Validierungen der Eingabe zu implementieren. Benutzer mit Adaptive Cards müssen planen, empfangene Daten auf ihrer Seite zu überprüfen.
5. Geben Sie die wertbindung **müssen** ordnungsgemäß mit Escapezeichen versehen werden

6. Das Objekt **müssen** an den Host-app wie folgt zurückgegeben:

   Wir machen Versprechen, die Überprüfung der Eingabe nicht in mit adaptive Cards, ist es also an die empfangende Partei, ordnungsgemäß Analysieren der Antwort. Z. B. eine Input.Number konnte "hello" zurück, und sie dafür vorbereitet werden müssen.


## <a name="events"></a>Ereignisse

1. Ein Renderer **sollte** ein Ereignis, wenn die Sichtbarkeit eines Elements geändert wurde, ermöglicht es der Host-app in die Position die Karte zu scrollen, ausgelöst.
