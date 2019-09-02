---
title: Implementieren eines Renderers
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: b39493f82f3378e5a554abc6df890d6821869671
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67138023"
---
# <a name="adaptive-card-renderer-specification"></a><span data-ttu-id="ff795-102">Spezifikation eines Renderers für adaptive Karten</span><span class="sxs-lookup"><span data-stu-id="ff795-102">Adaptive Card Renderer Specification</span></span>

<span data-ttu-id="ff795-103">Die folgende Spezifikation beschreibt die Implementierung eines Renderers für adaptive Karten auf einer beliebigen Benutzeroberflächenplattform.</span><span class="sxs-lookup"><span data-stu-id="ff795-103">The following specification describes how implement an Adaptive Card renderer on any UI platform.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="ff795-104">Dieser Inhalt ist noch nicht final.</span><span class="sxs-lookup"><span data-stu-id="ff795-104">This content is not finished yet.</span></span> <span data-ttu-id="ff795-105">Schau später wieder rein.</span><span class="sxs-lookup"><span data-stu-id="ff795-105">Check back shortly.</span></span>

## <a name="sdk-versioning"></a><span data-ttu-id="ff795-106">SDK-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ff795-106">SDK Versioning</span></span>

1. <span data-ttu-id="ff795-107">Haupt- und Nebenversion des SDKs **SOLLTEN** der `schema`-Version entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ff795-107">The SDK major and minor version **SHOULD** match the `schema` version.</span></span> 
1. <span data-ttu-id="ff795-108">Patch und Build **SOLLTEN** für Rendererupdates angegeben werden, die keine Schemaänderungen umfassen.</span><span class="sxs-lookup"><span data-stu-id="ff795-108">Patch/build **SHOULD** be used for renderer updates that don't have schema changes.</span></span>

## <a name="parsing-json"></a><span data-ttu-id="ff795-109">Analysieren von JSON</span><span class="sxs-lookup"><span data-stu-id="ff795-109">Parsing JSON</span></span>

### <a name="error-conditions"></a><span data-ttu-id="ff795-110">Fehlerbedingungen</span><span class="sxs-lookup"><span data-stu-id="ff795-110">Error conditions</span></span>
1. <span data-ttu-id="ff795-111">Ein Parser **MUSS** prüfen, ob es sich um gültigen JSON-Inhalt handelt.</span><span class="sxs-lookup"><span data-stu-id="ff795-111">A parser **MUST** check that it's valid JSON content</span></span>
1. <span data-ttu-id="ff795-112">Ein Parser **MUSS** eine Überprüfung anhand des Schemas (erforderliche Eigenschaften usw.) ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff795-112">A parser **MUST** validate against the schema (required properties, etc)</span></span>
1. <span data-ttu-id="ff795-113">Die oben genannten Fehler **MÜSSEN** der Host-App gemeldet werden (als Ausnahme oder eine entsprechende Angabe).</span><span class="sxs-lookup"><span data-stu-id="ff795-113">The above errors **MUST** be reported to the host app (exception or equivalent)</span></span>

### <a name="unknown-types"></a><span data-ttu-id="ff795-114">Unbekannte Typen</span><span class="sxs-lookup"><span data-stu-id="ff795-114">Unknown types</span></span>
1. <span data-ttu-id="ff795-115">Wenn unbekannte „Typen“ ermittelt werden, **MÜSSEN DIESE AUS DEM ERGEBNIS GELÖSCHT** werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-115">If unknown "types" are encountered they **MUST BE DROPPED** from the result</span></span>
1. <span data-ttu-id="ff795-116">Alle Änderungen der Nutzlast (wie oben) **SOLLTEN** der Host-App als Warnungen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-116">Any alterations of the payload (like above) **SHOULD** be reported as warnings to the host app</span></span>

