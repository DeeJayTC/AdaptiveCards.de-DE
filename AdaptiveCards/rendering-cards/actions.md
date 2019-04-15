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
# <a name="actions"></a>Aktionen

Standardmäßig werden die Aktionen als Schaltflächen auf der Karte gerendert, aber es liegt an Ihre app so zu machen, die das erwartete Verhalten. Jedes SDK verfügt über das Äquivalent einer `OnAction` -Ereignis, das Sie behandeln müssen.

* **Action.OpenUrl** – öffnen Sie das angegebene `url`.  
* **Action.Submit** – nutzen Sie das Ergebnis der Sendevorgang und senden Sie sie an der Quelle. Wie Sie es an der Quelle der Karte senden ist völlig Ihnen überlassen.
* **Action.ShowCard** : Ruft ein Dialogfeld und rendert die untergeordneten Karte in diesem Dialogfeld. Beachten Sie, dass Sie nur diesen, wenn behandeln müssen `ShowCardActionMode` nastaven NA hodnotu `popup`.