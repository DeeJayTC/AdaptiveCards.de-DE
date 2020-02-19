---
title: Host Konfiguration-JavaScript SDK
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: a011ffc43c2990cd8eb568b9f1c449cf541f9a70
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454614"
---
# <a name="host-config---javascript"></a>Host Konfiguration-JavaScript

```js
// Create an AdaptiveCard instance
var adaptiveCard = new AdaptiveCards.AdaptiveCard();

// Set its hostConfig property unless you want to use the default Host Config
// Host Config defines the style and behavior of a card
adaptiveCard.hostConfig = new AdaptiveCards.HostConfig({
    fontFamily: "Segoe UI, Helvetica Neue, sans-serif"
    // More host config options
});

// Render the card to an HTML element:
var renderedCard = adaptiveCard.render();
```

## <a name="customization"></a>Anpassung

Es gibt drei Möglichkeiten, das Rendering von adaptiven Karten anzupassen: 
1. Hostkonfiguration
2. CSS-Formatvorlagen
3. Benutzerdefiniertes Element Rendering

### <a name="hostconfig"></a>HostConfig 

Eine [Hostkonfiguration](../../../rendering-cards/host-config.md) ist ein gemeinsam genutztes Konfigurationsobjekt, das von allen Renderern verstanden wird. Dadurch kannst du allgemeine Formatvorlagen (z. B. Schriftfamilie, Schriftgrad, Standardabstand) und Verhaltensweisen (z. B. die maximale Anzahl von Aktionen) definieren, die von jedem Plattformrenderer automatisch interpretiert werden. 

Das Ziel besteht darin, dass die von jedem Plattformrenderer generierte native Benutzeroberfläche ähnlich aussieht und dein Aufwand hierfür nur gering ist.

```javascript
var renderOptions = {
    ...
    hostConfig: {
        // Define your host config object here
        // See the HostConfig docs for details
    }
};
```