### <a name="unknown-properties"></a><span data-ttu-id="ff795-117">Unbekannte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ff795-117">Unknown properties</span></span>
1. <span data-ttu-id="ff795-118">Ein Parser **MUSS** **zusätzliche** Eigenschaften in Elementen einschließen.</span><span class="sxs-lookup"><span data-stu-id="ff795-118">A parser **MUST** include **additional** properties on elements</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="ff795-119">Weitere Aspekte</span><span class="sxs-lookup"><span data-stu-id="ff795-119">Additional considerations</span></span>
1. <span data-ttu-id="ff795-120">Die Eigenschaft `speak` kann SSML-Markup enthalten und **MUSS** wie angegeben an die Host-App zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-120">The `speak` property may contain SSML markup and **MUST** be returned to the host app as-specified</span></span>

## <a name="parsing-host-config"></a><span data-ttu-id="ff795-121">Analyse der Hostkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ff795-121">Parsing Host Config</span></span>
1. <span data-ttu-id="ff795-122">TODO</span><span class="sxs-lookup"><span data-stu-id="ff795-122">TODO</span></span>

## <a name="versioning"></a><span data-ttu-id="ff795-123">Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="ff795-123">Versioning</span></span>

1. <span data-ttu-id="ff795-124">Ein Renderer **MUSS** eine bestimmte Version des Schemas implementieren.</span><span class="sxs-lookup"><span data-stu-id="ff795-124">A renderer **MUST** implement a particular version of the schema.</span></span> 
1. <span data-ttu-id="ff795-125">Der `AdaptiveCard`-Konstruktor **MUSS** der Eigenschaft `version` einen Standardwert basierend auf der aktuellen Schemaversion zuweisen.</span><span class="sxs-lookup"><span data-stu-id="ff795-125">The `AdaptiveCard` constructor **MUST** give the `version` property a default value based on the current schema version</span></span> 
1. <span data-ttu-id="ff795-126">Wenn ein Renderer eine `version`-Eigenschaft in einer `AdaptiveCard` findet, die höher ist als die unterstützte Version, **MUSS** er stattdessen den `fallbackText` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ff795-126">If a renderer encounters a `version` property in the `AdaptiveCard` that is higher than the supported version, it **MUST** return the `fallbackText` instead.</span></span>

## <a name="rendering"></a><span data-ttu-id="ff795-127">Rendering</span><span class="sxs-lookup"><span data-stu-id="ff795-127">Rendering</span></span>

<span data-ttu-id="ff795-128">Eine `AdaptiveCard` besteht aus einem `body`- und einem `actions`-Element.</span><span class="sxs-lookup"><span data-stu-id="ff795-128">An `AdaptiveCard` consists of a `body` and `actions`.</span></span> <span data-ttu-id="ff795-129">Der `body` ist eine Sammlung von `CardElement`-Elementen, die von einem Renderer enumeriert und in der entsprechenden Reihenfolge gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-129">The `body` is a collection of `CardElement`s that a renderer will enumerate and render in order.</span></span> 

1. <span data-ttu-id="ff795-130">Jedes Element **MUSS** auf die Breite des übergeordneten Elements gestreckt werden (ähnlich wie bei `display: block` in HTML).</span><span class="sxs-lookup"><span data-stu-id="ff795-130">Each Element **MUST** stretch to the width of its parent (think `display: block` in HTML).</span></span>
1. <span data-ttu-id="ff795-131">Ein Renderer **MUSS** unbekannte Elementtypen ignorieren und mit dem Rest der Nutzlast fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ff795-131">A renderer **MUST** ignore unknown element types, and continue rendering the rest of the payload.</span></span>

### <a name="spacing-and-separators"></a><span data-ttu-id="ff795-132">Abstände und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="ff795-132">Spacing and Separators</span></span>

