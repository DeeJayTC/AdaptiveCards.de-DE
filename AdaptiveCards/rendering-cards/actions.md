---
title: Aktionen
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 34283b52f0c4902c71ea33634676832c7dfec5c9
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "77454943"
---
# <a name="actions"></a>Aktionen

Aktionen werden standardmäßig als Schaltflächen auf der Karte gerendert, allerdings obliegt es deiner App, für ein ordnungsgemäßes Verhalten zu sorgen. Jedes SDK verfügt über das Äquivalent eines `OnAction`-Ereignisses, die verarbeitet werden müssen.

* **Action.OpenUrl**: Öffnet die angegebene `url`.  
* **Action.Submit**: Akzeptiert das Ergebnis der Übermittlung und sendet es an die Quelle. Wie du das Ergebnis an die Quelle der Karte sendest, liegt allein in deinem Ermessen.
* **Action.ShowCard**: Ruft ein Dialogfeld auf und rendert die untergeordnete Karte in diesem Dialogfeld. Beachte, dass du dies nur verarbeiten musst, wenn `ShowCardActionMode` auf `popup` festgelegt ist.