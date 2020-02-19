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
# <a name="actions---net-html"></a><span data-ttu-id="f6175-102">Aktionen: .net-html</span><span class="sxs-lookup"><span data-stu-id="f6175-102">Actions - .NET HTML</span></span>

<span data-ttu-id="f6175-103">Karten `actions` der obersten Ebene werden als HTML-`<button>`dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f6175-103">Top-level card `actions` will render as an HTML `<button>`.</span></span> <span data-ttu-id="f6175-104">Da es sich hierbei um eine serverseitige Bibliothek handelt, können Sie Client seitige Ereignishandler beim Drücken von Schaltflächen verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="f6175-104">Since this is a server-side library it's up to you to wire up client-side event handlers when buttons are pressed.</span></span> <span data-ttu-id="f6175-105">Jede `<button>` in HTML verfügt über Attribute, die Sie verwenden können, um das richtige Verhalten zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="f6175-105">Each `<button>` in the HTML will have attributes that you can use to wire up the proper behavior.</span></span>

<span data-ttu-id="f6175-106">Einige Elemente verfügen über eine `selectAction`-Eigenschaft (Container, Spalten, Image), mit der Sie aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="f6175-106">Some elements have a `selectAction` property (Container, Columns, Image) which makes them invokable.</span></span> <span data-ttu-id="f6175-107">Wenn ein Element einen `selectAction` hat der Renderer eine CSS-Klasse von `ac-selectable`zusammen mit den folgenden Attributen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6175-107">If an element has a `selectAction` the renderer will add a CSS class of `ac-selectable`, along with the below attributes.</span></span>

<span data-ttu-id="f6175-108">Aktionstyp</span><span class="sxs-lookup"><span data-stu-id="f6175-108">Action Type</span></span> | <span data-ttu-id="f6175-109">CSS-Klasse</span><span class="sxs-lookup"><span data-stu-id="f6175-109">CSS class</span></span> | <span data-ttu-id="f6175-110">Zusätzliche Attribute</span><span class="sxs-lookup"><span data-stu-id="f6175-110">Additional attributes</span></span>
---|---|---
`Action.OpenUrl` | `ac-action-openUrl` | <span data-ttu-id="f6175-111">`data-ac-url` (die `url`-Eigenschaft der Karte)</span><span class="sxs-lookup"><span data-stu-id="f6175-111">`data-ac-url` (the `url` property from the card)</span></span>
`Action.Submit` | `ac-action-submit` | <span data-ttu-id="f6175-112">`data-ac-data` (die `data`-Eigenschaft der Karte)</span><span class="sxs-lookup"><span data-stu-id="f6175-112">`data-ac-data` (the `data` property from the card)</span></span>
`Action.ShowCard` | `ac-action-showCard` | <span data-ttu-id="f6175-113">`data-ac-showcardid` (die `id` der `<div>`, die die innere Karte enthält)</span><span class="sxs-lookup"><span data-stu-id="f6175-113">`data-ac-showcardid` (the `id` of the `<div>` containing the inner card)</span></span>