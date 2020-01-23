---
title: Verarbeiten der Sprachausgabe
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: fb56c97da3cca776da0fc7ea65a9726c8826e910
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145540"
---
# <a name="handling-speech"></a>Verarbeiten der Sprachausgabe

Zur Unterstützung der Sprachausgabe verfügen adaptive Karten über die Eigenschaft `speak`, die Informationen darüber enthält, wie eine Karte einem Benutzer vorgelesen werden soll.

Das Sprachtag kann nicht per [SSML-Markup](https://msdn.microsoft.com/library/office/hh361578(v=office.14).aspx) mit Anmerkungen versehen werden. Mit SSML kannst du die Geschwindigkeit, den Klang und den Tonfall der Sprachausgabe steuern.  Du kannst sogar Audiodaten streamen oder einen TTS-Audiostream aus deinem eigenen Dienst rendern und das Feature auf diese Weise genau an deine Anforderungen anpassen.

Es gibt zwei Muster für die Verwendung der Eigenschaft „speak“ durch eine Hostanwendung:
* **Bei der Bereitstellung**: Wenn eine Karte übermittelt wird, kann der Client die speak-Eigenschaft für die Karte lesen, um die ganze Karte zu beschreiben.
* **Bei Bedarf**: Dieses Schema unterstützt ein speak-Tag für jedes Element und somit ein umfangreicheres Barrierefreiheitsmodell.  
Damit können Clients Empfängern, die Barrierefreiheitsfunktionen benötigen, jedes Element vorlesen.

