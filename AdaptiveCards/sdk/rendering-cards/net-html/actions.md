---
title: Aktionen – HTML-SDK für .NET
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
# <a name="actions---net-html"></a>Aktionen – .NET HTML

Der obersten Ebene Karte `actions` als HTML rendert `<button>`. Da es sich um eine serverseitige-Bibliothek, die es liegt an Ihnen handelt, um clientseitige-Ereignishandler zu verknüpfen, wenn die Taste gedrückt werden. Jede `<button>` im HTML-Attribute, die Sie verwenden können, müssen das richtige Verhalten verknüpfen.

Einige Elemente haben eine `selectAction` Eigenschaft (Spalten-Container-Image), wodurch sie aufrufbaren. Wenn ein Element verfügt über eine `selectAction` der Renderer Fügt eine CSS-Klasse von `ac-selectable`, zusammen mit der folgenden Attribute.

Aktionstyp | CSS-Klasse | Zusätzliche Attribute
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | `data-ac-url` (die `url` Eigenschaft von der Karte)
`Action.Submit` | `ac-action-submit` | `data-ac-data` (die `data` Eigenschaft von der Karte)
`Action.ShowCard` | `ac-action-showCard` | `data-ac-showcardid` (die `id` von der `<div>` , enthält die innere-Karte)