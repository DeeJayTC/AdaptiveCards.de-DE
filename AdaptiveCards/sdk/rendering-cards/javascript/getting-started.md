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
# <a name="getting-started---javascript"></a>Erste Schritte – JavaScript

Wie wir im beschrieben [Einstieg](../../../authoring-cards/getting-started.md) Seite eine Adaptive Card ist ein JSON-serialisierten Karte-Objektmodell. Dies ist eine JavaScript-SDK für die Generierung der clientseitigen HTML im Browser.

> [!IMPORTANT]
> **Wichtige Änderungen gegenüber v0.5**
> 
> 1. Paket umbenannt `microsoft-adaptivecards` auf `adaptivecards`
> 1. Die statische `AdaptiveCards.setHostConfig()` wurde in einen Instanzmember `AdaptiveCard`. E.g., `myCard.hostConfig = {}` 
> 1. `HostConfig` ist aufgetreten, obwohl verschiedene umbenennen und verschieben. Finden Sie unter den [sample.json](https://github.com/Microsoft/AdaptiveCards/blob/master/samples/HostConfig/sample.json) Host-Konfiguration für die aktuelle Struktur
> 1. Es wurden außerdem einige schemaänderungen in der Vorschau v0.5 sind [die nachfolgend beschrieben](https://github.com/Microsoft/AdaptiveCards/pull/633)
> 1. Die statische `renderCard()` wie redundante mit Methoden der Klasse-Funktion wurde entfernt. Verwendung `adaptiveCard.render()` wie unten beschrieben. 


## <a name="install"></a>Installieren

### <a name="node"></a>Knoten

[![Npm-Installation](https://img.shields.io/npm/v/adaptivecards.svg)](https://www.npmjs.com/package/adaptivecards)

```console
npm install adaptivecards --save
```

### <a name="cdn"></a>CDN

```html
<script src="https://unpkg.com/adaptivecards/dist/adaptivecards.js"></script>
```

## <a name="usage"></a>Verwendung

### <a name="import-the-module"></a>Importieren Sie das Modul

```js
// import the module
import * as AdaptiveCards from "adaptivecards";

// or require it
var AdaptiveCards = require("adaptivecards");

// or use the global variable if loaded from CDN
AdaptiveCards.renderCard(...);
```

## <a name="next-steps"></a>Nächste Schritte

Finden Sie unter [rendern eine Karte](render-a-card.md) für die nächsten Schritte.
