---
title: Behandeln von Spracherkennung
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 64eeaefbc2ac775b69bd48cc853beb729cb2c37f
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67137993"
---
# <a name="handling-speech"></a>Behandeln von Spracherkennung

Unterstützung Speech mit adaptive Cards hat die `speak` Eigenschaft enthält Informationen wie eine Karte zu einem Benutzer vorgelesen werden soll.

Die Sprach-Tag kann angemerkt werden, mithilfe von [SSML-Markup](https://msdn.microsoft.com/en-us/library/office/hh361578(v=office.14).aspx). SSML bietet Ihnen die Möglichkeit Steuerelements die Geschwindigkeit, Ton, Wendepunkt von der Sprache.  Sie können sogar Stream Audio-oder ein renderobjekt einen Audiostream TTS aus Ihrem eigenen Dienst, bietet Ihnen eine umfangreiche Anpassung.

Es gibt 2 Muster für die Verwendung von Eigenschaften sprechen, von einer hostanwendung:
* **Bei der Lieferung** : Wenn eine Karte mit einen Client übermittelt wird können entscheiden, zum Lesen der Speak-Eigenschaft für die Karte, um die Karte als Ganzes zu beschreiben.
* **bei Bedarf** – um einem umfangreicheren Zugriffsmodell auf das Schema unterstützt eine Speak tag pro Element zu unterstützen.  
Dies ermöglicht Clients, die jedes Element an die Empfänger Zugriff auf Anforderungen zu lesen.

