---
title: 'Native Formatierung: IOS SDK'
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: f9ed839a19ac778381fa36361ad37e95b7ab5e08
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727469"
---
# <a name="native-styling---ios"></a>Native Formatierung (IOS)

Verwenden Sie XIb für differenzierte Formatierungen.

Die folgenden xisb sind vorhanden.

| XIb | Usage |
|---|---|
| Acrbutton. XIb | Parab |
| Acrcellforcompactmode. XIb   | Choiceset Compact-Modus|
| Acrdatepicker. XIb | DatePicker für Input. Date |
| Acrdatetextfield. XIb  | TextField für Input. Date |
| Acrinputtableview. XIb   | Container für Eingaben |
| Acrlabelview. XIb  | TextBlock |
| Acrpickerview. XIb | Choiceset |
| Acrquickaktionmultilineview. XIb  | Schnelle Aktionen mit mehreren Zeilen |
| Acrquickaktionview. XIb | Schnelle Aktionen |
| Acrtextfield. XIb | Input |

XIb kann über Xcode IB bearbeitet werden.
Nachdem xisb an der Spezifikation bearbeitet wurden.
Von einem Terminal
```
ibtool --compile name.nib name.xib 
```

So formatieren Sie z. b. eine Schaltfläche
```
ibtool --compile ACRButton.nib ACRButton.xib 
```

Die generierten nib-Dateien können dann in adaptivecards. Framework ersetzt werden.
