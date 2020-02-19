---
title: 'Aktionen: .net html SDK'
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: f577c0bab73e2bd1f75bb22dd7a41a7dbfd63307
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454573"
---
# <a name="actions---net-html"></a>Aktionen: .net-html

Karten `actions` der obersten Ebene werden als HTML-`<button>`dargestellt. Da es sich hierbei um eine serverseitige Bibliothek handelt, können Sie Client seitige Ereignishandler beim Drücken von Schaltflächen verknüpfen. Jede `<button>` in HTML verfügt über Attribute, die Sie verwenden können, um das richtige Verhalten zu verknüpfen.

Einige Elemente verfügen über eine `selectAction`-Eigenschaft (Container, Spalten, Image), mit der Sie aufgerufen werden können. Wenn ein Element einen `selectAction` hat der Renderer eine CSS-Klasse von `ac-selectable`zusammen mit den folgenden Attributen hinzugefügt.

Aktionstyp | CSS-Klasse | Zusätzliche Attribute
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | `data-ac-url` (die `url`-Eigenschaft der Karte)
`Action.Submit` | `ac-action-submit` | `data-ac-data` (die `data`-Eigenschaft der Karte)
`Action.ShowCard` | `ac-action-showCard` | `data-ac-showcardid` (die `id` der `<div>`, die die innere Karte enthält)