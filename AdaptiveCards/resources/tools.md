---
title: Tools für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: f0c5a61d3406e1defffefc575ee0a6ec78fba93d
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454833"
---
# <a name="tools-and-samples"></a>Tools und Beispiele

## <a name="card-designer"></a>Karten-Designer 

Benötigst du ein Tool zum Entwerfen deiner Karten? Hier ist die Lösung: der browserbasierte Designer für adaptive Karten unter [https://adaptivecards.io/designer](https://adaptivecards.io/designer).

[![Screenshot des Designers](media/tools/designer.jpg)](https://adaptivecards.io/designer)

### <a name="embed-the-designer-into-your-app"></a>Einbetten des Designers in deine App

Anstatt die Benutzer an diesen Browser zu verweisen, kannst du deine JavaScript-Bibliothek verwenden, um **den Karten-Designer direkt in deine Web-App** zu integrieren. 

Sieh dir für den Einstieg das Paket [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) an.

## <a name="schema-validation"></a>Schemaüberprüfung

Die Schemaüberprüfung ist eine leistungsstarke Methode, um das Erstellen von Karten zu vereinfachen und die Verwendung von Tools zu ermöglichen.

Wir haben eine vollständige [JSON-Schemadatei](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) bereitgestellt, um adaptive Karten in JSON zu bearbeiten und zu überprüfen. Beachte, dass die Schema-URL versioniert ist. Neuere Versionen von adaptiven Karten weisen eine entsprechende URL auf.

In Visual Studio und Visual Studio Code kannst du durch Einschließen eines `$schema`-Verweises automatische IntelliSense-Funktionen erzielen.

![Ungültig](media/tools/invalidjson1.png)

![AutoVervollständigen](media/tools/autocomplete.png)

## <a name="example"></a>Beispiel

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a>Erweiterung für Visual Studio Code

Wir haben eine Visual Studio Code-Erweiterung erstellt, mit der du die Karte, die du bearbeitest, im Editor selbst in Echtzeit visualisieren kannst. 

![Erweiterung](media/tools/vscode-extension.png)

Um die Erweiterung zu installieren, öffne den Marketplace für Erweiterungen und suche nach **Adaptive Card Viewer**.

![Marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a>Usage

Wenn du eine JSON-Datei mit einer adaptiven Karteneigenschaft `$schema` bearbeitest, kannst du das Schema mithilfe von `Ctrl+Shift+V A` anzeigen.
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a>Optionen

Die folgende Visual Studio Code-Einstellung ist für den Adaptive Card Viewer verfügbar. Diese kann in den Benutzer- oder Arbeitsbereichseinstellungen festgelegt werden.

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a>Beispiel: WPF-Visualisierer

Mit dem [Beispielprojekt für einen WPF-Visualisierer](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) kannst du Karten mithilfe von WPF/XAML auf einem Windows-Computer visualisieren.  Ein `hostconfig`-Editor ist zum Bearbeiten und Anzeigen von Hostkonfigurationseinstellungen integriert. Speichere diese Einstellungen als JSON, um sie zum Rendern in deiner Anwendung zu verwenden.

![WPF-Visualisierer](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a>Beispiel: WPF ImageRender

Das [ImageRender-Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) wandelt jede Karte über die Befehlszeile mithilfe von WPF in eine PNG-Datei um. 
