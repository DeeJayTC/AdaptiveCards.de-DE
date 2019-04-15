---
title: Hosten der JavaScript-SDK-Konfiguration –
author: matthidinger
ms.author: mahiding
ms.date: 11/28/2017
ms.topic: article
ms.openlocfilehash: 1809a022481e4fb28d2db454cfe90e07d09279ff
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553602"
---
# <a name="host-config---javascript"></a>Host-Konfiguration – JavaScript

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

Es gibt 3 Möglichkeiten, um das Rendering adaptive Karte anpassen: 
1. Host-Konfiguration
2. CSS-Stile
3. Benutzerdefiniertes Element-Textrendering

### <a name="hostconfig"></a>HostConfig 

Ein [Hosts Config](../../../rendering-cards/host-config.md) ist eine Konfiguration für shared-Objekt, das Verstehen von allen Renderern. Dadurch können Sie allgemeine Formatvorlagen (z. B. Schriftfamilie, Schriftgrößen, Abstände Standard) und Verhaltensweisen (z. B. maximale Anzahl von Aktionen), die automatisch mit jeder Plattform Renderer interpretiert werden, zu definieren. 

Das Ziel ist, dass von jeder Plattform Renderer generierten systemeigene Benutzeroberfläche sehr ähnlich, mit minimalem Aufwand ihrerseits aussieht.

```javascript
var renderOptions = {
    ...
    hostConfig: {
        // Define your host config object here
        // See the HostConfig docs for details
    }
};
```