---
title: Hosts Config - SDK für iOS
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: b788ecc5c2371d2575e0165296365238535dd7c5
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553702"
---
# <a name="host-config---ios"></a>Host-Konfiguration – iOS

Host kann über HostConfig konfiguriert werden, die von JSON-Zeichenfolge generiert werden können

```objective-c
ACOParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
```

Standard-HostConfig kann instanziiert werden

```objective-c
ACOHostConfig *defaultConfig = [[ACHostConfig alloc] init];
```

## <a name="render-a-card-using-host-config"></a>Rendern Sie eine Karte mit Host-Konfiguration

Rederer dauert adaptive Card und Host-Konfiguration. HostConfig kann NULL sein, und wenn NULL, Standardwert verwendet werden.

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:hostconfigParseResult.config
                   widthConstraint:300.0];
```