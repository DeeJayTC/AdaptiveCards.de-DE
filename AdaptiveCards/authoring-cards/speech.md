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
# <a name="speech-and-advanced-customization"></a>Sprach- und erweiterte Anpassung
Wir leben in einer Zeit der Spracherkennung Interaktion über Dienste wie Cortana.  Mit Adaptive Cards werden vom ersten Tag sollen-Sprache, "kalt" neue Hands-Full-Szenarien zu unterstützen.

Die `speak` Tag können adaptive Karte, die in einer Umgebung übermittelt werden, in dem eine visuelle Darstellung nicht primäre, z. B. an ein Dashboard Auto beim vorantreiben ist. 

## <a name="speak-property"></a>Sprechen Sie die Eigenschaft
Sprache unterstützen, wir haben, eine `speak` Eigenschaft, die Text für den Benutzer ein enthält. Der Text kann angemerkt werden, mithilfe von Markup für die synthesesprache ([SSML](https://msdn.microsoft.com/en-us/library/office/hh361578)). SSML steuert die Geschwindigkeit, Ton und Wendepunkt von der Sprache.  Sie können sogar Stream Audio-oder ein renderobjekt einen Audiostream TTS aus Ihrem eigenen Dienst, bietet Ihnen ein hohes Maß an Flexibilität für die Anpassung.

Es gibt zwei Muster für die Verwendung von Eigenschaften sprechen, von einer hostanwendung:

* **Bei der Lieferung** – Wenn eine Karte übermittelt wird, der Client kann sich entscheiden, zum Lesen der Speak-Eigenschaft für die Karte, um die Karte als Ganzes zu beschreiben.
* **Bei Bedarf** – um ein umfangreicheres Barrierefreiheitsmodell, das Schema unterstützt eine Speak-Tag für jedes Element zu unterstützen. Der Client kann eine Speak-Eigenschaft für jedes Element in der Karte gelesen.

### <a name="examples"></a>Beispiele

```json
    "speak":"hello world!"

    "speak":"<s>This is sentence 1.</s><s>This is sentence two</s>"

    "speak":"<speak><audio src='https://www.soundjay.com/misc/bell-ringing-04.mp3'/><s>Time to wake up!</s></speak>"
```

## <a name="speech-content-design"></a>Spracherkennung inhaltsdesign

Inhalte, die für die Spracherkennung unterscheidet sich von der Inhalte, die für die grafische Darstellung. Wenn Sie eine Karte entwerfen, Entwerfen Sie eine gesamte visuelle Darstellung, um Informationen zu einem Benutzer auf eine Weise zu präsentieren, die sie delights. Beim Entwerfen der Spracherkennung, sollten Sie sich vorstellen dazu, wie Sie den Inhalt auf eine Weise verbal zu beschreiben, die den Benutzer delights.  
