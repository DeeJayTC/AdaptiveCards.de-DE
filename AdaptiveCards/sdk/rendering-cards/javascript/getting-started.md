---
title: JavaScript-SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 9684b96bba5168a1f07549468274ce5d74c01820
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553462"
---
# <a name="getting-started---javascript"></a><span data-ttu-id="f9dc3-102">Erste Schritte – JavaScript</span><span class="sxs-lookup"><span data-stu-id="f9dc3-102">Getting started - JavaScript</span></span>

<span data-ttu-id="f9dc3-103">Wie wir im beschrieben [Einstieg](../../../authoring-cards/getting-started.md) Seite eine Adaptive Card ist ein JSON-serialisierten Karte-Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="f9dc3-104">Dies ist eine JavaScript-SDK für die Generierung der clientseitigen HTML im Browser.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-104">This is a JavaScript SDK for generating client-side HTML in the browser.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9dc3-105">**Wichtige Änderungen gegenüber v0.5**</span><span class="sxs-lookup"><span data-stu-id="f9dc3-105">**Breaking changes from v0.5**</span></span>
> 
> 1. <span data-ttu-id="f9dc3-106">Paket umbenannt `microsoft-adaptivecards` auf `adaptivecards`</span><span class="sxs-lookup"><span data-stu-id="f9dc3-106">Package renamed from `microsoft-adaptivecards` to `adaptivecards`</span></span>
> 1. <span data-ttu-id="f9dc3-107">Die statische `AdaptiveCards.setHostConfig()` wurde in einen Instanzmember `AdaptiveCard`.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-107">The static `AdaptiveCards.setHostConfig()` has been moved to an instance member of `AdaptiveCard`.</span></span> <span data-ttu-id="f9dc3-108">E.g., `myCard.hostConfig = {}`</span><span class="sxs-lookup"><span data-stu-id="f9dc3-108">E.g., `myCard.hostConfig = {}`</span></span> 
> 1. <span data-ttu-id="f9dc3-109">`HostConfig` ist aufgetreten, obwohl verschiedene umbenennen und verschieben.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-109">`HostConfig` has gone though various renames and moves.</span></span> <span data-ttu-id="f9dc3-110">Finden Sie unter den [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) Host-Konfiguration für die aktuelle Struktur</span><span class="sxs-lookup"><span data-stu-id="f9dc3-110">See the [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) Host Config for current structure</span></span>
> 1. <span data-ttu-id="f9dc3-111">Es wurden außerdem einige schemaänderungen in der Vorschau v0.5 sind [die nachfolgend beschrieben](https://github.com/Microsoft/AdaptiveCards/pull/633)</span><span class="sxs-lookup"><span data-stu-id="f9dc3-111">There have also been some schema changes from the v0.5 preview, which are [outlined here](https://github.com/Microsoft/AdaptiveCards/pull/633)</span></span>
> 1. <span data-ttu-id="f9dc3-112">Die statische `renderCard()` wie redundante mit Methoden der Klasse-Funktion wurde entfernt.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-112">The static `renderCard()` function was removed as it was redundant with the class methods.</span></span> <span data-ttu-id="f9dc3-113">Verwendung `adaptiveCard.render()` wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-113">Use `adaptiveCard.render()` as described below.</span></span> 


## <a name="install"></a><span data-ttu-id="f9dc3-114">Installieren</span><span class="sxs-lookup"><span data-stu-id="f9dc3-114">Install</span></span>

### <a name="node"></a><span data-ttu-id="f9dc3-115">Knoten</span><span class="sxs-lookup"><span data-stu-id="f9dc3-115">Node</span></span>

<span data-ttu-id="f9dc3-116">[![Npm-Installation](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span><span class="sxs-lookup"><span data-stu-id="f9dc3-116">[![npm install](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span></span>

```console
npm install adaptivecards --save
```

### <a name="cdn"></a><span data-ttu-id="f9dc3-117">CDN</span><span class="sxs-lookup"><span data-stu-id="f9dc3-117">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a><span data-ttu-id="f9dc3-118">Verwendung</span><span class="sxs-lookup"><span data-stu-id="f9dc3-118">Usage</span></span>

### <a name="import-the-module"></a><span data-ttu-id="f9dc3-119">Importieren Sie das Modul</span><span class="sxs-lookup"><span data-stu-id="f9dc3-119">Import the module</span></span>

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a><span data-ttu-id="f9dc3-120">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f9dc3-120">Next steps</span></span>

<span data-ttu-id="f9dc3-121">Finden Sie unter [rendern eine Karte](render-a-card.md) für die nächsten Schritte.</span><span class="sxs-lookup"><span data-stu-id="f9dc3-121">See [Render a card](render-a-card.md) for the next steps!</span></span>
