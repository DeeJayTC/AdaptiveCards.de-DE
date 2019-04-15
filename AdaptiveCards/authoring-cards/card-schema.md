---
title: Smartcard-Schema
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 76a21affcd26798acb52e2bcf1168121838ed00a
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553722"
---
# <a name="card-schema"></a>Smartcard-Schema

Karten
   * [`AdaptiveCard`](#schema-adaptivecard) -In eine Adaptive Card Root-Element.

Elemente mit Karte
   * [`TextBlock`](#schema-textblock) -Zeigt Text an, sodass Kontrolle über die Schriftgrade, Stärke und Farbe.
   * [`Image`](#schema-image) – Zeigt ein Bild.
   * [`Media`](#schema-media) – Zeigt einen MediaPlayer für Audio-und Videoinhalte.
   * [`MediaSource`](#schema-mediasource) : Definiert als Quelle für ein Medienelement

Container
   * [`Container`](#schema-container) – Container werden die Elemente zusammen gruppiert.
   * [`ColumnSet`](#schema-columnset) -Die ColumnSet teilt eine Region in Spalten, zulassen, dass Elemente auf der Seite-an-Seite befinden.
   * [`Column`](#schema-column) : Definiert einen Container, der Teil eines Spaltensatzes ist.
   * [`FactSet`](#schema-factset) – Die FactSet-Element zeigt eine Reihe von Fakten (d. h. Name/Wert-Paare) in einer Tabelle an.
   * [`Fact`](#schema-fact) – Beschreibt Fakten in einer FactSet als Schlüssel/Wert-Paar.
   * [`ImageSet`](#schema-imageset) – Die ImageSet zeigt eine Auflistung von Bildern, die ähnlich wie in einem Katalog an.

Aktionen
   * [`Action.OpenUrl`](#schema-action.openurl) – Wenn es sich um eine aufgerufen wird, werden die angegebene Url entweder durch Starten Sie ihn in einem externen Webbrowser oder mit direkt mit eingebetteten Webbrowser angezeigt.
   * [`Action.Submit`](#schema-action.submit) – Sammelt Eingabefelder, führt Sie zusammen mit optionalen Datenfeld und sendet ein Ereignis an den Client. Es obliegt dem Client, um zu bestimmen, wie diese Daten verarbeitet werden. Zum Beispiel: Mit BotFramework Bots wäre der Client eine Aktivität über das messaging Medium an den Bot senden.
   * [`Action.ShowCard`](#schema-action.showcard) : Definiert ein AdaptiveCard, die dem Benutzer angezeigt wird, wenn auf die Schaltfläche oder Link geklickt wird.

Eingaben
   * [`Input.Text`](#schema-input.text) – Ermöglicht es einen Benutzer Text eingeben.
   * [`Input.Number`](#schema-input.number) – Ermöglicht es einem Benutzer eine Zahl eingeben.
   * [`Input.Date`](#schema-input.date) – Ermöglicht es einen Benutzer ein Datum auswählen.
   * [`Input.Time`](#schema-input.time) – Ermöglicht es einen Benutzer, die eine Uhrzeit auswählen.
   * [`Input.Toggle`](#schema-input.toggle) – Ermöglicht es einen Benutzer, die zwischen zwei Optionen auswählen.
   * [`Input.ChoiceSet`](#schema-input.choiceset) – Ermöglicht es einem Benutzer eine Wahl eingeben.
   * [`Input.Choice`](#schema-input.choice) – Eine Wahl für die Verwendung in einer ChoiceSet beschreibt.

# <a name="cards"></a>Karten

<a name="schema-adaptivecard"></a>
## <a name="adaptivecard"></a>AdaptiveCard

Das Stammelement in eine Adaptive Card.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"AdaptiveCard"`|Ja|Muss `"AdaptiveCard"`.|1.0
|**actions**|`Action[]`| Nein|Die Aktionen, die in der Aktionsleiste der Karte angezeigt.|1.0
|**body**|`array[]`| Nein|Die Smartcard-Elemente, die in der Region für die primäre Karte angezeigt werden soll.|1.0
|**selectAction**|`object`| Nein|Eine Aktion, die aufgerufen wird, wenn die Karte tippen oder ausgewählt wird. `Action.ShowCard` wird nicht unterstützt.|1.0
|**Version**|`string`|Ja|Die Schemaversion, die diese Karte ist erforderlich. Wenn ein Client ist **niedrigere** als die Version, die `fallbackText` gerendert wird.|1.0
|**fallbackText**|`string`| Nein|Text, der angezeigt wird, wenn der Client die angegebene Version nicht unterstützt (eventuell Markdown).|1.0
|**backgroundImage**|`string`| Nein|Ein Bild, das als Hintergrund der Karte verwendet werden soll.|1.0
|**speak**|`string`| Nein|Gibt an, was für diese gesamte Karte gesprochen werden soll. Dies ist einfacher Text oder SSML-Fragment.|1.0
|**lang**|`string`| Nein|Die Sprache des 2 Buchstaben bestehende ISO 639-1, die in der Karte verwendet. Verwendet, um alle Datum/Uhrzeit-Funktionen zu lokalisieren.|1.0


# <a name="card-elements"></a>Elemente mit Karte

<a name="schema-textblock"></a>
## <a name="textblock"></a>TextBlock

Zeigt Text an, sodass Kontrolle über die Schriftgrade, Stärke und Farbe.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**color**|`string`| Nein|Legt die Farbe des `TextBlock` Elemente.|1.0
|**horizontalAlignment**|`string`| Nein, Standardwert: `"left"`|Steuert, wie Elemente in ihren Container horizontal positioniert werden.|1.0
|**isSubtle**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeigt Text etwas weniger gut sichtbaren angezeigt Farbtönen nach unten an.|1.0
|**maxLines**|`number`| Nein|Gibt die maximale Anzahl der anzuzeigenden Zeilen an.|1.0
|**size**|`string`| Nein|Steuert die Größe des Texts.|1.0
|**text**|`string`|Ja|Anzuzeigende Text.|1.0
|**type**|`"TextBlock"`|Ja|Muss `"TextBlock"`.|1.0
|**weight**|`string`| Nein|Steuert die Gewichtung des `TextBlock` Elemente.|1.0
|**wrap**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, Textumbruch zulassen. Andernfalls wird der Text abgeschnitten.|1.0
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-image"></a>
## <a name="image"></a>Bild

Zeigt ein Bild.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**altText**|`string`| Nein|Alternativtext, die Beschreibung des Images.|1.0
|**horizontalAlignment**|`string`| Nein, Standardwert: `"left"`|Steuert, wie Elemente in ihren Container horizontal positioniert werden.|1.0
|**selectAction**|`object`| Nein|Eine Aktion, die aufgerufen wird, wenn die `Image` getippt oder ausgewählt ist. `Action.ShowCard` wird nicht unterstützt.|1.0
|**size**|`string`| Nein, Standardwert: `"auto"`|Steuert die ungefähre Größe des Bilds an. Die physischen Abmessungen variieren pro Host. Geben Sie `"auto"` für Dimension "true" Image oder `"stretch"` erzwingen den Container ausfüllt.|1.0
|**style**|`string`| Nein|Steuerelemente wie dieser `Image` wird angezeigt.|1.0
|**type**|`"Image"`|Ja|Muss `"Image"`.|1.0
|**url**|`string`|Ja|Die URL zum Bild.|1.0
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-media"></a>
## <a name="media"></a>Media

Zeigt einen MediaPlayer für Audio-und Videoinhalte.

#### <a name="introduced-in-version-11"></a>Eingeführt in Version 1.1

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Media"`|Ja|Muss `"Media"`.|1.1
|**sources**|`object` `[]`| Nein|Array von Media-Quellen, um zu versuchen, spielen.|1.1
|**poster**|`string`| Nein|Die URL eines Bilds, der vor der Wiedergabe angezeigt.|1.1
|**altText**|`string`| Nein|Der Alternativtext, die Audio oder Video beschreibt.|1.1
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.1
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.1
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.1


<a name="schema-mediasource"></a>
## <a name="mediasource"></a>MediaSource

Definiert eine Quelle für ein Medienelement

#### <a name="introduced-in-version-11"></a>Eingeführt in Version 1.1

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**mimeType**|`string`|Ja|MIME-Typ der zugehörigen Medien (z. B. `"video/mp4"`).|1.1
|**url**|`string`|Ja|Die URL auf die Medien.|1.1


# <a name="containers"></a>Container

<a name="schema-container"></a>
## <a name="container"></a>Container

Container werden die Elemente zusammen gruppiert.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Container"`|Ja|Muss `"Container"`.|1.0
|**items**|`array[]`|Ja|Die Elemente der Karte zum Rendern in das `Container`.|1.0
|**selectAction**|`object`| Nein|Eine Aktion, die aufgerufen wird, wenn die `Container` getippt oder ausgewählt ist. `Action.ShowCard` wird nicht unterstützt.|1.0
|**style**|`string`| Nein|Style-Hinweis für `Container`.|1.0
|**verticalContentAlignment**|`string`| Nein, Standardwert: `"top"`|Definiert, wie der Inhalt vertikal innerhalb des Containers ausgerichtet werden soll.|1.1
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-columnset"></a>
## <a name="columnset"></a>ColumnSet

ColumnSet teilt eine Region in Spalten, die zulassen, dass Elemente auf der Seite-an-Seite befinden.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**columns**|`Column[]`| Nein|Das Array von `Columns` die Region zu unterteilen.|1.0
|**selectAction**|`object`| Nein|Eine Aktion, die aufgerufen wird, wenn die `ColumnSet` getippt oder ausgewählt ist. `Action.ShowCard` wird nicht unterstützt.|1.0
|**type**|`"ColumnSet"`|Ja|Muss `"ColumnSet"`.|1.0
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-column"></a>
## <a name="column"></a>Column

Definiert einen Container, der Teil eines Spaltensatzes ist.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**items**|`array[]`|Ja|Die Elemente der Karte einschließt der `Column`.|1.0
|**selectAction**|`object`| Nein|Eine Aktion, die aufgerufen wird, wenn die `Column` getippt oder ausgewählt ist. `Action.ShowCard` wird nicht unterstützt.|1.0
|**style**|`string`| Nein|Style-Hinweis für `Column`.|1.0
|**width**|`string,number`| Nein|`"auto"`, `"stretch"`, oder eine Zahl, die relative Breite der Spalte in der Spaltengruppe.|1.0
|**type**|`"Column"`| Nein|Muss `"Column"`.|1.0
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-factset"></a>
## <a name="factset"></a>FactSet

Das FactSet-Element zeigt eine Reihe von Fakten (d. h. Name/Wert-Paare) in einer Tabelle an.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**facts**|`Fact[]`|Ja|Das Array von `Fact`s.|1.0
|**type**|`"FactSet"`|Ja|Muss `"FactSet"`.|1.0
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-fact"></a>
## <a name="fact"></a>Faktentabelle

Beschreibt den Fakten in einer FactSet als Schlüssel/Wert-Paar.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Fact"`| Nein|&nbsp;|1.0
|**title**|`string`|Ja|Der Titel des Fakts.|1.0
|**value**|`string`|Ja|Der Wert des Fakts.|1.0


<a name="schema-imageset"></a>
## <a name="imageset"></a>ImageSet

Die ImageSet zeigt eine Auflistung von Bildern, die ähnlich wie in einem Katalog an.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**Images**|`Image[]`|Ja|Das Array von `Image` Elemente angezeigt.|1.0
|**imageSize**|`string`| Nein, Standardwert: `"auto"`|Steuert die ungefähre Größe des Bilds an. Die physischen Abmessungen variieren pro Host. Geben Sie `"auto"` für Dimension "true" Image oder `"stretch"` erzwingen den Container ausfüllt.|1.0
|**type**|`"ImageSet"`|Ja|Muss `"ImageSet"`.|1.0
|**id**|`string`| Nein|Ein eindeutiger Bezeichner, der dem Element zugeordnet ist.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


# <a name="actions"></a>Aktionen

<a name="schema-action.openurl"></a>
## <a name="actionopenurl"></a>Action.OpenUrl

Wenn aufgerufen, zeigen Sie die angegebene Url entweder durch Starten Sie ihn in einem externen Webbrowser oder mit direkt mit eingebetteten Webbrowser aus.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Action.OpenUrl"`|Ja|Muss `"Action.OpenUrl"`.|1.0
|**title**|`string`|Ja|Bezeichnung für die Schaltfläche oder Link, der diese Aktion darstellt.|1.0
|**iconUrl**|`string`| Nein|Optionales Symbol, das auf die Aktion in Verbindung mit dem Titel angezeigt werden|1.1
|**url**|`string`|Ja|Die URL zu öffnen.|1.0


<a name="schema-action.submit"></a>
## <a name="actionsubmit"></a>Action.Submit

Erfasst die Eingabefelder, führt Sie zusammen mit optionalen Datenfeld und sendet ein Ereignis an den Client. Es obliegt dem Client, um zu bestimmen, wie diese Daten verarbeitet werden. Zum Beispiel: Mit BotFramework Bots wäre der Client eine Aktivität über das messaging Medium an den Bot senden.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Action.Submit"`|Ja|Muss `"Action.Submit"`.|1.0
|**title**|`string`|Ja|Bezeichnung für die Schaltfläche oder Link, der diese Aktion darstellt.|1.0
|**iconUrl**|`string`| Nein|Optionales Symbol, das auf die Aktion in Verbindung mit dem Titel angezeigt werden|1.1
|**data**|`string,object`| Nein|Anfängliche Daten, denen Eingabefelder mit kombiniert werden. Dies sind im Wesentlichen 'hidden' Eigenschaften.|1.0


<a name="schema-action.showcard"></a>
## <a name="actionshowcard"></a>Action.ShowCard

Definiert eine AdaptiveCard, die dem Benutzer angezeigt wird, wenn auf die Schaltfläche oder Link geklickt wird.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Action.ShowCard"`|Ja|Muss `"Action.ShowCard"`.|1.0
|**title**|`string`|Ja|Bezeichnung für die Schaltfläche oder Link, der diese Aktion darstellt.|1.0
|**iconUrl**|`string`| Nein|Optionales Symbol, das auf die Aktion in Verbindung mit dem Titel angezeigt werden|1.1
|**card**|`object`|Ja|Das Stammelement in eine Adaptive Card.|1.0


# <a name="inputs"></a>Eingaben

<a name="schema-input.text"></a>
## <a name="inputtext"></a>Input.Text

Kann einen Benutzer Text eingeben.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**id**|`string`|Ja|Eindeutiger Bezeichner für den Wert. Verwendet, um die gesammelten Eingabe zu identifizieren, wenn die Aktion senden ausgeführt wird.|1.0
|**isMultiline**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, können Sie mehrere Zeilen der Eingabe.|1.0
|**maxLength**|`number`| Nein|Hinweis der maximale Länge von Zeichen zum Sammeln von (kann von einigen Clients ignoriert werden).|1.0
|**placeholder**|`string`| Nein|Beschreibung der gewünschten Eingabe. Angezeigt, wenn kein Text eingegeben wurde.|1.0
|**style**|`string`| Nein, Standardwert: `"text"`|Style-Hinweis für `Input.Text`.|1.0
|**type**|`"Input.Text"`|Ja|Muss `"Input.Text"`.|1.0
|**value**|`string`| Nein|Der Anfangswert für dieses Feld.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-input.number"></a>
## <a name="inputnumber"></a>Input.Number

Ermöglicht einem Benutzer eine Zahl eingeben.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**id**|`string`|Ja|Eindeutiger Bezeichner für den Wert. Verwendet, um die gesammelten Eingabe zu identifizieren, wenn die Aktion senden ausgeführt wird.|1.0
|**max**|`number`| Nein|Hinweis der maximale Wert (kann von einigen Clients ignoriert werden).|1.0
|**min**|`number`| Nein|Hinweis der Mindestwert (kann von einigen Clients ignoriert werden).|1.0
|**placeholder**|`string`| Nein|Beschreibung der gewünschten Eingabe. Angezeigt, wenn keine Auswahl getroffen wurde.|1.0
|**type**|`"Input.Number"`|Ja|Muss `"Input.Number"`.|1.0
|**value**|`number`| Nein|Der Anfangswert für dieses Feld.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-input.date"></a>
## <a name="inputdate"></a>Input.Date

Erlaubt dem Benutzer ein Datum auswählen.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**id**|`string`|Ja|Eindeutiger Bezeichner für den Wert. Verwendet, um die gesammelten Eingabe zu identifizieren, wenn die Aktion senden ausgeführt wird.|1.0
|**max**|`string`| Nein|Hinweis der maximale Wert, der im ISO-8601-Format (kann von einigen Clients ignoriert werden) ausgedrückt wird.|1.0
|**min**|`string`| Nein|Hinweis der minimale Wert, der im ISO-8601-Format (kann von einigen Clients ignoriert werden) ausgedrückt wird.|1.0
|**placeholder**|`string`| Nein|Beschreibung der gewünschten Eingabe. Angezeigt, wenn keine Auswahl getroffen wurde.|1.0
|**type**|`"Input.Date"`|Ja|Muss `"Input.Date"`.|1.0
|**value**|`string`| Nein|Der Anfangswert für dieses Feld im ISO-8601-Format ausgedrückt.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-input.time"></a>
## <a name="inputtime"></a>Input.Time

Ermöglicht Benutzern eine Uhrzeit auswählen.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**id**|`string`|Ja|Eindeutiger Bezeichner für den Wert. Verwendet, um die gesammelten Eingabe zu identifizieren, wenn die Aktion senden ausgeführt wird.|1.0
|**max**|`string`| Nein|Hinweis der maximale Wert (kann von einigen Clients ignoriert werden).|1.0
|**min**|`string`| Nein|Hinweis der Mindestwert (kann von einigen Clients ignoriert werden).|1.0
|**placeholder**|`string`| Nein|Beschreibung der gewünschten Eingabe. Angezeigt, wenn keine Zeit ausgewählt wurde.|1.0
|**type**|`"Input.Time"`|Ja|Muss `"Input.Time"`.|1.0
|**value**|`string`| Nein|Der Anfangswert für dieses Feld im ISO-8601-Format ausgedrückt.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-input.toggle"></a>
## <a name="inputtoggle"></a>Input.Toggle

Können Benutzer zwischen zwei Optionen auswählen.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**id**|`string`|Ja|Eindeutiger Bezeichner für den Wert. Verwendet, um die gesammelten Eingabe zu identifizieren, wenn die Aktion senden ausgeführt wird.|1.0
|**title**|`string`|Ja|Titel für die ein/aus|1.0
|**type**|`"Input.Toggle"`|Ja|Input.Toggle|1.0
|**value**|`string`| Nein, Standardwert: `"false"`|Der aktuelle ausgewählte Wert. Wenn das Element ausgewählt ist, dass "ValueOn" verwendet werden, andernfalls "ValueOff"|1.0
|**valueOff**|`string`| Nein, Standardwert: `"false"`|Der Wert, wenn Sie deaktiviert ist|1.0
|**valueOn**|`string`| Nein, Standardwert: `"true"`|Der Wert, wenn die Umschaltfläche aktiviert ist|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-input.choiceset"></a>
## <a name="inputchoiceset"></a>Input.ChoiceSet

Ermöglicht einem Benutzer eine Wahl eingeben.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**choices**|`Input.Choice[]`|Ja|`Choice` Optionen.|1.0
|**id**|`string`|Ja|Eindeutiger Bezeichner für den Wert. Verwendet, um die gesammelten Eingabe zu identifizieren, wenn die Aktion senden ausgeführt wird.|1.0
|**isMultiSelect**|`boolean`| Nein, Standardwert: `false`|Können Sie mehrere Optionen ausgewählt werden.|1.0
|**style**|`string`| Nein, Standardwert: `"compact"`|Style-Hinweis für `Input.ChoiceSet`.|1.0
|**type**|`"Input.ChoiceSet"`|Ja|Muss `"Input.ChoiceInput"`.|1.0
|**value**|`string`| Nein|Die erste Wahl (oder einen Satz von Optionen), die ausgewählt werden soll. Geben Sie eine durch Trennzeichen getrennte Zeichenfolge von Werten für die Mehrfachauswahl können.|1.0
|**spacing**|`string`| Nein|Steuert die Größe des Abstands zwischen diesem Element und das vorangehende Element.|1.0
|**separator**|`boolean`| Nein, Standardwert: `false`|Wenn `true`, zeichnen Sie eine Trennung Linie am oberen Rand des Elements.|1.0


<a name="schema-input.choice"></a>
## <a name="inputchoice"></a>Input.Choice

Beschreibt eine Wahl für die Verwendung in einer ChoiceSet an.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**type**|`"Input.Choice"`| Nein|&nbsp;|1.0
|**title**|`string`|Ja|Anzuzeigende Text.|1.0
|**value**|`string`|Ja|Der Rohwert für die Auswahl. **Hinweis:** verwenden Sie keine `,` in den Wert, da eine `ChoiceSet` mit `isMultiSelect` festgelegt `true` gibt eine durch Trennzeichen getrennte Zeichenfolge Auswahlwerte zurück.|1.0
