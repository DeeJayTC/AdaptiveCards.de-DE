---
title: Status des Renderers
author: matthidinger
ms.author: mahiding
ms.date: 10/12/2018
ms.topic: article
ms.openlocfilehash: 63426b2250407cc40af8c46975c10f57d1028a40
ms.sourcegitcommit: 1e18c5dc0cf85d26f66335e312348bbfb903d95a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77454903"
---
# <a name="renderer-status"></a>Status des Renderers
Die folgenden Tabellen zeigen den aktuellen Status der einzelnen Renderer, basierend auf ihren veröffentlichten öffentlichen Versionen.

### <a name="parsing"></a>Analyse

|Funktion | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Überprüfungsfehler zurückgeben | ✅ | ✅ | ✅ | ✅ | ✅ |
|Unbekannte Eigenschaften analysieren | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="card-rendering"></a>Rendern von Karten

|Funktion | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Auf unterstützte Version überprüfen | ✅ | ✅ | ✅ | ✅ | ✅  |
|Vollständiges Schema rendern | ✅ | ✅ | ✅ | ✅ | ✅ |
|Aktionsleiste rendern | ✅ | ✅ | ✅ | ✅ | ✅ |
|Unbekannte Elemente ignorieren | ✅ | ✅ | ✅ | ✅ | ✅ |
|Unterstützung für Hostkonfiguration | ✅ | ✅ | ✅ | ✅ | ✅ |
|Native Plattformformatierung | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="element-rendering"></a>Rendern von Elementen

|Funktion | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Abstände und Trennzeichen | ✅ | ✅ | ✅ | ✅ | ✅ |
|[DATE/TIME-Formatierung für TextBlock](../authoring-cards/text-features.md#datetime-formatting-and-localization) | ✅ | ✅ | ✅ | ✅ | ✅ |
|[Markdownunterstützung für TextBlock](../authoring-cards/text-features.md#markdown) | ✅* | ✅ | ✅ | ✅ | ✅ |
|Unterstützung für vollständige Eingaben | ✅ | ✅ | ✅ | ✅ | ✅ |

\* Der HTML-Renderer enthält keine integrierte Markdownunterstützung, um die Größe der Bibliothek zu minimieren und es Anwendungen zu ermöglichen, den bevorzugten Markdownprozessor zu verwenden. Der HTML-Renderer verwendet Markdown jedoch automatisch – sofern es geladen ist.

### <a name="extensibility"></a>Erweiterbarkeit

|Funktion | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
|Elementrenderer überschreiben | ✅ | ✅ | ✅ | ✅ | ✅ |
|Neuen Elementrenderer hinzufügen | ✅ | ✅ | ✅ | ✅ | ✅ |
|Elementrenderer entfernen | ✅ | ✅ | ✅ | ✅ | ✅ |
|[Aktionsrenderer überschreiben/hinzufügen/entfernen](https://github.com/Microsoft/AdaptiveCards/issues/1671) | ✅ | ✅ | ❌ | ✅ | ✅ |

### <a name="actions"></a>Aktionen

| Funktion | HTML | .NET | UWP | iOS | Android |
|--- | --- | --- | --- | --- | --- | --- |
| Unterstützung für „Action.OpenUrl“ | ✅ | ✅ | ✅ | ✅ | ✅  |
| Unterstützung für „Action.ShowCard“  | ✅ | ✅ | ✅ | ✅ | ✅ |
| Unterstützung für „Action.Submit“  | ✅ | ✅ | ✅ | ✅ | ✅  |
| Unterstützung für „selectAction“ | ✅ | ✅ | ✅ | ✅ | ✅ |

### <a name="events"></a>Ereignisse

|       Funktion        | HTML | .NET | UWP | iOS | Android | 
|----------------------------|------|------|-----|-----|---------|
| Elementsichtbarkeit geändert |  ✅   |  ❌   |  ❌  |  ❌  | ❌ |