1. <span data-ttu-id="ff795-133">Die `spacing`-Eigenschaft jedes Elements wirkt sich darauf aus, wie viel Abstand zwischen dem **AKTUELLEN** Element und dem Element **DAVOR** vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-133">The `spacing` property on every element influences the amount of space between the **CURRENT** element and the one **BEFORE** it.</span></span>
1. <span data-ttu-id="ff795-134">Ein Abstand **DARF NUR DANN** angewendet werden, wenn vor dem Element tatsächlich ein anderes Element vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-134">Spacing **MUST ONLY** apply when there actually is an element preceding it.</span></span> <span data-ttu-id="ff795-135">(Diese Eigenschaft gilt also nicht für das erste Element in einem Array).</span><span class="sxs-lookup"><span data-stu-id="ff795-135">(E.g., won't apply to the first item in an array)</span></span>
1. <span data-ttu-id="ff795-136">Ein Renderer **MUSS** den zu verwendenden Abstand aus `hostConfig` für den Enumerationswert ablesen, der auf das aktuelle Element angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff795-136">A renderer **MUST** look up the amount of space to use from the `hostConfig` spacing for the enum value applied to the current element.</span></span>
1. <span data-ttu-id="ff795-137">Wenn das Element den `separator`-Wert `true` aufweist, **MUSS** eine sichtbare Linie zwischen dem aktuellen Element und dem Element davor gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-137">If the element has a `separator` value of `true`, then a visible line **MUST** be drawn between the current element and the one before it.</span></span>
1. <span data-ttu-id="ff795-138">Die Trennlinie **MUSS** mithilfe der Eigenschaft `container.style.default.foregroundColor` gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-138">The separator line **MUST** be drawn using the `container.style.default.foregroundColor`.</span></span>
1. <span data-ttu-id="ff795-139">Eine Trennlinie **DARF NUR** gezeichnet werden, wenn das Element **NICHT** das erste Element im Array ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-139">A separator **MUST ONLY** be drawn if the item **IS NOT** the first in the array.</span></span>

### <a name="columns"></a><span data-ttu-id="ff795-140">Spalten</span><span class="sxs-lookup"><span data-stu-id="ff795-140">Columns</span></span>

1. <span data-ttu-id="ff795-141">`Column` `width` **MUSS** als „auto“, „stretch“ oder als gewichtetes Verhältnis interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-141">`Column` `width` **MUST** be interpreted by "auto", "stretch" or a weighted ratio.</span></span>

### <a name="textblock"></a><span data-ttu-id="ff795-142">TextBlock</span><span class="sxs-lookup"><span data-stu-id="ff795-142">TextBlock</span></span>

1. <span data-ttu-id="ff795-143">Ein TextBlock **MUSS** eine einzelne Zeile aufnehmen, sofern die `wrap`-Eigenschaft nicht `true` lautet.</span><span class="sxs-lookup"><span data-stu-id="ff795-143">A TextBlock **MUST** take up a single line unless the `wrap` property is `true`.</span></span> 
1. <span data-ttu-id="ff795-144">Der Textblock **SOLLTE** überschüssigen Text abschneiden und Auslassungspunkte (...) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff795-144">The text block **SHOULD** trim any excess text with an ellipsis (...)</span></span>

#### <a name="markdown"></a><span data-ttu-id="ff795-145">Markdown</span><span class="sxs-lookup"><span data-stu-id="ff795-145">Markdown</span></span>

1. <span data-ttu-id="ff795-146">Adaptive Karten lassen eine Teilmenge von Markdown zu und **SOLLTEN** in `TextBlock` unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-146">Adaptive Cards allow for a subset of Markdown and **SHOULD** be supported in `TextBlock`.</span></span> 
1. <span data-ttu-id="ff795-147">Weitere Informationen findest du unter [Markdownanforderungen](../authoring-cards/text-features.md).</span><span class="sxs-lookup"><span data-stu-id="ff795-147">See full [markdown requirements](../authoring-cards/text-features.md)</span></span>

