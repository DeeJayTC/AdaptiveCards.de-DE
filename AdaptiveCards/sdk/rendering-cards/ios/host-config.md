---
title: 'Host Konfiguration: IOS SDK'
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 614fc4a91941f59e422470c37ee90faa547bcede
ms.sourcegitcommit: c921a7bb15a95c0ceb803ad375501ee3b8bef028
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83631303"
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

Der Renderer nimmt die Adaptive Karte und die Host Konfiguration an. Hostconfig kann NULL sein, und wenn NULL, wird der Standardwert verwendet.

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
