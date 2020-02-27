---
title: Aktionen
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 34283b52f0c4902c71ea33634676832c7dfec5c9
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454943"
---
# <a name="actions"></a><span data-ttu-id="18e77-102">Aktionen</span><span class="sxs-lookup"><span data-stu-id="18e77-102">Actions</span></span>

<span data-ttu-id="18e77-103">Aktionen werden standardmäßig als Schaltflächen auf der Karte gerendert, allerdings obliegt es deiner App, für ein ordnungsgemäßes Verhalten zu sorgen.</span><span class="sxs-lookup"><span data-stu-id="18e77-103">By default, the actions will render as buttons on the card, but it's up to your app to make them behave as you expect.</span></span> <span data-ttu-id="18e77-104">Jedes SDK verfügt über das Äquivalent eines `OnAction`-Ereignisses, die verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="18e77-104">Each SDK has the equivalent of an `OnAction` event that you must handle.</span></span>

* <span data-ttu-id="18e77-105">**Action.OpenUrl**: Öffnet die angegebene `url`.</span><span class="sxs-lookup"><span data-stu-id="18e77-105">**Action.OpenUrl** - open the specified `url`.</span></span>  
* <span data-ttu-id="18e77-106">**Action.Submit**: Akzeptiert das Ergebnis der Übermittlung und sendet es an die Quelle.</span><span class="sxs-lookup"><span data-stu-id="18e77-106">**Action.Submit** - take the result of the submit and send it to the source.</span></span> <span data-ttu-id="18e77-107">Wie du das Ergebnis an die Quelle der Karte sendest, liegt allein in deinem Ermessen.</span><span class="sxs-lookup"><span data-stu-id="18e77-107">How you send it to the source of the card is entirely up to you.</span></span>
* <span data-ttu-id="18e77-108">**Action.ShowCard**: Ruft ein Dialogfeld auf und rendert die untergeordnete Karte in diesem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="18e77-108">**Action.ShowCard** - invokes a dialog and renders the sub-card into that dialog.</span></span> <span data-ttu-id="18e77-109">Beachte, dass du dies nur verarbeiten musst, wenn `ShowCardActionMode` auf `popup` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="18e77-109">Note that you only need to handle this if `ShowCardActionMode` is set to `popup`.</span></span>