#### <a name="formatting-functions"></a><span data-ttu-id="ff795-148">Formatierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="ff795-148">Formatting functions</span></span>

1. <span data-ttu-id="ff795-149">`TextBlock` ermöglicht [Formatierungsfunktionen für DATUM und UHRZEIT](../authoring-cards/text-features.md), die in jedem Renderer unterstützt werden **MÜSSEN**.</span><span class="sxs-lookup"><span data-stu-id="ff795-149">`TextBlock` allows [DATE/TIME formatting functions](../authoring-cards/text-features.md) that **MUST** be supported on every renderer.</span></span>
1. <span data-ttu-id="ff795-150">**BEI ALLEN FEHLERN MUSS** die unformatierte Zeichenfolge auf der Karte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-150">**ALL FAILURES MUST** display the raw string in the card.</span></span> <span data-ttu-id="ff795-151">Es wird keine benutzerfreundliche Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff795-151">No friendly message attempted.</span></span> <span data-ttu-id="ff795-152">(Ziel hierbei ist es, den Entwickler sofort darauf aufmerksam zu machen, dass ein Problem vorliegt).</span><span class="sxs-lookup"><span data-stu-id="ff795-152">(The goal being to make the developer immediately aware there is a problem)</span></span>

1. <span data-ttu-id="ff795-153">TODO: Einschließen von regulären Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="ff795-153">TODO: Include regex</span></span>

### <a name="images"></a><span data-ttu-id="ff795-154">Abbilder</span><span class="sxs-lookup"><span data-stu-id="ff795-154">Images</span></span>

1. <span data-ttu-id="ff795-155">Ein Renderer **SOLLTE** Host-Apps informieren, wenn alle HTTP-Bilder heruntergeladen wurden und die Karte „vollständig gerendert“ ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-155">A renderer **SHOULD** allow host apps to know when all HTTP images have been downloaded and the card is "fully rendered"</span></span>
1. <span data-ttu-id="ff795-156">Ein Renderer **MUSS** beim Herunterladen von HTTP-Bildern den Hostkonfigurationsparameter `maxImageSize` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ff795-156">A renderer **MUST** inspect the Host Config `maxImageSize` param when downloading HTTP images</span></span>
1. <span data-ttu-id="ff795-157">Ein Renderer **MUSS** `.png` und `.jpeg` unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ff795-157">A renderer **MUST** support `.png` and `.jpeg`</span></span>
1. <span data-ttu-id="ff795-158">Ein Renderer **SOLLTE** `.gif`-Bilder unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ff795-158">A renderer **SHOULD** support `.gif` images</span></span>

### <a name="host-config"></a><span data-ttu-id="ff795-159">Hostkonfiguration</span><span class="sxs-lookup"><span data-stu-id="ff795-159">Host Config</span></span>

* <span data-ttu-id="ff795-160">TODO: Wie sollten die Standardwerte lauten?</span><span class="sxs-lookup"><span data-stu-id="ff795-160">TODO: What should the defaults be?</span></span> <span data-ttu-id="ff795-161">Sollten diese überall freigegeben werden?</span><span class="sxs-lookup"><span data-stu-id="ff795-161">Should they all share it?</span></span> <span data-ttu-id="ff795-162">Sollten wir eine gemeinsame hostConfig.json-Datei in den Binärdateien einbetten?</span><span class="sxs-lookup"><span data-stu-id="ff795-162">Should we embed a common hostConfig.json file in the binaries?</span></span>
* <span data-ttu-id="ff795-163">TODO: Ich denke, HostConfig sollte auch für die Analyse versioniert werden?</span><span class="sxs-lookup"><span data-stu-id="ff795-163">TODO: I think HostConfig needs to be versioned as well for parsing?</span></span>

