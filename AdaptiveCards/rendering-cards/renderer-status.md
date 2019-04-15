---
title: Renderer-Status
author: matthidinger
ms.author: mahiding
ms.date: 10/12/2018
ms.topic: article
ms.openlocfilehash: 303d5675f58bd2c870dcdf5718d508d2e3c78fca
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553352"
---
# <a name="renderer-status"></a>Renderer-Status
Die folgenden Tabellen zeigen den aktuellen Status jeder Renderer, basierend auf ihrer öffentlichen veröffentlichten Versionen.

### <a name="parsing"></a>Analysieren von

|Funktionalität | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Fehler bei der Überprüfung zurückgegeben | ✅ | ✅ | ✅ | ✅ | ✅ |
|Eigenschaften von unbekannte analysieren | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="card-rendering"></a>Smartcard-Rendering

|Funktionalität | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Überprüfung auf unterstützte version | ✅ | ✅ | ✅ | ✅ | ✅  |
|Vollständiges Schema Rendern | ✅ | ✅ | ✅ | ✅ | ✅ |
|Rendern von Aktionssymbolleiste | ✅ | ✅ | ✅ | ✅ | ✅ |
|Unbekannte Elemente ignorieren | ✅ | ✅ | ✅ | ✅ | ✅ |
|Unterstützung des Host-Konfiguration | ✅ | ✅ | ✅ | ✅ | ✅ |
|Systemeigene Plattform erstellen | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="element-rendering"></a>Element-Textrendering

|Funktionalität | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Abstand und die Trennzeichen | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock Datum/Uhrzeit-Format](../authoring-cards/text-features.md#datetime-formatting-and-localization) | ✅ | ✅ | ✅ | ✅ | ✅ |
|[TextBlock-Markdown-support](../authoring-cards/text-features.md#markdown) | ✅* | ✅ | ✅ | ✅ | ✅ |
|Gesamte Eingabe zu unterstützen. | ✅ | ✅ | ✅ | ✅ | ✅ |

\* Der HTML-Renderer enthält keine integrierten Unterstützung für Markdown, um die Größe der Bibliothek zu minimieren und verarbeitende Anwendungen, die ihre bevorzugten Markdown-Prozessor verwenden zu können. Der HTML-Renderer verwendet jedoch automatisch Markdown-It, wenn es geladen wird.

### <a name="extensbility"></a>Extensbility

|Funktionalität | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Überschreiben Sie die Element-Renderer | ✅ | ✅ | ✅ | ✅ | ✅ |
|Hinzufügen von neuen Element-Renderer | ✅ | ✅ | ✅ | ✅ | ✅ |
|Entfernen Sie die Element-Renderer | ✅ | ✅ | ✅ | ✅ | ✅ |
|[Aktion-Renderers außer Kraft setzen/hinzufügen/entfernen](https://github.com/Microsoft/AdaptiveCards/issues/1671) | ✅ | ✅ | ❌ | ✅ | ✅ |

### <a name="actions"></a>Aktionen

| Funktionalität | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
| Action.OpenUrl-Unterstützung | ✅ | ✅ | ✅ | ✅ | ✅  |
| Action.ShowCard-Unterstützung  | ✅ | ✅ | ✅ | ✅ | ✅ |
| Action.Submit-Unterstützung  | ✅ | ✅ | ✅ | ✅ | ✅  |
| Unterstützung für selectAction | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="events"></a>Ereignisse

|       Funktionalität        | HTML | .NET | UWP | iOS | Android | 
|----------------------------|------|------|-----|-----|---------|
| Sichtbarkeit des Elements geändert |  ✅   |  ❌   |  ❌  |  ❌  | ❌ |

