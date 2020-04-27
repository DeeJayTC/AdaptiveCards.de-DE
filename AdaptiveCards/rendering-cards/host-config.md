---
title: HostConfig für adaptive Karten
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 848ce3dd2ccca1f975dfd330c1c88292c753641d
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "77454923"
---
# <a name="what-is-hostconfig"></a>Was ist HostConfig?
`HostConfig` ist ein **plattformübergreifendes Konfigurationsobjekt**, das angibt, wie ein Renderer für adaptive Karten eine Benutzeroberfläche generiert.

So können plattformunabhängige Eigenschaften für Renderer auf verschiedenen Plattformen und Geräten freigegeben werden. Zudem können Tools erstellt werden, die dir eine Vorstellung vom Aussehen und Verhalten einer Karte in einer bestimmten Umgebung vermitteln.

Informationen zu den Inhalten findest du in diesem [HostConfig.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json)-Beispiel.

---

   * [`AdaptiveCardConfig`](#schema-adaptivecardconfig): Optionen auf oberster Ebene für `AdaptiveCards`
   * [`ActionsConfig`](#schema-actionsconfig): Optionen für `Action`-Elemente
   * [`ContainerStylesConfig`](#schema-containerstylesconfig): Steuert den Stil für Container mit Standard- und Hervorhebungsformatierung
   * [`FactSetConfig`](#schema-factsetconfig): Steuert die Anzeige von `FactSet`-Elementen
   * [`FontSizesConfig`](#schema-fontsizesconfig): Steuert die Metrik für den Schriftgrad für verschiedene Schriftarten
   * [`FontWeightsConfig`](#schema-fontweightsconfig): Steuert die Metrik für die Strichstärke der Schrift
   * [`ForegroundColorsConfig`](#schema-foregroundcolorsconfig): Steuert verschiedene Schriftfarben
   * [`ImageSetConfig`](#schema-imagesetconfig): Steuert die Anzeige von `ImageSet`-Elementen
   * [`ImageSizesConfig`](#schema-imagesizesconfig): Steuert `Image`-Größen
   * [`MediaConfig`](#schema-mediaconfig): Steuert die Anzeige und das Verhalten von `Media`-Elementen
   * [`SeparatorConfig`](#schema-separatorconfig): Steuert die Anzeige von Trennzeichen
   * [`ShowCardConfig`](#schema-showcardconfig): Steuert das Verhalten und die Formatierung von `Action.ShowCard`
   * [`SpacingsConfig`](#schema-spacingsconfig): Steuert das Layout von Elementen
   * [`TextBlockConfig`](#schema-textblockconfig): Parameter für die Steuerung der Textanzeige

# <a name="card-configuration"></a>Kartenkonfiguration

<a name="schema-adaptivecardconfig"></a>
## <a name="adaptivecardconfig"></a>AdaptiveCardConfig

Optionen auf oberster Ebene für `AdaptiveCards`

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**allowCustomStyle**|`boolean`| Nein, Standardwert: `true`|Steuert, ob eine benutzerdefinierte Formatierung zulässig ist|1.0
|**supportsInteractivity**|`boolean`| Nein, Standardwert: `true`|Steuert, ob interaktive `Action`-Elemente aufgerufen werden dürfen|1.0
|**imageBaseUrl**|`string`| Nein|Zu verwendende Basis-URL beim Laden von Ressourcen|1.0
|**fontFamily**|`string`| Nein, Standardwert: `"Calibri"`|Zu verwendende Schriftart beim Rendern von Text|1.0
|**Aktionen**|`object`| Nein|Optionen für `Action`-Elemente|1.0
|**adaptiveCard**|`object`| Nein|Optionen auf oberster Ebene für `AdaptiveCards`|1.0
|**containerStyles**|`object`| Nein|Steuert den Stil für Container mit Standard- und Hervorhebungsformatierung|1.0
|**imageSizes**|`object`| Nein|Steuert `Image`-Größen|1.0
|**imageSet**|`object`| Nein|Steuert die Anzeige von `ImageSet`-Elementen|1.0
|**factSet**|`object`| Nein|Steuert die Anzeige von `FactSet`-Elementen|1.0
|**fontSizes**|`object`| Nein|Steuert die Metrik für den Schriftgrad für verschiedene Schriftarten|1.0
|**fontWeights**|`object`| Nein|Steuert die Metrik für die Strichstärke der Schrift|1.0
|**spacing**|`object`| Nein|Steuert das Layout von Elementen|1.0
|**separator**|`object`| Nein|Steuert die Anzeige von Trennzeichen|1.0
|**media**|`object`| Nein|Steuert die Anzeige und das Verhalten von `Media`-Elementen|1.1


<a name="schema-actionsconfig"></a>
## <a name="actionsconfig"></a>ActionsConfig

Optionen für `Action`-Elemente

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**actionsOrientation**|`string`| Nein, Standardwert: `"horizontal"`|Steuert die Ausrichtung von Schaltflächen|1.0
|**actionAlignment**|`string`| Nein, Standardwert: `"stretch"`|Steuert das Layout von Schaltflächen|1.0
|**buttonSpacing**|`integer`| Nein, Standardwert: `10`|Steuert die Abstände zwischen Schaltflächen|1.0
|**maxActions**|`integer`| Nein, Standardwert: `5`|Steuert die insgesamt zulässige Anzahl von Aktionen|1.0
|**spacing**|`string`| Nein, Standardwert: `"default"`|Steuert den Gesamtabstand um ein Aktionselement|1.0
|**showCard**|`object`| Nein|Steuert das Verhalten und die Formatierung von `Action.ShowCard`|1.0
|**iconPlacement**|`string`| Nein, Standardwert: `"aboveTitle"`|Steuert die Platzierung des Aktionssymbols|1.0
|**iconSize**|`integer`| Nein, Standardwert: `30`|Steuert die Größe des Aktionssymbols|1.0


<a name="schema-containerstylesconfig"></a>
## <a name="containerstylesconfig"></a>ContainerStylesConfig

Steuert den Stil für Container mit Standard- und Hervorhebungsformatierung

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**default**|`object`| Nein|Standardcontainerstil|1.0
|**emphasis**|`object`| Nein|Containerstil für Hervorhebungen|1.0


<a name="schema-factsetconfig"></a>
## <a name="factsetconfig"></a>FactSetConfig

Steuert die Anzeige von `FactSet`-Elementen

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**title**|`object`| Nein, Standardwert: `{"weight":"bolder","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":150}`|Parameter für die Steuerung der Textanzeige|1.0
|**value**|`object`| Nein, Standardwert: `{"weight":"default","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":0}`|Parameter für die Steuerung der Textanzeige|1.0
|**spacing**|`integer`| Nein, Standardwert: `10`|&nbsp;|1.0


<a name="schema-fontsizesconfig"></a>
## <a name="fontsizesconfig"></a>FontSizesConfig

Steuert die Metrik für den Schriftgrad für verschiedene Schriftarten

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| Nein, Standardwert: `10`|Kleiner Schriftgrad|1.0
|**default**|`integer`| Nein, Standardwert: `12`|Standardschriftgrad|1.0
|**medium**|`integer`| Nein, Standardwert: `14`|Mittlerer Schriftgrad|1.0
|**large**|`integer`| Nein, Standardwert: `17`|Großer Schriftgrad|1.0
|**extraLarge**|`integer`| Nein, Standardwert: `20`|Besonders großer Schriftgrad|1.0


<a name="schema-fontweightsconfig"></a>
## <a name="fontweightsconfig"></a>FontWeightsConfig

Steuert die Metrik für die Strichstärke der Schrift

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**lighter**|`integer`| Nein, Standardwert: `200`|&nbsp;|1.0
|**default**|`integer`| Nein, Standardwert: `400`|&nbsp;|1.0
|**bolder**|`integer`| Nein, Standardwert: `800`|&nbsp;|1.0


<a name="schema-foregroundcolorsconfig"></a>
## <a name="foregroundcolorsconfig"></a>ForegroundColorsConfig

Steuert verschiedene Schriftfarben

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**default**|`object`| Nein, Standardwert: `{"default":"#FF000000","subtle":"#B2000000"}`|&nbsp;|1.0
|**accent**|`object`| Nein, Standardwert: `{"default":"#FF0000FF","subtle":"#B20000FF"}`|&nbsp;|1.0
|**dark**|`object`| Nein, Standardwert: `{"default":"#FF101010","subtle":"#B2101010"}`|&nbsp;|1.0
|**light**|`object`| Nein, Standardwert: `{"default":"#FFFFFFFF","subtle":"#B2FFFFFF"}`|&nbsp;|1.0
|**good**|`object`| Nein, Standardwert: `{"default":"#FF008000","subtle":"#B2008000"}`|&nbsp;|1.0
|**warning**|`object`| Nein, Standardwert: `{"default":"#FFFFD700","subtle":"#B2FFD700"}`|&nbsp;|1.0
|**attention**|`object`| Nein, Standardwert: `{"default":"#FF8B0000","subtle":"#B28B0000"}`|&nbsp;|1.0


<a name="schema-imagesetconfig"></a>
## <a name="imagesetconfig"></a>ImageSetConfig

Steuert die Anzeige von `ImageSet`-Elementen

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**imageSize**|`string`| Nein, Standardwert: `"auto"`|Steuert die Größe einzelner Bilder|1.0
|**maxImageHeight**|`integer`| Nein, Standardwert: `100`|Beschränkt die Bildhöhe auf diesen Wert|1.0


<a name="schema-imagesizesconfig"></a>
## <a name="imagesizesconfig"></a>ImageSizesConfig

Steuert `Image`-Größen

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| Nein, Standardwert: `80`|Wert für geringe Bildgröße|1.0
|**medium**|`integer`| Nein, Standardwert: `120`|Wert für mittlere Bildgröße|1.0
|**large**|`integer`| Nein, Standardwert: `180`|Wert für große Bildgröße|1.0


<a name="schema-mediaconfig"></a>
## <a name="mediaconfig"></a>MediaConfig

Steuert die Anzeige und das Verhalten von `Media`-Elementen

#### <a name="introduced-in-version-11"></a>Eingeführt in Version 1.1

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**defaultPoster**|`string`| Nein|URI zum anzuzeigenden Bild, wenn die Wiedergabeschaltfläche nicht aufgerufen wurde|1.1
|**playButton**|`string`| Nein|Bild, das als Wiedergabeschaltfläche angezeigt werden soll|1.1
|**allowInlinePlayback**|`boolean`| Nein, Standardwert: `true`|Gibt an, ob Medien inline angezeigt oder extern aufgerufen werden|1.1


<a name="schema-separatorconfig"></a>
## <a name="separatorconfig"></a>SeparatorConfig

Steuert die Anzeige von Trennzeichen

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**lineThickness**|`integer`| Nein, Standardwert: `1`|Stärke der Trennlinie|1.0
|**lineColor**|`string,null`| Nein, Standardwert: `#B2000000`|Beim Zeichnen einer Trennlinie zu verwendende Farbe|1.0


<a name="schema-showcardconfig"></a>
## <a name="showcardconfig"></a>ShowCardConfig

Steuert das Verhalten und die Formatierung von `Action.ShowCard`

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**actionMode**|`string`| Nein, Standardwert: `"inline"`|Steuert die Anzeige der Karte|1.0
|**style**|`object`| Nein, Standardwert: `emphasis`|Steuert den Stil eines Containers|1.0
|**inlineTopMargin**|`integer`| Nein, Standardwert: `16`|Beim Anzeigen der Karte zu verwendende Randgröße|1.0


<a name="schema-spacingsconfig"></a>
## <a name="spacingsconfig"></a>SpacingsConfig

Steuert das Layout von Elementen

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| Nein, Standardwert: `3`|Geringer Abstandswert|1.0
|**default**|`integer`| Nein, Standardwert: `8`|Standardabstandswert|1.0
|**medium**|`integer`| Nein, Standardwert: `20`|Mittlerer Abstandswert|1.0
|**large**|`integer`| Nein, Standardwert: `30`|Großer Abstandswert|1.0
|**extraLarge**|`integer`| Nein, Standardwert: `40`|Besonders großer Abstandswert|1.0
|**padding**|`integer`| Nein, Standardwert: `20`|Wert für den Innenabstand|1.0


<a name="schema-textblockconfig"></a>
## <a name="textblockconfig"></a>TextBlockConfig

Parameter für die Steuerung der Textanzeige

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**size**|`string`| Nein, Standardwert: `"default"`|Zu verwendender Schriftgrad, wenn dieser für die Karte nicht angegeben ist|1.0
|**weight**|`string`| Nein, Standardwert: `"normal"`|Zu verwendende Strichstärke der Schrift, wenn diese für die Karte nicht angegeben ist|1.0
|**color**|`string`| Nein, Standardwert: `"default"`|Zu verwendende Schriftfarbe, wenn diese für die Karte nicht angegeben ist|1.0
|**isSubtle**|`boolean`| Nein, Standardwert: `false`|Gibt an, ob der Text bei fehlender Angabe für die Karte dezent dargestellt werden sein soll|1.0
|**wrap**|`boolean`| Nein, Standardwert: `true`|Gibt an, ob der Text bei fehlender Angabe für die Karte umbrochen werden soll|1.0
|**maxWidth**|`integer`| Nein, Standardwert: `0`|Maximale Breite, wenn diese für die Karte nicht angegeben ist|1.0