<span data-ttu-id="ff795-164">[`HostConfig`](host-config.md) ist ein gemeinsam genutztes Konfigurationsobjekt, das angibt, wie ein Renderer für adaptive Karten eine Benutzeroberfläche generiert.</span><span class="sxs-lookup"><span data-stu-id="ff795-164">[`HostConfig`](host-config.md) is a shared configuration object that specifies how an Adaptive Card Renderer generates UI.</span></span>  

<span data-ttu-id="ff795-165">So können plattformunabhängige Eigenschaften für Renderer auf verschiedenen Plattformen und Geräten freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-165">This allows properties which are platform agnostic to be shared among renderers on different platforms and devices.</span></span> <span data-ttu-id="ff795-166">Zudem können Tools erstellt werden, die dir eine Vorstellung vom Aussehen und Verhalten einer Karte in einer bestimmten Umgebung vermitteln.</span><span class="sxs-lookup"><span data-stu-id="ff795-166">It also allows tooling to be created which gives you an idea of the look and feel that card would have for a given environment.</span></span>

1. <span data-ttu-id="ff795-167">Renderer **MÜSSEN** einen **HostConfig**-Parameter für Host-Apps verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ff795-167">Renderers **MUST** expose a **Host Config** parameter to host apps</span></span>
1. <span data-ttu-id="ff795-168">Alle Elemente **MÜSSEN** entsprechend ihren jeweiligen HostConfig-Einstellungen formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-168">All elements **MUST** be styled according to their respective Host Config settings</span></span>

### <a name="native-platform-styling"></a><span data-ttu-id="ff795-169">Native Plattformformatierung</span><span class="sxs-lookup"><span data-stu-id="ff795-169">Native platform styling</span></span>

1. <span data-ttu-id="ff795-170">Jeder Elementtyp **SOLLTE** eine native Plattformformatierung mit dem generierten Benutzeroberflächenelement anfügen.</span><span class="sxs-lookup"><span data-stu-id="ff795-170">Each element type **SHOULD** attach a native platform style with the generated UI element.</span></span> <span data-ttu-id="ff795-171">In HTML haben wir beispielsweise eine CSS-Klasse zu den Elementtypen hinzugefügt, und in XAML weisen wir einen bestimmten Stil zu.</span><span class="sxs-lookup"><span data-stu-id="ff795-171">E.g., in HTML we added a CSS class to the element types, and in XAML we assign a specific Style.</span></span>

## <a name="extensibility"></a><span data-ttu-id="ff795-172">Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ff795-172">Extensibility</span></span> 

1. <span data-ttu-id="ff795-173">Ein Renderer **MUSS** es Host-Apps ermöglichen, standardmäßige Elementrenderer zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ff795-173">A renderer **MUST** allow host apps to override default element renderers.</span></span> <span data-ttu-id="ff795-174">Beispiel: Ersetzen des Renderns von `TextBlock` durch eigene Logik.</span><span class="sxs-lookup"><span data-stu-id="ff795-174">E.g., replace `TextBlock` rendering with their own logic.</span></span>
1. <span data-ttu-id="ff795-175">Ein Renderer **MUSS** es Host-Apps ermöglichen, benutzerdefinierte Elementtypen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ff795-175">A renderer **MUST** allow host apps to register custom element types.</span></span> <span data-ttu-id="ff795-176">Beispiel: Hinzufügen von Unterstützung für ein benutzerdefiniertes `Rating`-Element.</span><span class="sxs-lookup"><span data-stu-id="ff795-176">E.g., add support for a custom `Rating` element</span></span>
1. <span data-ttu-id="ff795-177">Ein Renderer **MUSS** es Host-Apps ermöglichen, Unterstützung für ein Standardelement zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ff795-177">A renderer **MUST** allow host apps to remove support for a default element.</span></span> <span data-ttu-id="ff795-178">Beispiel: Entfernen von `Action.Submit`, wenn die Unterstützung nicht gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-178">E.g., remove `Action.Submit` if they don't want it supported.</span></span>

