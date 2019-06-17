---
title: Mit Adaptive Cards-Tools
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: ad520693224509deaf0ea1c2cd6a837089dbf2d5
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137983"
---
# <a name="tools-and-samples"></a><span data-ttu-id="93d5d-102">Tools und Beispielen</span><span class="sxs-lookup"><span data-stu-id="93d5d-102">Tools and Samples</span></span>

## <a name="card-designer"></a><span data-ttu-id="93d5d-103">Karten-Designer</span><span class="sxs-lookup"><span data-stu-id="93d5d-103">Card Designer</span></span> 

<span data-ttu-id="93d5d-104">Benötigen Sie für ein Tool zum Entwerfen Ihrer Karten?</span><span class="sxs-lookup"><span data-stu-id="93d5d-104">Need for a tool to design your cards?</span></span> <span data-ttu-id="93d5d-105">Finden Sie den Designer adaptive Card browserbasierte und in [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="93d5d-105">Look no further than the browser-based adaptive card designer at [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span></span>

<span data-ttu-id="93d5d-106">[![Designer-screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="93d5d-106">[![designer screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span></span>

### <a name="embed-the-designer-into-your-app"></a><span data-ttu-id="93d5d-107">Den Designer in Ihre Anwendung einbetten.</span><span class="sxs-lookup"><span data-stu-id="93d5d-107">Embed the designer into your app</span></span>

<span data-ttu-id="93d5d-108">Aber warum es Ihren Benutzern zu senden, wenn möglich **einbetten den Karte Designer direkt in Ihrer Web** -app mit unseren JavaScript-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="93d5d-108">But why send your users there when you can **embed the card designer directly into your web** app using our JavaScript library.</span></span> 

<span data-ttu-id="93d5d-109">Sehen Sie sich die [Adaptivecards-Designer](https://npmjs.com/adaptivecards-designer) Paket, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="93d5d-109">Check out the [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) package to get started.</span></span>

## <a name="schema-validation"></a><span data-ttu-id="93d5d-110">Schema-Validierung</span><span class="sxs-lookup"><span data-stu-id="93d5d-110">Schema validation</span></span>

<span data-ttu-id="93d5d-111">Schema-Validierung ist eine leistungsfähige Möglichkeit einfacher erstellen und aktivieren die Tools zu machen.</span><span class="sxs-lookup"><span data-stu-id="93d5d-111">Schema validation is a powerful way of making authoring easier and enabling tooling.</span></span>

<span data-ttu-id="93d5d-112">Wir haben eine vollständige bereitgestellt [JSON-Schemadatei](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) zum Bearbeiten und Validieren mit adaptive Cards im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="93d5d-112">We have provided a complete [JSON Schema file](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) for editing and validating adaptive cards in json.</span></span> <span data-ttu-id="93d5d-113">Beachten Sie, dass die Schema-URL mit Versionsangabe, neuere Versionen mit Adaptive Cards ist, wird eine entsprechende URL haben.</span><span class="sxs-lookup"><span data-stu-id="93d5d-113">Note that the schema URL is versioned, newer versions of Adaptive Cards will have a corresponding URL.</span></span>

<span data-ttu-id="93d5d-114">Sie können automatische Intellisense in Visual Studio und Visual Studio Code abrufen, mit einem `$schema` Verweis.</span><span class="sxs-lookup"><span data-stu-id="93d5d-114">In Visual Studio and Visual Studio Code you can get automatic Intellisense by including a `$schema` reference.</span></span>

![Ungültige](media/tools/invalidjson1.png)

![AutoVervollständigen-Funktion](media/tools/autocomplete.png)

## <a name="example"></a><span data-ttu-id="93d5d-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93d5d-117">Example</span></span>

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a><span data-ttu-id="93d5d-118">Visual Studio Code-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="93d5d-118">Visual Studio Code Extension</span></span>

<span data-ttu-id="93d5d-119">Wir haben Visual Studio Code-Erweiterung erstellt, die Sie die Karte visuell darstellen, die Sie in Echtzeit in den Editor bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="93d5d-119">We have created a Visual Studio code extension which allows you to visualize the card you are editing in real time inside the editor itself.</span></span> 

![Erweiterung](media/tools/vscode-extension.png)

<span data-ttu-id="93d5d-121">Klicken Sie zum Installieren Erweiterungen Marketplace zu öffnen, und suchen Sie nach **Adaptive Card Viewer**.</span><span class="sxs-lookup"><span data-stu-id="93d5d-121">To install, open Extensions Marketplace and search for **Adaptive Card Viewer**.</span></span>

![Marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a><span data-ttu-id="93d5d-123">Verwendung</span><span class="sxs-lookup"><span data-stu-id="93d5d-123">Usage</span></span>

<span data-ttu-id="93d5d-124">Wenn Sie eine JSON-Datei mit der eine Adaptive Card bearbeiten `$schema` Eigenschaft, die Sie anzeigen können, mithilfe von `Ctrl+Shift+V A`.</span><span class="sxs-lookup"><span data-stu-id="93d5d-124">When you are editing a .json file with an Adaptive Card `$schema` property you can view by using `Ctrl+Shift+V A`.</span></span>
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a><span data-ttu-id="93d5d-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="93d5d-125">Options</span></span>

<span data-ttu-id="93d5d-126">Die folgende Einstellung für die Visual Studio Code ist für den AdaptiveCards Viewer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="93d5d-126">The following Visual Studio Code setting is available for the AdaptiveCards Viewer.</span></span> <span data-ttu-id="93d5d-127">Dies kann in den Einstellungen für Benutzer und Arbeitsbereich festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="93d5d-127">This can be set in User Settings or Workspace Settings.</span></span>

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="93d5d-128">Beispiel für WPF-Schnellansicht</span><span class="sxs-lookup"><span data-stu-id="93d5d-128">WPF Visualizer Sample</span></span>

<span data-ttu-id="93d5d-129">Die [WPF-Schnellansicht-Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) ermöglicht Ihnen das Visualisieren von Karten, die mithilfe von WPF-Xaml auf einem Windows-Computer.</span><span class="sxs-lookup"><span data-stu-id="93d5d-129">The [WPF visualizer sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF/Xaml on a Windows machine.</span></span>  <span data-ttu-id="93d5d-130">Ein `hostconfig` Editor zum Bearbeiten und Anzeigen von Host-Konfigurationseinstellungen integriert ist.</span><span class="sxs-lookup"><span data-stu-id="93d5d-130">A `hostconfig` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="93d5d-131">Speichern Sie diese Einstellungen als JSON, sie in das Rendering in Ihrer Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="93d5d-131">Save these settings as a JSON to use them in rendering in your application.</span></span>

![WPF-Schnellansicht](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a><span data-ttu-id="93d5d-133">Beispiel für WPF-ImageRender</span><span class="sxs-lookup"><span data-stu-id="93d5d-133">WPF ImageRender Sample</span></span>

<span data-ttu-id="93d5d-134">Die [ImageRender Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) eine Karte, in eine PNG-Datei über die Befehlszeile mit WPF umwandelt.</span><span class="sxs-lookup"><span data-stu-id="93d5d-134">The [ImageRender sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) turns any card into a PNG from the command line using WPF.</span></span> 
