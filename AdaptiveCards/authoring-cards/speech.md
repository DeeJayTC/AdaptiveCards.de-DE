---
title: Sprache und erweiterte Anpassung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 19e77b86da9d163f5fcf6a6074071a4638a8d793
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2019
ms.locfileid: "59552612"
---
# <a name="speech-and-advanced-customization"></a>Sprache und erweiterte Anpassung
Wir leben in einer Zeit der Spracherkennung, in der wir mit Diensten wir Cortana interagieren.  Adaptive Karten sollen von Anfang an die Spracherkennung unterstützen und ermöglichen so coole neue Szenarien.

Das Tag `speak` ermöglicht die Bereitstellung der adaptiven Karte in einer Umgebung, in der eine visuelle Anzeige nicht die wichtigste Funktion ist, beispielsweise auf dem Armaturenbrett eines Autos beim Fahren. 

## <a name="speak-property"></a>Speak-Eigenschaft
Zur Unterstützung der Spracherkennung gibt es die Eigenschaft `speak`, die den Text enthält, den der Benutzer hört. Der Text kann mithilfe von Speech Synthesis Markup Language ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)) mit Anmerkungen versehen werden. SSML steuert die Geschwindigkeit, den Tonfall und die Flexion der Sprache.  Es ermöglicht dir sogar das Streamen von Audio oder das Rendern eines TTS-Audiodatenstroms von deinem eigenen Dienst und bietet dir so ein hohes Maß an Flexibilität für deine eigenen Anpassungen.

Es gibt zwei Muster für die Verwendung der Speak-Eigenschaft durch eine Hostanwendung:

* **Bei der Bereitstellung:** Wenn eine Karte übermittelt wird, kann der Client auswählen, die Speak-Eigenschaft für die Karte zu lesen, um die ganze Karte zu beschreiben.
* **Bei Bedarf:** Dieses Schema unterstützt ein Speak-Tag für jedes Element und somit ein umfangreicheres Barrierefreiheitsmodell. Der Client kann eine Speak-Eigenschaft für jedes Element in der Karte lesen.

### <a name="examples"></a>Beispiele

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a>Design des Sprachinhalts

Inhalte, die für die Spracherkennung entwickelt wurden, unterscheiden sich von Inhalten, die für die grafische Darstellung entwickelt wurden. Wenn du eine Karte entwirfst, entwickelst du eine gesamte visuelle Darstellung, um Benutzern Informationen auf ansprechende Weise zu präsentieren. Wenn du Inhalte für die Spracherkennung entwirfst, denk daran, wie du den Inhalt verbal ansprechend beschreiben kannst.  