## <a name="actions"></a><span data-ttu-id="ff795-179">Aktionen</span><span class="sxs-lookup"><span data-stu-id="ff795-179">Actions</span></span>

1. <span data-ttu-id="ff795-180">Ein Renderer **DARF KEINE** Aktionen rendern, wenn das `supportsInteractivity`-Element in der HostConfig `false` ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-180">If HostConfig `supportsInteractivity` is `false`, a renderer **MUST NOT** render any actions.</span></span>
1. <span data-ttu-id="ff795-181">Die `actions`-Eigenschaft **MUSS** als Schaltflächen auf einer Form von Aktionsleiste gerendert werden, üblicherweise am unteren Rand der Karte.</span><span class="sxs-lookup"><span data-stu-id="ff795-181">The `actions` property **MUST** be rendered as buttons in some kind of action bar, usually at the bottom of the card.</span></span> 
1. <span data-ttu-id="ff795-182">Wenn eine Schaltfläche aktiviert wird, **MUSS** die Host-App das Ereignis verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="ff795-182">When a button is tapped it **MUST** allow the host app to handle the event.</span></span> 
1. <span data-ttu-id="ff795-183">Das Ereignis **MUSS** alle zugeordneten Eigenschaften mit der Aktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="ff795-183">The event **MUST** pass along all associated properties with the action</span></span>
1. <span data-ttu-id="ff795-184">Das Ereignis **MUSS** die ausgeführte `AdaptiveCard` übergeben.</span><span class="sxs-lookup"><span data-stu-id="ff795-184">The event **MUST** pass along the `AdaptiveCard` which was executed</span></span>

<span data-ttu-id="ff795-185">Aktion</span><span class="sxs-lookup"><span data-stu-id="ff795-185">Action</span></span> | <span data-ttu-id="ff795-186">Verhalten</span><span class="sxs-lookup"><span data-stu-id="ff795-186">Behavior</span></span>
--- | ---
<span data-ttu-id="ff795-187">**Action.OpenUrl**</span><span class="sxs-lookup"><span data-stu-id="ff795-187">**Action.OpenUrl**</span></span> | <span data-ttu-id="ff795-188">Öffnet eine externe URL zur Anzeige.</span><span class="sxs-lookup"><span data-stu-id="ff795-188">Open an external URL for viewing</span></span>
<span data-ttu-id="ff795-189">**Action.ShowCard**</span><span class="sxs-lookup"><span data-stu-id="ff795-189">**Action.ShowCard**</span></span> | <span data-ttu-id="ff795-190">Fordert eine untergeordnete Karte an, die dem Benutzer angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff795-190">Requests a sub-card to be shown to the user.</span></span>
<span data-ttu-id="ff795-191">**Action.Submit**</span><span class="sxs-lookup"><span data-stu-id="ff795-191">**Action.Submit**</span></span> | <span data-ttu-id="ff795-192">Fordert an, dass alle Eingabeelemente in einem Objekt zusammengefasst werden, das dir anschließend über eine von der Hostanwendung definierte Methode gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="ff795-192">Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

### <a name="actionopenurl"></a><span data-ttu-id="ff795-193">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="ff795-193">Action.OpenUrl</span></span>
1. <span data-ttu-id="ff795-194">`Action.OpenUrl` **SOLLTE** mithilfe des nativen Plattformmechanismus eine URL öffnen.</span><span class="sxs-lookup"><span data-stu-id="ff795-194">`Action.OpenUrl` **SHOULD** open a URL using the native platform mechanism</span></span>
1. <span data-ttu-id="ff795-195">Wenn dies nicht möglich ist, **MUSS** die Aktion ein Ereignis auslösen, damit die Host-App das Öffnen der URL verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ff795-195">If this is not possible it **MUST** raise an event to the host app to handle opening the URL.</span></span> <span data-ttu-id="ff795-196">Dieses Ereignis **MUSS** es der Host-App ermöglichen, das Standardverhalten zu überschreiben,</span><span class="sxs-lookup"><span data-stu-id="ff795-196">This event **MUST** allow the host app to override the default behavior.</span></span> <span data-ttu-id="ff795-197">beispielsweise durch Öffnen der URL innerhalb der eigenen App.</span><span class="sxs-lookup"><span data-stu-id="ff795-197">E.g., let them open the URL within their own app.</span></span>

