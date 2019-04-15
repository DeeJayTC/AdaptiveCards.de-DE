---
title: HostConfig für mit Adaptive Cards
author: paulcam206
ms.author: paulcam
ms.date: 09/18/2018
ms.topic: reference
ms.openlocfilehash: 46ba9987cf162e95ab86dcdafa55e10df29b1121
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552592"
---
# <a name="what-is-hostconfig"></a>Was ist HostConfig?
`HostConfig` ist eine **plattformübergreifende Konfigurationsobjekt** , der angibt, wie eine Adaptive Card Renderer UI generiert.

Dadurch können die Eigenschaften, die plattformunabhängig von Renderern, die auf verschiedenen Plattformen und Geräten gemeinsam verwendet werden. Darüber hinaus können Tools erstellt werden, wodurch Sie sich ein Überblick über das Aussehen und Verhalten, die Karte müssten für eine bestimmte Umgebung.

Ein Beispiel finden Sie [HostConfig.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) um ein Gefühl für deren Inhalte zu erhalten.

---

   * [`AdaptiveCardConfig`](#schema-adaptivecardconfig) -Toplevel Optionen für `AdaptiveCards`
   * [`ActionsConfig`](#schema-actionsconfig) -Optionen für `Action`s
   * [`ContainerStylesConfig`](#schema-containerstylesconfig) -Steuerelemente formatieren für Standard- und Hervorhebung von Containern
   * [`FactSetConfig`](#schema-factsetconfig) -Steuert die Anzeige von `FactSet`s
   * [`FontSizesConfig`](#schema-fontsizesconfig) -Steuert das Größe Schriftarteigenschaften für unterschiedliche Textformate
   * [`FontWeightsConfig`](#schema-fontweightsconfig) -Steuert das Gewicht von Schriftarteigenschaften
   * [`ForegroundColorsConfig`](#schema-foregroundcolorsconfig) -Steuert verschiedene Schriftfarben
   * [`ImageSetConfig`](#schema-imagesetconfig) -Steuert wie `ImageSet`s werden angezeigt.
   * [`ImageSizesConfig`](#schema-imagesizesconfig) -Steuert das `Image` Größen
   * [`MediaConfig`](#schema-mediaconfig) -Steuert die Anzeige und das Verhalten der `Media` Elemente
   * [`SeparatorConfig`](#schema-separatorconfig) -Steuert, wie der Trennzeichen angezeigt werden
   * [`ShowCardConfig`](#schema-showcardconfig) -Steuert das Verhalten und die Gestaltung der `Action.ShowCard`
   * [`SpacingsConfig`](#schema-spacingsconfig) -Steuert, wie Elemente angeordnet werden
   * [`TextBlockConfig`](#schema-textblockconfig) -Parameter, die Steuern der Anzeige von text

# <a name="card-configuration"></a>Netzwerkschnittstellenkarten-Konfiguration

<a name="schema-adaptivecardconfig"></a>
## <a name="adaptivecardconfig"></a>AdaptiveCardConfig

TopLevel-Optionen für `AdaptiveCards`

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**allowCustomStyle**|`boolean`| Nein, Standardwert: `true`|Steuert, ob die benutzerdefinierte Formatierung zulässig ist|1.0
|**supportsInteractivity**|`boolean`| Nein, Standardwert: `true`|Steuern, ob es interaktiven `Action`aufgerufen werden dürfen|1.0
|**imageBaseUrl**|`string`| Nein|Basis-URL verwendet werden, beim Laden von Ressourcen|1.0
|**fontFamily**|`string`| Nein, Standardwert: `"Calibri"`|Schriftart zur Verwendung beim Rendern von text|1.0
|**actions**|`object`| Nein|Optionen für `Action`s|1.0
|**adaptiveCard**|`object`| Nein|TopLevel-Optionen für `AdaptiveCards`|1.0
|**containerStyles**|`object`| Nein|Steuerelemente formatieren für Standard- und Hervorhebung von Containern|1.0
|**imageSizes**|`object`| Nein|Steuerelemente `Image` Größen|1.0
|**imageSet**|`object`| Nein|Steuerelemente wie `ImageSet`s werden angezeigt.|1.0
|**factSet**|`object`| Nein|Steuert die Anzeige von `FactSet`s|1.0
|**fontSizes**|`object`| Nein|Steuert die Größe der Schriftarteigenschaften für unterschiedliche Textformate|1.0
|**fontWeights**|`object`| Nein|Steuerelemente Gewichtung Schriftarteigenschaften|1.0
|**spacing**|`object`| Nein|Steuert, wie Elemente angeordnet werden|1.0
|**separator**|`object`| Nein|Steuert, wie der Trennzeichen angezeigt werden|1.0
|**media**|`object`| Nein|Steuert die Anzeige und das Verhalten der `Media` Elemente|1.1


<a name="schema-actionsconfig"></a>
## <a name="actionsconfig"></a>ActionsConfig

Optionen für `Action`s

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**actionsOrientation**|`string`| Nein, Standardwert: `"horizontal"`|Steuerelemente wie Schaltflächen angeordnet werden|1.0
|**actionAlignment**|`string`| Nein, Standardwert: `"stretch"`|Steuerelementlayout von Schaltflächen|1.0
|**buttonSpacing**|`integer`| Nein, Standardwert: `10`|Steuert, wie viel Abstand zwischen Schaltflächen|1.0
|**maxActions**|`integer`| Nein, Standardwert: `5`|Steuert, wie viele Aktionen insgesamt zulässig sind|1.0
|**spacing**|`string`| Nein, Standardwert: `"default"`|Steuerelemente, die insgesamt Abstand der Action-element|1.0
|**showCard**|`object`| Nein|Verhalten für Steuerelemente und die Gestaltung der `Action.ShowCard`|1.0
|**iconPlacement**|`string`| Nein, Standardwert: `"aboveTitle"`|Steuert, wo das Symbol "Aktion"|1.0
|**iconSize**|`integer`| Nein, Standardwert: `30`|Größe der Steuerelemente von Aktionssymbol|1.0


<a name="schema-containerstylesconfig"></a>
## <a name="containerstylesconfig"></a>ContainerStylesConfig

Steuerelemente formatieren für Standard- und Hervorhebung von Containern

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**default**|`object`| Nein|Container-Standardformat|1.0
|**emphasis**|`object`| Nein|Container-Format zur Hervorhebung verwendet.|1.0


<a name="schema-factsetconfig"></a>
## <a name="factsetconfig"></a>FactSetConfig

Steuert die Anzeige von `FactSet`s

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**title**|`object`| Nein, Standardwert: `{"weight":"bolder","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":150}`|Parameter, die Steuern der Anzeige von text|1.0
|**value**|`object`| Nein, Standardwert: `{"weight":"default","size":"default","color":"default","isSubtle":false,"wrap":true,"maxWidth":0}`|Parameter, die Steuern der Anzeige von text|1.0
|**spacing**|`integer`| Nein, Standardwert: `10`|&nbsp;|1.0


<a name="schema-fontsizesconfig"></a>
## <a name="fontsizesconfig"></a>FontSizesConfig

Steuert die Größe der Schriftarteigenschaften für unterschiedliche Textformate

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| Nein, Standardwert: `10`|Kleinen Schriftgrad|1.0
|**default**|`integer`| Nein, Standardwert: `12`|Standardschriftgröße|1.0
|**medium**|`integer`| Nein, Standardwert: `14`|Mittlere Schriftgrad|1.0
|**large**|`integer`| Nein, Standardwert: `17`|Große Schriftgrad|1.0
|**extraLarge**|`integer`| Nein, Standardwert: `20`|Extra groß Schriftgrad|1.0


<a name="schema-fontweightsconfig"></a>
## <a name="fontweightsconfig"></a>FontWeightsConfig

Steuerelemente Gewichtung Schriftarteigenschaften

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

Steuerelemente wie `ImageSet`s werden angezeigt.

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**imageSize**|`string`| Nein, Standardwert: `"auto"`|Steuerelemente einzelnen Bild-größenanpassung|1.0
|**maxImageHeight**|`integer`| Nein, Standardwert: `100`|Bildhöhe auf diesen Wert zu beschränken|1.0


<a name="schema-imagesizesconfig"></a>
## <a name="imagesizesconfig"></a>ImageSizesConfig

Steuerelemente `Image` Größen

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| Nein, Standardwert: `80`|Größenwert für Miniaturansicht|1.0
|**medium**|`integer`| Nein, Standardwert: `120`|Mittlere Bild Größenwert|1.0
|**large**|`integer`| Nein, Standardwert: `180`|Großes Bild Größenwert|1.0


<a name="schema-mediaconfig"></a>
## <a name="mediaconfig"></a>MediaConfig

Steuert die Anzeige und das Verhalten der `Media` Elemente

#### <a name="introduced-in-version-11"></a>Eingeführt in Version 1.1

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**defaultPoster**|`string`| Nein|URI zu Bild angezeigt wird, wenn die Schaltfläche "Abspielen" wurde nicht aufgerufen wurde|1.1
|**playButton**|`string`| Nein|Bild, um anzuzeigen, wie die Schaltfläche "Abspielen|1.1
|**allowInlinePlayback**|`boolean`| Nein, Standardwert: `true`|Angibt, ob Media Inline anzeigen oder extern aufrufen|1.1


<a name="schema-separatorconfig"></a>
## <a name="separatorconfig"></a>SeparatorConfig

Steuert, wie der Trennzeichen angezeigt werden

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**lineThickness**|`integer`| Nein, Standardwert: `1`|Stärke der Trennlinie|1.0
|**lineColor**|`string,null`| Nein, Standardwert: `#B2000000`|Farbe beim Zeichnen der Trennlinie verwendet|1.0


<a name="schema-showcardconfig"></a>
## <a name="showcardconfig"></a>ShowCardConfig

Verhalten für Steuerelemente und die Gestaltung der `Action.ShowCard`

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**actionMode**|`string`| Nein, Standardwert: `"inline"`|Steuert die Anzeige die Karte|1.0
|**style**|`object`| Nein, Standardwert: `emphasis`|Formatieren von Steuerelementen eines Containers|1.0
|**inlineTopMargin**|`integer`| Nein, Standardwert: `16`|Stärke des Rands verwenden, wenn die Karte anzeigen|1.0


<a name="schema-spacingsconfig"></a>
## <a name="spacingsconfig"></a>SpacingsConfig

Steuert, wie Elemente angeordnet werden

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**small**|`integer`| Nein, Standardwert: `3`|Kleine Spacing-Wert|1.0
|**default**|`integer`| Nein, Standardwert: `8`|Standardwert für Abstand|1.0
|**medium**|`integer`| Nein, Standardwert: `20`|Mittlere Spacing-Wert|1.0
|**large**|`integer`| Nein, Standardwert: `30`|Große Spacing-Wert|1.0
|**extraLarge**|`integer`| Nein, Standardwert: `40`|Extra groß Spacing-Wert|1.0
|**padding**|`integer`| Nein, Standardwert: `20`|Der Wert für Leerraum|1.0


<a name="schema-textblockconfig"></a>
## <a name="textblockconfig"></a>TextBlockConfig

Parameter, die Steuern der Anzeige von text

|Eigenschaft|Typ|Erforderlich|Beschreibung|Version|
|--------|----|--------|-----------|-------|
|**size**|`string`| Nein, Standardwert: `"default"`|Schriftgrad verwenden, wenn eine Karte angeben, nicht|1.0
|**weight**|`string`| Nein, Standardwert: `"normal"`|Zu verwenden, wenn eine Karte angeben, nicht Schriftbreite|1.0
|**color**|`string`| Nein, Standardwert: `"default"`|Schriftfarbe beim Angeben einer Karte, nicht zu verwendenden|1.0
|**isSubtle**|`boolean`| Nein, Standardwert: `false`|Text subtil, wenn eine Karte angeben, nicht sein sollten|1.0
|**wrap**|`boolean`| Nein, Standardwert: `true`|Textfeld umbrochen werden soll, wenn eine Karte angeben, nicht|1.0
|**maxWidth**|`integer`| Nein, Standardwert: `0`|Maximale Breite verwenden, wenn eine Karte angeben, nicht|1.0
