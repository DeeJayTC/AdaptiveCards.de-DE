---
title: Host Konfiguration-Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: c44cf609fd52423a1ca17988a875c6dc48550007
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553342"
---
# <a name="host-config---android"></a>Host Konfiguration-Android

Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an. (Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../rendering-cards/host-config.md) .)

Verwenden Sie die deserializefromstring-Methode, um ein hostconfig-Objekt aus einer Zeichenfolge zu erstellen.

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```