### <a name="actionshowcard"></a><span data-ttu-id="ff795-198">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="ff795-198">Action.ShowCard</span></span>

1. <span data-ttu-id="ff795-199">`Action.ShowCard` **MUSS** auf irgendeine Weise unterstützt werden, basierend auf der HostConfig-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ff795-199">`Action.ShowCard` **MUST** be supported in some way, based on the hostConfig setting.</span></span> <span data-ttu-id="ff795-200">Es gibt zwei Modi: Inline und Popup.</span><span class="sxs-lookup"><span data-stu-id="ff795-200">There are two modes: inline, and popup.</span></span> <span data-ttu-id="ff795-201">Inlinekarten **SOLLTEN** die Sichtbarkeit der Karte automatisch umschalten.</span><span class="sxs-lookup"><span data-stu-id="ff795-201">Inline cards **SHOULD** toggle the card visibility automatically.</span></span> <span data-ttu-id="ff795-202">Im Popupmodus **SOLLTE** ein Ereignis ausgelöst werden, damit die Host-App die Karte auf irgendeine Weise anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ff795-202">In popup mode, an event **SHOULD** be fired to the host app to show the card in some way.</span></span>

### <a name="actionsubmit"></a><span data-ttu-id="ff795-203">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="ff795-203">Action.Submit</span></span>

<span data-ttu-id="ff795-204">Die Submit-Aktion verhält sich wie eine Übermittlungsaktion in einem HTML-Formular, mit einer Ausnahme: In HTML wird typischerweise eine HTTP-POST-Aktion ausgelöst, bei adaptiven Karten dagegen bleibt der Host-App die Entscheidung überlassen, wie „submit“ zu interpretieren ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-204">The Submit Action behaves like an HTML form submit, except that where HTML typically triggers an HTTP post, Adaptive Cards leaves it up to each host app to determine what "submit" means to them.</span></span> 

1. <span data-ttu-id="ff795-205">Wenn ein Ereignis ausgelöst werden **MUSS**, tippt der Benutzer auf die aufgerufene Aktion.</span><span class="sxs-lookup"><span data-stu-id="ff795-205">When this **MUST** raise an event the user taps the action invoked.</span></span>  
1. <span data-ttu-id="ff795-206">Die `data`-Eigenschaft **MUSS** in der Rückrufnutzlast enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ff795-206">The `data` property **MUST** be included in the callback payload.</span></span>
1. <span data-ttu-id="ff795-207">Bei `Action.Submit` **MUSS** ein Renderer alle Eingaben auf der Karte erfassen und die zugehörigen Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="ff795-207">For `Action.Submit`, a renderer **MUST** gather all inputs on the card and retrieve their values.</span></span> 

### <a name="selectaction"></a><span data-ttu-id="ff795-208">selectAction</span><span class="sxs-lookup"><span data-stu-id="ff795-208">selectAction</span></span>

1. <span data-ttu-id="ff795-209">Eine `selectAction` **DARF NICHT** als Berührungsziel gerendert werden, wenn das `supportedInteractivity`-Element der Hostkonfiguration `false` ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-209">If Host Config `supportedInteractivity` is `false` then a `selectAction` **MUST NOT** render as a touch target.</span></span>
1. <span data-ttu-id="ff795-210">`Image`, `ColumnSet` und `Column` bieten eine `selectAction`-Eigenschaft, die ausgeführt werden **SOLLTE**, wenn sie von einem Benutzer z. B. durch Tippen auf das Element aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ff795-210">`Image`, `ColumnSet`, and `Column` offer a `selectAction` property, which **SHOULD** be executed when the user invokes it, e.g., by tapping the element.</span></span>

