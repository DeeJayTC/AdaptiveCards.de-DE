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
# <a name="card-designer"></a><span data-ttu-id="c20ff-102">Karten-Designer</span><span class="sxs-lookup"><span data-stu-id="c20ff-102">Card Designer</span></span> 

<span data-ttu-id="c20ff-103">Benötigen Sie für ein Tool zum Entwerfen Ihrer Karten?</span><span class="sxs-lookup"><span data-stu-id="c20ff-103">Need for a tool to design your cards?</span></span> <span data-ttu-id="c20ff-104">Finden Sie den Designer adaptive Card browserbasierte und in [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="c20ff-104">Look no further than the browser-based adaptive card designer at [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span></span>

<span data-ttu-id="c20ff-105">[![Designer-screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="c20ff-105">[![designer screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span></span>

## <a name="embed-the-designer-into-your-app"></a><span data-ttu-id="c20ff-106">Den Designer in Ihre Anwendung einbetten.</span><span class="sxs-lookup"><span data-stu-id="c20ff-106">Embed the designer into your app</span></span>

<span data-ttu-id="c20ff-107">Aber warum es Ihren Benutzern zu senden, wenn möglich **einbetten den Karte Designer direkt in Ihrer Web** -app mit unseren JavaScript-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="c20ff-107">But why send your users there when you can **embed the card designer directly into your web** app using our JavaScript library.</span></span> 

<span data-ttu-id="c20ff-108">Sehen Sie sich die [Adaptivecards-Designer](https://npmjs.com/adaptivecards-designer) Paket, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c20ff-108">Check out the [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) package to get started.</span></span>

# <a name="schema-validation"></a><span data-ttu-id="c20ff-109">Schema-Validierung</span><span class="sxs-lookup"><span data-stu-id="c20ff-109">Schema validation</span></span>

<span data-ttu-id="c20ff-110">Schema-Validierung ist eine leistungsfähige Möglichkeit einfacher erstellen und aktivieren die Tools zu machen.</span><span class="sxs-lookup"><span data-stu-id="c20ff-110">Schema validation is a powerful way of making authoring easier and enabling tooling.</span></span>

## <a name="json-schema"></a><span data-ttu-id="c20ff-111">JSON-Schema</span><span class="sxs-lookup"><span data-stu-id="c20ff-111">JSON Schema</span></span>
<span data-ttu-id="c20ff-112">Wir haben eine vollständige bereitgestellt [JSON-Schemadatei](http://adaptivecards.io/schemas/adaptive-card.json) zum Bearbeiten und Validieren mit adaptive Cards im JSON-Format.</span><span class="sxs-lookup"><span data-stu-id="c20ff-112">We have provided a complete [JSON Schema file](http://adaptivecards.io/schemas/adaptive-card.json) for editing and validating adaptive cards in json.</span></span>

<span data-ttu-id="c20ff-113">Sie können automatische Intellisense in Visual Studio und Visual Studio Code abrufen, mit einem `$schema` Verweis.</span><span class="sxs-lookup"><span data-stu-id="c20ff-113">In Visual Studio and Visual Studio Code you can get automatic Intellisense by including a `$schema` reference.</span></span>

![Ungültige](media/tools/invalidjson1.png)

![AutoVervollständigen-Funktion](media/tools/autocomplete.png)

### <a name="example"></a><span data-ttu-id="c20ff-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c20ff-116">Example</span></span>

```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "0.5",
    "body": []
}
```

# <a name="tools-and-samples"></a><span data-ttu-id="c20ff-117">Tools und Beispiele</span><span class="sxs-lookup"><span data-stu-id="c20ff-117">Tools and samples</span></span>
<span data-ttu-id="c20ff-118">Es gibt einige Tools und Beispiele in der ursprünglichen Struktur nützliche Verweise als auch nützliche Tools sind.</span><span class="sxs-lookup"><span data-stu-id="c20ff-118">There are some tools and samples in the source tree which are useful references as well as useful tools.</span></span>

## <a name="visual-studio-code-extension"></a><span data-ttu-id="c20ff-119">Visual Studio Code-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="c20ff-119">Visual Studio Code Extension</span></span>
<span data-ttu-id="c20ff-120">Wir haben Visual Studio Code-Erweiterung erstellt, die Sie die Karte visuell darstellen, die Sie in Echtzeit in den Editor bearbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="c20ff-120">We have created a Visual Studio code extension which allows you to visualize the card you are editing in real time inside the editor itself.</span></span> 

![Erweiterung](media/tools/vscode-extension.png)

<span data-ttu-id="c20ff-122">Klicken Sie zum Installieren Erweiterungen Marketplace zu öffnen, und suchen Sie nach **Adaptive Card Viewer**.</span><span class="sxs-lookup"><span data-stu-id="c20ff-122">To install, open Extensions Marketplace and search for **Adaptive Card Viewer**.</span></span>

![Marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a><span data-ttu-id="c20ff-124">Verwendung</span><span class="sxs-lookup"><span data-stu-id="c20ff-124">Usage</span></span>

<span data-ttu-id="c20ff-125">Wenn Sie eine JSON-Datei mit der eine Adaptive Card bearbeiten `$schema` Eigenschaft, die Sie anzeigen können, mithilfe von `Ctrl+Shift+V A`.</span><span class="sxs-lookup"><span data-stu-id="c20ff-125">When you are editing a .json file with an Adaptive Card `$schema` property you can view by using `Ctrl+Shift+V A`.</span></span>
```json
{
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a><span data-ttu-id="c20ff-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="c20ff-126">Options</span></span>

<span data-ttu-id="c20ff-127">Die folgende Einstellung für die Visual Studio Code ist für den AdaptiveCards Viewer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c20ff-127">The following Visual Studio Code setting is available for the AdaptiveCards Viewer.</span></span> <span data-ttu-id="c20ff-128">Dies kann in den Einstellungen für Benutzer und Arbeitsbereich festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c20ff-128">This can be set in User Settings or Workspace Settings.</span></span>

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="c20ff-129">Beispiel für WPF-Schnellansicht</span><span class="sxs-lookup"><span data-stu-id="c20ff-129">WPF Visualizer Sample</span></span>
<span data-ttu-id="c20ff-130">Die [WPF-Schnellansicht-Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) ermöglicht Ihnen das Visualisieren von Karten, die mithilfe von WPF-Xaml auf einem Windows-Computer.</span><span class="sxs-lookup"><span data-stu-id="c20ff-130">The [WPF visualizer sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF/Xaml on a Windows machine.</span></span>  <span data-ttu-id="c20ff-131">Ein `hostconfig` Editor zum Bearbeiten und Anzeigen von Host-Konfigurationseinstellungen integriert ist.</span><span class="sxs-lookup"><span data-stu-id="c20ff-131">A `hostconfig` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="c20ff-132">Speichern Sie diese Einstellungen als JSON, sie in das Rendering in Ihrer Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c20ff-132">Save these settings as a JSON to use them in rendering in your application.</span></span>

![WPF-Schnellansicht](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a><span data-ttu-id="c20ff-134">Beispiel für WPF-ImageRender</span><span class="sxs-lookup"><span data-stu-id="c20ff-134">WPF ImageRender Sample</span></span>
<span data-ttu-id="c20ff-135">Die [ImageRender Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) eine Karte, in eine PNG-Datei über die Befehlszeile mit WPF umwandelt.</span><span class="sxs-lookup"><span data-stu-id="c20ff-135">The [ImageRender sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) turns any card into a PNG from the command line using WPF.</span></span> 
