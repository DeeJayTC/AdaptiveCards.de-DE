---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: b5f1279317e6b34d2e3bccee2625d972ac185e04
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134274"
---
# <a name="getting-started---android"></a><span data-ttu-id="e8a42-102">Erste Schritte – Android</span><span class="sxs-lookup"><span data-stu-id="e8a42-102">Getting started - Android</span></span>

<span data-ttu-id="e8a42-103">Dies ist ein Renderer für native Android-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e8a42-103">This is a renderer which targets Android native controls.</span></span>

## <a name="install-maven-package"></a><span data-ttu-id="e8a42-104">Installieren des Maven-Pakets</span><span class="sxs-lookup"><span data-stu-id="e8a42-104">Install Maven package</span></span>

<span data-ttu-id="e8a42-105">[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)</span><span class="sxs-lookup"><span data-stu-id="e8a42-105">[![Maven Central](https://img.shields.io/maven-central/v/io.adaptivecards/adaptivecards-android.svg)](https://search.maven.org/#search%7Cga%7C1%7Ca%3A%22adaptivecards-android%22)</span></span>

<span data-ttu-id="e8a42-106">Die veröffentlichten Pakete findest du</span><span class="sxs-lookup"><span data-stu-id="e8a42-106">You can find the published packages</span></span> ![hier](https://search.maven.org/search?q=g:io.adaptivecards)

<span data-ttu-id="e8a42-108">Damit du die Bibliothek in dein Projekt einbeziehen kannst, musst du im Abschnitt mit den Abhängigkeiten diese Zeile in gradle.build deines Projekts einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="e8a42-108">To include library to your project you must include this line into your project gradle.build under the dependencies section</span></span>

```build.gradle
 implementation 'io.adaptivecards:adaptivecards-android:1.1.0'
```
<span data-ttu-id="e8a42-109">Je nach der Version, die du in dein Projekt einbeziehen möchtest, musst du die Versionsnummer ändern.</span><span class="sxs-lookup"><span data-stu-id="e8a42-109">You need to change the version number depending on the version you want to include into your project</span></span>

## <a name="add-import"></a><span data-ttu-id="e8a42-110">Hinzufügen eines Imports</span><span class="sxs-lookup"><span data-stu-id="e8a42-110">Add import</span></span>

<span data-ttu-id="e8a42-111">Füge den folgenden Import hinzu, um das Objektmodell einzubeziehen:</span><span class="sxs-lookup"><span data-stu-id="e8a42-111">To include the object model, add this import</span></span>

```
 import io.adaptivecards.objectmodel.*;
```

<span data-ttu-id="e8a42-112">Füge den folgenden Import hinzu, um den Renderer einzubeziehen:</span><span class="sxs-lookup"><span data-stu-id="e8a42-112">To include the renderer, add this import</span></span>

```
 import io.adaptivecards.renderer.*;
```

## <a name="next-steps"></a><span data-ttu-id="e8a42-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e8a42-113">Next steps</span></span>

<span data-ttu-id="e8a42-114">Informationen zu den nächsten Schritten findest du unter [Rendern einer Karte](render-a-card.md).</span><span class="sxs-lookup"><span data-stu-id="e8a42-114">See [Render a card](render-a-card.md) for the next steps!</span></span>