## <a name="inputs"></a><span data-ttu-id="ff795-211">Eingaben</span><span class="sxs-lookup"><span data-stu-id="ff795-211">Inputs</span></span>

1. <span data-ttu-id="ff795-212">Ein Renderer **DARF KEINE** Eingaben rendern, wenn das `supportsInteractivity`-Element der HostConfig `false` ist.</span><span class="sxs-lookup"><span data-stu-id="ff795-212">If HostConfig `supportsInteractivity` is `false` a renderer **MUST NOT** render any inputs.</span></span>
2. <span data-ttu-id="ff795-213">Eingaben **SOLLTEN** mit der höchstmöglichen Genauigkeit gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-213">Inputs **SHOULD** render with the highest fidelity possible.</span></span> <span data-ttu-id="ff795-214">Ein `Input.Date`-Element beispielsweise sollte dem Benutzer idealerweise eine Datumsauswahl bieten. Wenn dies jedoch in deinem UI-Stapel nicht möglich ist, **MUSS** der Renderer ein Standardtextfeld rendern.</span><span class="sxs-lookup"><span data-stu-id="ff795-214">For example, an `Input.Date` would ideally offer a date picker to a user, but if this isn't possible on your UI stack, then the renderer **MUST** fall back to rendering a standard text box.</span></span>
3. <span data-ttu-id="ff795-215">Ein Renderer **SOLLTE** nach Möglichkeit `placeholderText` anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ff795-215">A renderer **SHOULD** display the `placeholderText` if possible</span></span>
4. <span data-ttu-id="ff795-216">Ein Renderer **MUSS KEINE** Überprüfung der Eingabe implementieren.</span><span class="sxs-lookup"><span data-stu-id="ff795-216">A renderer **DOES NOT** have to implement validation of the input.</span></span> <span data-ttu-id="ff795-217">Benutzer von adaptiven Karten müssen die Überprüfung empfangener Daten auf ihrer Seite selbst planen.</span><span class="sxs-lookup"><span data-stu-id="ff795-217">Users of Adaptive Cards must plan to validate any received data on their end.</span></span>
5. <span data-ttu-id="ff795-218">Die Bindung von Eingabewerten **MUSS** ordnungsgemäß mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="ff795-218">Input value binding **MUST** be properly escaped</span></span>

6. <span data-ttu-id="ff795-219">Das Objekt **MUSS** folgendermaßen an die Host-App zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ff795-219">The object **MUST** be returned to the host app as follows:</span></span>

   <span data-ttu-id="ff795-220">Wir können keinerlei Zusagen hinsichtlich der Eingabeüberprüfung in adaptiven Karten machen, daher obliegt es dem Empfänger, Antworten ordnungsgemäß zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="ff795-220">We do not make any promises of input validation in adaptive cards, so it's up to the receiving party to properly parse the response.</span></span> <span data-ttu-id="ff795-221">„Input.Number“ könnte beispielsweise „Hallo“ zurückgeben, und die Empfänger müssen darauf vorbereitet sein.</span><span class="sxs-lookup"><span data-stu-id="ff795-221">E.g., a Input.Number could return "hello" and they need to be prepared for that.</span></span>


## <a name="events"></a><span data-ttu-id="ff795-222">Veranstaltungen</span><span class="sxs-lookup"><span data-stu-id="ff795-222">Events</span></span>

1. <span data-ttu-id="ff795-223">Ein Renderer **SOLLTE** ein Ereignis auslösen, wenn sich die Sichtbarkeit eines Elements geändert hat, sodass die Host-App die Karte an die richtige Position verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="ff795-223">A renderer **SHOULD** fire an event when an element's visibility has changed, allowing the host app to scroll the card into position.</span></span>
