---
title: Aktionen
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 42ba1ca4ba2ecd508bdee2f04061293d48349aab
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553372"
---
# <a name="actions"></a><span data-ttu-id="28f09-102">Aktionen</span><span class="sxs-lookup"><span data-stu-id="28f09-102">Actions</span></span>

<span data-ttu-id="28f09-103">Standardmäßig werden die Aktionen als Schaltflächen auf der Karte gerendert, aber es liegt an Ihre app so zu machen, die das erwartete Verhalten.</span><span class="sxs-lookup"><span data-stu-id="28f09-103">By default, the actions will render as buttons on the card, but it's up to your app to make them behave as you expect.</span></span> <span data-ttu-id="28f09-104">Jedes SDK verfügt über das Äquivalent einer `OnAction` -Ereignis, das Sie behandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="28f09-104">Each SDK has the equivalent of an `OnAction` event that you must handle.</span></span>

* <span data-ttu-id="28f09-105">**Action.OpenUrl** – öffnen Sie das angegebene `url`.</span><span class="sxs-lookup"><span data-stu-id="28f09-105">**Action.OpenUrl** - open the specified `url`.</span></span>  
* <span data-ttu-id="28f09-106">**Action.Submit** – nutzen Sie das Ergebnis der Sendevorgang und senden Sie sie an der Quelle.</span><span class="sxs-lookup"><span data-stu-id="28f09-106">**Action.Submit** - take the result of the submit and send it to the source.</span></span> <span data-ttu-id="28f09-107">Wie Sie es an der Quelle der Karte senden ist völlig Ihnen überlassen.</span><span class="sxs-lookup"><span data-stu-id="28f09-107">How you send it to the source of the card is entirely up to you.</span></span>
* <span data-ttu-id="28f09-108">**Action.ShowCard** : Ruft ein Dialogfeld und rendert die untergeordneten Karte in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="28f09-108">**Action.ShowCard** - invokes a dialog and renders the sub-card into that dialog.</span></span> <span data-ttu-id="28f09-109">Beachten Sie, dass Sie nur diesen, wenn behandeln müssen `ShowCardActionMode` nastaven NA hodnotu `popup`.</span><span class="sxs-lookup"><span data-stu-id="28f09-109">Note that you only need to handle this if `ShowCardActionMode` is set to `popup`.</span></span>