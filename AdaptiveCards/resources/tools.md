---
title: Mit Adaptive Cards-Tools
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: 35ce89653a6cf2a313518be0f221a166e1eb7711
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552502"
---
# <a name="card-designer"></a>Karten-Designer 

Benötigen Sie für ein Tool zum Entwerfen Ihrer Karten? Finden Sie den Designer adaptive Card browserbasierte und in [https://adaptivecards.io/designer](https://adaptivecards.io/designer)

[![Designer-screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)

## <a name="embed-the-designer-into-your-app"></a>Den Designer in Ihre Anwendung einbetten.

Aber warum es Ihren Benutzern zu senden, wenn möglich **einbetten den Karte Designer direkt in Ihrer Web** -app mit unseren JavaScript-Bibliothek. 

Sehen Sie sich die [Adaptivecards-Designer](https://npmjs.com/adaptivecards-designer) Paket, um zu beginnen.

# <a name="schema-validation"></a>Schema-Validierung

Schema-Validierung ist eine leistungsfähige Möglichkeit einfacher erstellen und aktivieren die Tools zu machen.

## <a name="json-schema"></a>JSON-Schema
Wir haben eine vollständige bereitgestellt [JSON-Schemadatei](http://adaptivecards.io/schemas/adaptive-card.json) zum Bearbeiten und Validieren mit adaptive Cards im JSON-Format.

Sie können automatische Intellisense in Visual Studio und Visual Studio Code abrufen, mit einem `$schema` Verweis.

![Ungültige](media/tools/invalidjson1.png)

![AutoVervollständigen-Funktion](media/tools/autocomplete.png)

### <a name="example"></a>Beispiel

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "0.5",
    "body": []
}
```

# <a name="tools-and-samples"></a>Tools und Beispiele
Es gibt einige Tools und Beispiele in der ursprünglichen Struktur nützliche Verweise als auch nützliche Tools sind.

## <a name="visual-studio-code-extension"></a>Visual Studio Code-Erweiterung
Wir haben Visual Studio Code-Erweiterung erstellt, die Sie die Karte visuell darstellen, die Sie in Echtzeit in den Editor bearbeitet werden können. 

![Erweiterung](media/tools/vscode-extension.png)

Klicken Sie zum Installieren Erweiterungen Marketplace zu öffnen, und suchen Sie nach **Adaptive Card Viewer**.

![Marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a>Verwendung

Wenn Sie eine JSON-Datei mit der eine Adaptive Card bearbeiten `$schema` Eigenschaft, die Sie anzeigen können, mithilfe von `Ctrl+Shift+V A`.
```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a>Optionen

Die folgende Einstellung für die Visual Studio Code ist für den AdaptiveCards Viewer verfügbar. Dies kann in den Einstellungen für Benutzer und Arbeitsbereich festgelegt werden.

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a>Beispiel für WPF-Schnellansicht
Die [WPF-Schnellansicht-Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) ermöglicht Ihnen das Visualisieren von Karten, die mithilfe von WPF-Xaml auf einem Windows-Computer.  Ein `hostconfig` Editor zum Bearbeiten und Anzeigen von Host-Konfigurationseinstellungen integriert ist. Speichern Sie diese Einstellungen als JSON, sie in das Rendering in Ihrer Anwendung verwenden.

![WPF-Schnellansicht](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a>Beispiel für WPF-ImageRender
Die [ImageRender Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) eine Karte, in eine PNG-Datei über die Befehlszeile mit WPF umwandelt. 
