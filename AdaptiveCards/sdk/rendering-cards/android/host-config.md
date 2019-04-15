---
title: Hosten von Android SDK-Konfiguration –
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
# <a name="host-config---android"></a>Host-Konfiguration – Android

Geben Sie zum Anpassen des Renderers eine Instanz des Objekts HostConfig an. (Finden Sie unter [Hosts Config-Schema](../../../rendering-cards/host-config.md) für die vollständige Beschreibung.)

Verwenden Sie zum Erstellen eines HostConfig-Objekts aus einer Zeichenfolge, die DeserializeFromString-Methode

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```