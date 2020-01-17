---
title: Host Konfiguration-Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 091e2093c380affc8c895d069a2f52061b991d2f
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145490"
---
# <a name="host-config---android"></a>Host Konfiguration-Android

Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an. (Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../rendering-cards/host-config.md) .)

Verwenden Sie die deserializefromstring-Methode, um ein hostconfig-Objekt aus einer Zeichenfolge zu erstellen.

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```