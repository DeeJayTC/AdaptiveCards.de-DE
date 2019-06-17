---
title: Status des Renderers
author: matthidinger
ms.author: mahiding
ms.date: 10/12/2018
ms.topic: article
ms.openlocfilehash: bffa49012a8ebe686fc033f98b2438d2e9e959cc
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138033"
---
# <a name="renderer-status"></a>Status des Renderers
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

### <a name="extensibility"></a>Erweiterungen

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

