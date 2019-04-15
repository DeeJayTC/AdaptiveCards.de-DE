---
title: Behandeln von Spracherkennung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: daea48607376c84f0e0f0af9450cac7dcdf67c0e
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552482"
---
# <a name="handling-speech"></a><span data-ttu-id="064aa-102">Behandeln von Spracherkennung</span><span class="sxs-lookup"><span data-stu-id="064aa-102">Handling speech</span></span>

<span data-ttu-id="064aa-103">Unterstützung Speech mit adaptive Cards hat die `speak` Eigenschaft enthält Informationen wie eine Karte zu einem Benutzer vorgelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="064aa-103">To support speech adaptive Cards has the `speak` property which contains information on how a card shoudl be read aloud to a user.</span></span>

<span data-ttu-id="064aa-104">Die Sprach-Tag kann angemerkt werden, mithilfe von [SSML-Markup](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx).</span><span class="sxs-lookup"><span data-stu-id="064aa-104">The speech tag can be annotated using  [SSML markup](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx).</span></span> <span data-ttu-id="064aa-105">SSML bietet Ihnen die Möglichkeit Steuerelements die Geschwindigkeit, Ton, Wendepunkt von der Sprache.</span><span class="sxs-lookup"><span data-stu-id="064aa-105">SSML gives you the ability control the speed, tone, inflection of the speech.</span></span>  <span data-ttu-id="064aa-106">Sie können sogar Stream Audio-oder ein renderobjekt einen Audiostream TTS aus Ihrem eigenen Dienst, bietet Ihnen eine umfangreiche Anpassung.</span><span class="sxs-lookup"><span data-stu-id="064aa-106">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of customization.</span></span>

<span data-ttu-id="064aa-107">Es gibt 2 Muster für die Verwendung von Eigenschaften sprechen, von einer hostanwendung:</span><span class="sxs-lookup"><span data-stu-id="064aa-107">There are 2 patterns for speak property usage by a host application:</span></span>
* <span data-ttu-id="064aa-108">**Bei der Lieferung** : Wenn eine Karte mit einen Client übermittelt wird können entscheiden, zum Lesen der Speak-Eigenschaft für die Karte, um die Karte als Ganzes zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="064aa-108">**on delivery** - When a card is delivered a client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="064aa-109">**bei Bedarf** – um einem umfangreicheren Zugriffsmodell auf das Schema unterstützt eine Speak tag pro Element zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="064aa-109">**on demand** - In order to support a richer accessibility model the schema supports a speak tag per element.</span></span>  
<span data-ttu-id="064aa-110">Dies ermöglicht Clients, die jedes Element an die Empfänger Zugriff auf Anforderungen zu lesen.</span><span class="sxs-lookup"><span data-stu-id="064aa-110">This allows for clients to read each element to recipients with accessibility requirements.</span></span>

