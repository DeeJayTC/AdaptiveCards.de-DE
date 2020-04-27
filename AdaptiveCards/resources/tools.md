---
title: Tools für adaptive Karten
author: matthidinger
ms.author: mahiding
ms.date: 03/14/2019
ms.topic: article
ms.openlocfilehash: f0c5a61d3406e1defffefc575ee0a6ec78fba93d
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "77454833"
---
# <a name="tools-and-samples"></a><span data-ttu-id="a77c0-102">Tools und Beispiele</span><span class="sxs-lookup"><span data-stu-id="a77c0-102">Tools and Samples</span></span>

## <a name="card-designer"></a><span data-ttu-id="a77c0-103">Karten-Designer</span><span class="sxs-lookup"><span data-stu-id="a77c0-103">Card Designer</span></span> 

<span data-ttu-id="a77c0-104">Benötigst du ein Tool zum Entwerfen deiner Karten?</span><span class="sxs-lookup"><span data-stu-id="a77c0-104">Need for a tool to design your cards?</span></span> <span data-ttu-id="a77c0-105">Hier ist die Lösung: der browserbasierte Designer für adaptive Karten unter [https://adaptivecards.io/designer](https://adaptivecards.io/designer).</span><span class="sxs-lookup"><span data-stu-id="a77c0-105">Look no further than the browser-based adaptive card designer at [https://adaptivecards.io/designer](https://adaptivecards.io/designer)</span></span>

<span data-ttu-id="a77c0-106">[![Screenshot des Designers](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span><span class="sxs-lookup"><span data-stu-id="a77c0-106">[![designer screenshot](media/tools/designer.jpg)](https://adaptivecards.io/designer)</span></span>

### <a name="embed-the-designer-into-your-app"></a><span data-ttu-id="a77c0-107">Einbetten des Designers in deine App</span><span class="sxs-lookup"><span data-stu-id="a77c0-107">Embed the designer into your app</span></span>

<span data-ttu-id="a77c0-108">Anstatt die Benutzer an diesen Browser zu verweisen, kannst du deine JavaScript-Bibliothek verwenden, um **den Karten-Designer direkt in deine Web-App** zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="a77c0-108">But why send your users there when you can **embed the card designer directly into your web** app using our JavaScript library.</span></span> 

<span data-ttu-id="a77c0-109">Sieh dir für den Einstieg das Paket [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) an.</span><span class="sxs-lookup"><span data-stu-id="a77c0-109">Check out the [adaptivecards-designer](https://npmjs.com/adaptivecards-designer) package to get started.</span></span>

## <a name="schema-validation"></a><span data-ttu-id="a77c0-110">Schemaüberprüfung</span><span class="sxs-lookup"><span data-stu-id="a77c0-110">Schema validation</span></span>

<span data-ttu-id="a77c0-111">Die Schemaüberprüfung ist eine leistungsstarke Methode, um das Erstellen von Karten zu vereinfachen und die Verwendung von Tools zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a77c0-111">Schema validation is a powerful way of making authoring easier and enabling tooling.</span></span>

<span data-ttu-id="a77c0-112">Wir haben eine vollständige [JSON-Schemadatei](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) bereitgestellt, um adaptive Karten in JSON zu bearbeiten und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a77c0-112">We have provided a complete [JSON Schema file](http://adaptivecards.io/schemas/1.2.0/adaptive-card.json) for editing and validating adaptive cards in json.</span></span> <span data-ttu-id="a77c0-113">Beachte, dass die Schema-URL versioniert ist. Neuere Versionen von adaptiven Karten weisen eine entsprechende URL auf.</span><span class="sxs-lookup"><span data-stu-id="a77c0-113">Note that the schema URL is versioned, newer versions of Adaptive Cards will have a corresponding URL.</span></span>

<span data-ttu-id="a77c0-114">In Visual Studio und Visual Studio Code kannst du durch Einschließen eines `$schema`-Verweises automatische IntelliSense-Funktionen erzielen.</span><span class="sxs-lookup"><span data-stu-id="a77c0-114">In Visual Studio and Visual Studio Code you can get automatic Intellisense by including a `$schema` reference.</span></span>

![Ungültig](media/tools/invalidjson1.png)

![AutoVervollständigen](media/tools/autocomplete.png)

## <a name="example"></a><span data-ttu-id="a77c0-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a77c0-117">Example</span></span>

```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

## <a name="visual-studio-code-extension"></a><span data-ttu-id="a77c0-118">Erweiterung für Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a77c0-118">Visual Studio Code Extension</span></span>

<span data-ttu-id="a77c0-119">Wir haben eine Visual Studio Code-Erweiterung erstellt, mit der du die Karte, die du bearbeitest, im Editor selbst in Echtzeit visualisieren kannst.</span><span class="sxs-lookup"><span data-stu-id="a77c0-119">We have created a Visual Studio code extension which allows you to visualize the card you are editing in real time inside the editor itself.</span></span> 

![Erweiterung](media/tools/vscode-extension.png)

<span data-ttu-id="a77c0-121">Um die Erweiterung zu installieren, öffne den Marketplace für Erweiterungen und suche nach **Adaptive Card Viewer**.</span><span class="sxs-lookup"><span data-stu-id="a77c0-121">To install, open Extensions Marketplace and search for **Adaptive Card Viewer**.</span></span>

![Marketplace](media/tools/vscode-extension-marketplace.png)

### <a name="usage"></a><span data-ttu-id="a77c0-123">Verwendungszweck</span><span class="sxs-lookup"><span data-stu-id="a77c0-123">Usage</span></span>

<span data-ttu-id="a77c0-124">Wenn du eine JSON-Datei mit einer adaptiven Karteneigenschaft `$schema` bearbeitest, kannst du das Schema mithilfe von `Ctrl+Shift+V A` anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a77c0-124">When you are editing a .json file with an Adaptive Card `$schema` property you can view by using `Ctrl+Shift+V A`.</span></span>
```json
{
    "$schema": "http://adaptivecards.io/schemas/1.2.0/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "body": []
}
```

### <a name="options"></a><span data-ttu-id="a77c0-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="a77c0-125">Options</span></span>

<span data-ttu-id="a77c0-126">Die folgende Visual Studio Code-Einstellung ist für den Adaptive Card Viewer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a77c0-126">The following Visual Studio Code setting is available for the AdaptiveCards Viewer.</span></span> <span data-ttu-id="a77c0-127">Diese kann in den Benutzer- oder Arbeitsbereichseinstellungen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a77c0-127">This can be set in User Settings or Workspace Settings.</span></span>

```js
{
    // Open or not open the preview screen automatically
    "adaptivecardsviewer.enableautopreview": true,
}
```

## <a name="wpf-visualizer-sample"></a><span data-ttu-id="a77c0-128">Beispiel: WPF-Visualisierer</span><span class="sxs-lookup"><span data-stu-id="a77c0-128">WPF Visualizer Sample</span></span>

<span data-ttu-id="a77c0-129">Mit dem [Beispielprojekt für einen WPF-Visualisierer](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) kannst du Karten mithilfe von WPF/XAML auf einem Windows-Computer visualisieren.</span><span class="sxs-lookup"><span data-stu-id="a77c0-129">The [WPF visualizer sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/WPFVisualizer) lets you visualize cards using WPF/Xaml on a Windows machine.</span></span>  <span data-ttu-id="a77c0-130">Ein `hostconfig`-Editor ist zum Bearbeiten und Anzeigen von Hostkonfigurationseinstellungen integriert.</span><span class="sxs-lookup"><span data-stu-id="a77c0-130">A `hostconfig` editor is built in for editing and viewing host config settings.</span></span> <span data-ttu-id="a77c0-131">Speichere diese Einstellungen als JSON, um sie zum Rendern in deiner Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a77c0-131">Save these settings as a JSON to use them in rendering in your application.</span></span>

![WPF-Visualisierer](media/tools/wpfvisualizer.png)

## <a name="wpf-imagerender-sample"></a><span data-ttu-id="a77c0-133">Beispiel: WPF ImageRender</span><span class="sxs-lookup"><span data-stu-id="a77c0-133">WPF ImageRender Sample</span></span>

<span data-ttu-id="a77c0-134">Das [ImageRender-Beispielprojekt](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) wandelt jede Karte über die Befehlszeile mithilfe von WPF in eine PNG-Datei um.</span><span class="sxs-lookup"><span data-stu-id="a77c0-134">The [ImageRender sample project](https://github.com/Microsoft/AdaptiveCards/tree/master/source/dotnet/Samples/AdaptiveCards.Sample.ImageRender) turns any card into a PNG from the command line using WPF.</span></span> 
