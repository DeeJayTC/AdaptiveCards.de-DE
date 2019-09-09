---
title: JavaScript-SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 4a6030dda12ab8d9a1e5c387cec63d45e84660d8
ms.sourcegitcommit: aa044167fd0b32b485ea2ce014afcf0b332bf1a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2019
ms.locfileid: "69529844"
---
# <a name="getting-started---javascript"></a><span data-ttu-id="68e77-102">Getting Started (JavaScript)</span><span class="sxs-lookup"><span data-stu-id="68e77-102">Getting started - JavaScript</span></span>

<span data-ttu-id="68e77-103">Wie auf der Seite mit den ersten Schritten beschrieben, handelt es sich bei einer adaptiven [Karte um ein](../../../authoring-cards/getting-started.md) JSON-serialisiertes Karten Objektmodell.</span><span class="sxs-lookup"><span data-stu-id="68e77-103">As we described in [Getting Started](../../../authoring-cards/getting-started.md) page, an Adaptive Card is a JSON-serialized card object model.</span></span> <span data-ttu-id="68e77-104">Dies ist ein JavaScript-SDK zum Erstellen von Client seitigem HTML im Browser.</span><span class="sxs-lookup"><span data-stu-id="68e77-104">This is a JavaScript SDK for generating client-side HTML in the browser.</span></span>

## <a name="install"></a><span data-ttu-id="68e77-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="68e77-105">Install</span></span>

### <a name="node"></a><span data-ttu-id="68e77-106">Knoten</span><span class="sxs-lookup"><span data-stu-id="68e77-106">Node</span></span>

<span data-ttu-id="68e77-107">[![npm-Installation](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span><span class="sxs-lookup"><span data-stu-id="68e77-107">[![npm install](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)</span></span>

```console
npm install adaptivecards
```

### <a name="cdn"></a><span data-ttu-id="68e77-108">CDN</span><span class="sxs-lookup"><span data-stu-id="68e77-108">CDN</span></span>

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a><span data-ttu-id="68e77-109">Verwendung</span><span class="sxs-lookup"><span data-stu-id="68e77-109">Usage</span></span>

### <a name="import-the-module"></a><span data-ttu-id="68e77-110">Importieren des Moduls</span><span class="sxs-lookup"><span data-stu-id="68e77-110">Import the module</span></span>

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a><span data-ttu-id="68e77-111">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="68e77-111">Next steps</span></span>

<span data-ttu-id="68e77-112">Informationen zu den nächsten Schritten findest du unter [Rendern einer Karte](render-a-card.md).</span><span class="sxs-lookup"><span data-stu-id="68e77-112">See [Render a card](render-a-card.md) for the next steps!</span></span>
