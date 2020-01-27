---
title: 'Host Konfiguration: IOS SDK'
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: fa420c0a6e9e9b7e5713b6cc528de39335f0b56c
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727474"
---
# <a name="host-config---ios"></a>Host Konfiguration-IOS

Der Host kann über die hostconfig konfiguriert werden, die durch eine JSON-Zeichenfolge generiert werden kann.

```objective-c
ACOParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
```

Standardhostconfig kann instanziiert werden.

```objective-c
ACOHostConfig *defaultConfig = [[ACHostConfig alloc] init];
```

## <a name="render-a-card-using-host-config"></a>Rendering einer Karte mithilfe der Host Konfiguration

Der Rederer nimmt die Adaptive Karte und die Host Konfiguration vor. Hostconfig kann NULL sein, und wenn NULL, wird der Standardwert verwendet.

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:hostconfigParseResult.config
                   widthConstraint:300.0];
```

## <a name="customization"></a>Anpassung

Es gibt drei Möglichkeiten, das Rendering von adaptiven Karten anzupassen:

1. Hostkonfiguration
2. XIb
3. Benutzerdefiniertes Element Rendering
