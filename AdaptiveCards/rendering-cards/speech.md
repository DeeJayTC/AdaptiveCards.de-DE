---
title: Verarbeiten der Sprachausgabe
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: fb56c97da3cca776da0fc7ea65a9726c8826e910
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "76145540"
---
# <a name="handling-speech"></a><span data-ttu-id="e8dad-102">Verarbeiten der Sprachausgabe</span><span class="sxs-lookup"><span data-stu-id="e8dad-102">Handling speech</span></span>

<span data-ttu-id="e8dad-103">Zur Unterstützung der Sprachausgabe verfügen adaptive Karten über die Eigenschaft `speak`, die Informationen darüber enthält, wie eine Karte einem Benutzer vorgelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8dad-103">To support speech adaptive Cards has the `speak` property which contains information on how a card should be read aloud to a user.</span></span>

<span data-ttu-id="e8dad-104">Das Sprachtag kann nicht per [SSML-Markup](https://msdn.microsoft.com/library/office/hh361578(v=office.14).aspx) mit Anmerkungen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="e8dad-104">The speech tag can be annotated using  [SSML markup](https://msdn.microsoft.com/library/office/hh361578(v=office.14).aspx).</span></span> <span data-ttu-id="e8dad-105">Mit SSML kannst du die Geschwindigkeit, den Klang und den Tonfall der Sprachausgabe steuern.</span><span class="sxs-lookup"><span data-stu-id="e8dad-105">SSML gives you the ability control the speed, tone, inflection of the speech.</span></span>  <span data-ttu-id="e8dad-106">Du kannst sogar Audiodaten streamen oder einen TTS-Audiostream aus deinem eigenen Dienst rendern und das Feature auf diese Weise genau an deine Anforderungen anpassen.</span><span class="sxs-lookup"><span data-stu-id="e8dad-106">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of customization.</span></span>

<span data-ttu-id="e8dad-107">Es gibt zwei Muster für die Verwendung der Eigenschaft „speak“ durch eine Hostanwendung:</span><span class="sxs-lookup"><span data-stu-id="e8dad-107">There are 2 patterns for speak property usage by a host application:</span></span>
* <span data-ttu-id="e8dad-108">**Bei der Bereitstellung**: Wenn eine Karte übermittelt wird, kann der Client die speak-Eigenschaft für die Karte lesen, um die ganze Karte zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e8dad-108">**on delivery** - When a card is delivered a client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="e8dad-109">**Bei Bedarf**: Dieses Schema unterstützt ein speak-Tag für jedes Element und somit ein umfangreicheres Barrierefreiheitsmodell.</span><span class="sxs-lookup"><span data-stu-id="e8dad-109">**on demand** - In order to support a richer accessibility model the schema supports a speak tag per element.</span></span>  
<span data-ttu-id="e8dad-110">Damit können Clients Empfängern, die Barrierefreiheitsfunktionen benötigen, jedes Element vorlesen.</span><span class="sxs-lookup"><span data-stu-id="e8dad-110">This allows for clients to read each element to recipients with accessibility requirements.</span></span>

