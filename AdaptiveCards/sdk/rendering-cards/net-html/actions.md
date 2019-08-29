---
title: 'Aktionen: .net html SDK'
author: matthidinger
ms.author: mahiding
ms.date: 10/19/2017
ms.topic: article
ms.openlocfilehash: 99bf6121489391c207a71b45264dc68aa2c6116e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553312"
---
# <a name="actions---net-html"></a>Aktionen: .net-html

Die Karte `actions` der obersten Ebene wird als HTML `<button>`-Code dargestellt. Da es sich hierbei um eine serverseitige Bibliothek handelt, können Sie Client seitige Ereignishandler beim Drücken von Schaltflächen verknüpfen. Jeder `<button>` in der HTML-Code verfügt über Attribute, die Sie verwenden können, um das richtige Verhalten zu verknüpfen.

Einige Elemente verfügen über `selectAction` eine Eigenschaft (Container, Spalten, Bild), durch die Sie aufgerufen werden können. Wenn ein Element über einen `selectAction` verfügt, fügt der Renderer eine CSS- `ac-selectable`Klasse von zusammen mit den folgenden Attributen hinzu.

Aktionstyp | CSS-Klasse | Zusätzliche Attribute
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | `data-ac-url`(die `url` -Eigenschaft der Karte)
`Action.Submit` | `ac-action-submit` | `data-ac-data`(die `data` -Eigenschaft der Karte)
`Action.ShowCard` | `ac-action-showCard` | `data-ac-showcardid`(der `id` `<div>` der, die die innere Karte enthält)