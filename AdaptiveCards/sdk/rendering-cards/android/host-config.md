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
# <a name="host-config---android"></a><span data-ttu-id="87ba3-102">Host Konfiguration-Android</span><span class="sxs-lookup"><span data-stu-id="87ba3-102">Host config - Android</span></span>

<span data-ttu-id="87ba3-103">Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="87ba3-103">To customize the renderer you provide an instance of the HostConfig object.</span></span> <span data-ttu-id="87ba3-104">(Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../rendering-cards/host-config.md) .)</span><span class="sxs-lookup"><span data-stu-id="87ba3-104">(See [Host Config Schema](../../../rendering-cards/host-config.md) for the full description.)</span></span>

<span data-ttu-id="87ba3-105">Verwenden Sie die deserializefromstring-Methode, um ein hostconfig-Objekt aus einer Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87ba3-105">To Create a HostConfig object from a string, use the DeserializeFromString method</span></span>

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```