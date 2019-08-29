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
# <a name="host-config---android"></a><span data-ttu-id="b7f12-102">Host Konfiguration-Android</span><span class="sxs-lookup"><span data-stu-id="b7f12-102">Host config - Android</span></span>

<span data-ttu-id="b7f12-103">Zum Anpassen des Renderers geben Sie eine Instanz des hostconfig-Objekts an.</span><span class="sxs-lookup"><span data-stu-id="b7f12-103">To customize the renderer you provide an instance of the HostConfig object.</span></span> <span data-ttu-id="b7f12-104">(Die vollständige Beschreibung finden Sie unter [Host config Schema](../../../rendering-cards/host-config.md) .)</span><span class="sxs-lookup"><span data-stu-id="b7f12-104">(See [Host Config Schema](../../../rendering-cards/host-config.md) for the full description.)</span></span>

<span data-ttu-id="b7f12-105">Verwenden Sie die deserializefromstring-Methode, um ein hostconfig-Objekt aus einer Zeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7f12-105">To Create a HostConfig object from a string, use the DeserializeFromString method</span></span>

```java
HostConfig hostConfig = HostConfig.DeserializeFromString(hostConfigText);
```