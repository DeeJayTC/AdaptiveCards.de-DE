---
title: Android SDK
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: d15e0963427babe045a4db6f93800e09e0d95da9
ms.sourcegitcommit: 9a9973129c36a41f5e4af30d95ffc146820ad173
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76145500"
---
# <a name="getting-started---android"></a>Erste Schritte – Android

Dies ist ein Renderer für native Android-Steuerelemente.

## <a name="install-maven-package"></a>Installieren des Maven-Pakets

[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)

Die veröffentlichten Pakete findest du ![hier.](https://search.maven.org/search?q=g:io.adaptivecards)

Damit du die Bibliothek in dein Projekt einbeziehen kannst, musst du im Abschnitt mit den Abhängigkeiten diese Zeile in gradle.build deines Projekts einbeziehen.

```build.gradle
 implementation 'io.adaptivecards:adaptivecards-android:1.1.0'
```
Je nach der Version, die du in dein Projekt einbeziehen möchtest, musst du die Versionsnummer ändern.

## <a name="add-import"></a>Hinzufügen eines Imports

Füge den folgenden Import hinzu, um das Objektmodell einzubeziehen:

```
 import io.adaptivecards.objectmodel.*;
```

Füge den folgenden Import hinzu, um den Renderer einzubeziehen:

```
 import io.adaptivecards.renderer.*;
```

## <a name="next-steps"></a>Nächste Schritte

Informationen zu den nächsten Schritten findest du unter [Rendern einer Karte](render-a-card.md).
