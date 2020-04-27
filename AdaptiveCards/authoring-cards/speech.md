---
title: Sprache und erweiterte Anpassung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 1dfd9b0c45a280905223e3286998b333b0a6ec6a
ms.sourcegitcommit: e6418d692296e06be7412c95c689843f9db5240d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "76145341"
---
# <a name="speech-and-advanced-customization"></a><span data-ttu-id="05b83-102">Sprache und erweiterte Anpassung</span><span class="sxs-lookup"><span data-stu-id="05b83-102">Speech and advanced customization</span></span>
<span data-ttu-id="05b83-103">Wir leben in einer Zeit der Spracherkennung, in der wir mit Diensten wir Cortana interagieren.</span><span class="sxs-lookup"><span data-stu-id="05b83-103">We live in an era of speech interaction via services like Cortana.</span></span>  <span data-ttu-id="05b83-104">Adaptive Karten sollen von Anfang an die Spracherkennung unterstützen und ermöglichen so coole neue Szenarien.</span><span class="sxs-lookup"><span data-stu-id="05b83-104">Adaptive cards are designed from day one to support speech, enabling cool new hands-full scenarios.</span></span>

<span data-ttu-id="05b83-105">Das Tag `speak` ermöglicht die Bereitstellung der adaptiven Karte in einer Umgebung, in der eine visuelle Anzeige nicht die wichtigste Funktion ist, beispielsweise auf dem Armaturenbrett eines Autos beim Fahren.</span><span class="sxs-lookup"><span data-stu-id="05b83-105">The `speak` tag enables the adaptive card to be delivered to an environment where a visual display is not primary experience, such as to a car dashboard while driving.</span></span> 

## <a name="speak-property"></a><span data-ttu-id="05b83-106">Speak-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="05b83-106">Speak property</span></span>
<span data-ttu-id="05b83-107">Zur Unterstützung der Spracherkennung gibt es die Eigenschaft `speak`, die den Text enthält, den der Benutzer hört.</span><span class="sxs-lookup"><span data-stu-id="05b83-107">To support speech we have a `speak` property which contains text to say to the user.</span></span> <span data-ttu-id="05b83-108">Der Text kann mithilfe von Speech Synthesis Markup Language ([SSML](https://msdn.microsoft.com/library/office/hh361578)) mit Anmerkungen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="05b83-108">The text can be annotated using speech synthesis markup language ([SSML](https://msdn.microsoft.com/library/office/hh361578)).</span></span> <span data-ttu-id="05b83-109">SSML steuert die Geschwindigkeit, den Tonfall und die Flexion der Sprache.</span><span class="sxs-lookup"><span data-stu-id="05b83-109">SSML controls the speed, tone, and inflection of the speech.</span></span>  <span data-ttu-id="05b83-110">Es ermöglicht dir sogar das Streamen von Audio oder das Rendern eines TTS-Audiodatenstroms von deinem eigenen Dienst und bietet dir so ein hohes Maß an Flexibilität für deine eigenen Anpassungen.</span><span class="sxs-lookup"><span data-stu-id="05b83-110">It even allows you to stream audio or a render a TTS audio stream from your own service, giving you a great deal of flexibility for customization.</span></span>

<span data-ttu-id="05b83-111">Es gibt zwei Muster für die Verwendung der Speak-Eigenschaft durch eine Hostanwendung:</span><span class="sxs-lookup"><span data-stu-id="05b83-111">There are two patterns for speak property usage by a host application:</span></span>

* <span data-ttu-id="05b83-112">**Bei der Bereitstellung:** Wenn eine Karte übermittelt wird, kann der Client auswählen, die Speak-Eigenschaft für die Karte zu lesen, um die ganze Karte zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="05b83-112">**On delivery** - When a card is delivered, the client may opt to read the Speak property for the card to describe the card as a whole.</span></span>
* <span data-ttu-id="05b83-113">**Bei Bedarf:** Dieses Schema unterstützt ein Speak-Tag für jedes Element und somit ein umfangreicheres Barrierefreiheitsmodell.</span><span class="sxs-lookup"><span data-stu-id="05b83-113">**On demand** - In order to support a richer accessibility model, the schema supports a speak tag for each element.</span></span> <span data-ttu-id="05b83-114">Der Client kann eine Speak-Eigenschaft für jedes Element in der Karte lesen.</span><span class="sxs-lookup"><span data-stu-id="05b83-114">The client may read a Speak property  for each element in the card.</span></span>

### <a name="examples"></a><span data-ttu-id="05b83-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="05b83-115">Examples</span></span>

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a><span data-ttu-id="05b83-116">Design des Sprachinhalts</span><span class="sxs-lookup"><span data-stu-id="05b83-116">Speech content design</span></span>

<span data-ttu-id="05b83-117">Inhalte, die für die Spracherkennung entwickelt wurden, unterscheiden sich von Inhalten, die für die grafische Darstellung entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="05b83-117">Content designed for speech is different from content designed for visual display.</span></span> <span data-ttu-id="05b83-118">Wenn du eine Karte entwirfst, entwickelst du eine gesamte visuelle Darstellung, um Benutzern Informationen auf ansprechende Weise zu präsentieren.</span><span class="sxs-lookup"><span data-stu-id="05b83-118">When you design a card, you are designing an entire visual experience to present information to a user in a way that delights them.</span></span> <span data-ttu-id="05b83-119">Wenn du Inhalte für die Spracherkennung entwirfst, denk daran, wie du den Inhalt verbal ansprechend beschreiben kannst.</span><span class="sxs-lookup"><span data-stu-id="05b83-119">When designing for speech, you should think about how to verbally describe the content in a way that delights the user.</span></span>  
