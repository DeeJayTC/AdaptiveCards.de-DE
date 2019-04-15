---
title: Sprach- und erweiterte Anpassung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 19e77b86da9d163f5fcf6a6074071a4638a8d793
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552612"
---
# <a name="speech-and-advanced-customization"></a><span data-ttu-id="a8294-102">Sprach- und erweiterte Anpassung</span><span class="sxs-lookup"><span data-stu-id="a8294-102">Speech and advanced customization</span></span>
<span data-ttu-id="a8294-103">Wir leben in einer Zeit der Spracherkennung Interaktion über Dienste wie Cortana.</span><span class="sxs-lookup"><span data-stu-id="a8294-103">We live in an era of speech interaction via services like Cortana.</span></span>  <span data-ttu-id="a8294-104">Mit Adaptive Cards werden vom ersten Tag sollen-Sprache, "kalt" neue Hands-Full-Szenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a8294-104">Adaptive cards are designed from day one to support speech, enabling cool new hands-full scenarios.</span></span>

<span data-ttu-id="a8294-105">Die `speak` Tag können adaptive Karte, die in einer Umgebung übermittelt werden, in dem eine visuelle Darstellung nicht primäre, z. B. an ein Dashboard Auto beim vorantreiben ist.</span><span class="sxs-lookup"><span data-stu-id="a8294-105">The `speak` tag enables the adaptive card to be delivered to an environment where a visual display is not primary experience, such as to a car dashboard while driving.</span></span> 

## <a name="speak-property"></a><span data-ttu-id="a8294-106">Sprechen Sie die Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a8294-106">Speak property</span></span>
<span data-ttu-id="a8294-107">Sprache unterstützen, wir haben, eine `speak` Eigenschaft, die Text für den Benutzer ein enthält.</span><span class="sxs-lookup"><span data-stu-id="a8294-107">To support speech we have a `speak` property which contains text to say to the user.</span></span> <span data-ttu-id="a8294-108">Der Text kann angemerkt werden, mithilfe von Markup für die synthesesprache ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)).</span><span class="sxs-lookup"><span data-stu-id="a8294-108">The text can be annotated using speech synthesis markup language ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)).</span></span> <span data-ttu-id="a8294-109">SSML steuert die Geschwindigkeit, Ton und Wendepunkt von der Sprache.</span><span class="sxs-lookup"><span data-stu-id="a8294-109">SSML controls the speed, tone, and inflection of the speech.</span></span>  <span data-ttu-id="a8294-110">Sie können sogar Stream Audio-oder ein renderobjekt einen Audiostream TTS aus Ihrem eigenen Dienst, bietet Ihnen ein hohes Maß an Flexibilität für die Anpassung.</span><span class="sxs-lookup"><span data-stu-id="a8294-110">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of flexibility for customization.</span></span>

<span data-ttu-id="a8294-111">Es gibt zwei Muster für die Verwendung von Eigenschaften sprechen, von einer hostanwendung:</span><span class="sxs-lookup"><span data-stu-id="a8294-111">There are two patterns for speak property usage by a host application:</span></span>

* <span data-ttu-id="a8294-112">**Bei der Lieferung** – Wenn eine Karte übermittelt wird, der Client kann sich entscheiden, zum Lesen der Speak-Eigenschaft für die Karte, um die Karte als Ganzes zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a8294-112">**On delivery** - When a card is delivered, the client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="a8294-113">**Bei Bedarf** – um ein umfangreicheres Barrierefreiheitsmodell, das Schema unterstützt eine Speak-Tag für jedes Element zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a8294-113">**On demand** - In order to support a richer accessibility model, the schema supports a speak tag for each element.</span></span> <span data-ttu-id="a8294-114">Der Client kann eine Speak-Eigenschaft für jedes Element in der Karte gelesen.</span><span class="sxs-lookup"><span data-stu-id="a8294-114">The client may read a Speak property  for each element in the card.</span></span>

### <a name="examples"></a><span data-ttu-id="a8294-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a8294-115">Examples</span></span>

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a><span data-ttu-id="a8294-116">Spracherkennung inhaltsdesign</span><span class="sxs-lookup"><span data-stu-id="a8294-116">Speech content design</span></span>

<span data-ttu-id="a8294-117">Inhalte, die für die Spracherkennung unterscheidet sich von der Inhalte, die für die grafische Darstellung.</span><span class="sxs-lookup"><span data-stu-id="a8294-117">Content designed for speech is different from content designed for visual display.</span></span> <span data-ttu-id="a8294-118">Wenn Sie eine Karte entwerfen, Entwerfen Sie eine gesamte visuelle Darstellung, um Informationen zu einem Benutzer auf eine Weise zu präsentieren, die sie delights.</span><span class="sxs-lookup"><span data-stu-id="a8294-118">When you design a card, you are designing an entire visual experience to present information to a user in a way that delights them.</span></span> <span data-ttu-id="a8294-119">Beim Entwerfen der Spracherkennung, sollten Sie sich vorstellen dazu, wie Sie den Inhalt auf eine Weise verbal zu beschreiben, die den Benutzer delights.</span><span class="sxs-lookup"><span data-stu-id="a8294-119">When designing for speech, you should think about how to verbally describe the content in a way that delights the user.</span></span>  
