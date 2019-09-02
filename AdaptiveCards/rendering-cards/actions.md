---
title: Aktionen
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 42ba1ca4ba2ecd508bdee2f04061293d48349aab
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553372"
---
# <a name="actions"></a>Aktionen

Aktionen werden standardmäßig als Schaltflächen auf der Karte gerendert, allerdings obliegt es deiner App, für ein ordnungsgemäßes Verhalten zu sorgen. Jedes SDK verfügt über das Äquivalent eines `OnAction`-Ereignisses, die verarbeitet werden müssen.

* **Action.OpenUrl**: Öffnet die angegebene `url`.  
* **Action.Submit**: Akzeptiert das Ergebnis der Übermittlung und sendet es an die Quelle. Wie du das Ergebnis an die Quelle der Karte sendest, liegt allein in deinem Ermessen.
* **Action.ShowCard**: Ruft ein Dialogfeld auf und rendert die untergeordnete Karte in diesem Dialogfeld. Beachte, dass du dies nur verarbeiten musst, wenn `ShowCardActionMode` auf `popup` festgelegt ist.