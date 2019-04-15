---
title: Implementieren eines Renderers
author: matthidinger
ms.author: mahiding
ms.date: 09/15/2017
ms.topic: article
ms.openlocfilehash: 3c79d768d5c979626b66614a1856ad6c2e390805
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552552"
---
# <a name="adaptive-card-renderer-specification"></a><span data-ttu-id="33f29-102">Adaptive Card Renderer-Spezifikation</span><span class="sxs-lookup"><span data-stu-id="33f29-102">Adaptive Card Renderer Specification</span></span>

<span data-ttu-id="33f29-103">Die folgende Spezifikation wird beschrieben, wie eine Adaptive Card-Renderer auf alle UI-Plattform implementieren.</span><span class="sxs-lookup"><span data-stu-id="33f29-103">The following specification describes how implement an Adaptive Card renderer on any UI platform.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="33f29-104">Dieser Inhalt ist noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="33f29-104">This content is not finished yet.</span></span> <span data-ttu-id="33f29-105">Später wieder.</span><span class="sxs-lookup"><span data-stu-id="33f29-105">Check back shortly.</span></span>

## <a name="sdk-versioning"></a><span data-ttu-id="33f29-106">SDK-Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="33f29-106">SDK Versioning</span></span>

1. <span data-ttu-id="33f29-107">Die SDK-Version für Haupt- und Nebenversionsnummern **sollte** entsprechen den `schema` Version.</span><span class="sxs-lookup"><span data-stu-id="33f29-107">The SDK major and minor version **SHOULD** match the `schema` version.</span></span> 
1. <span data-ttu-id="33f29-108">Patch/Build **sollte** für Renderer müssen Updates, die schemaänderungen nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-108">Patch/build **SHOULD** be used for renderer updates that don't have schema changes.</span></span>

## <a name="parsing-json"></a><span data-ttu-id="33f29-109">JSON-Analyse</span><span class="sxs-lookup"><span data-stu-id="33f29-109">Parsing JSON</span></span>

### <a name="error-conditions"></a><span data-ttu-id="33f29-110">Fehlerbedingungen</span><span class="sxs-lookup"><span data-stu-id="33f29-110">Error conditions</span></span>
1. <span data-ttu-id="33f29-111">Ein Parser **müssen** überprüfen Sie, dass es sich um gültigen JSON-Inhalt ist</span><span class="sxs-lookup"><span data-stu-id="33f29-111">A parser **MUST** check that it's valid JSON content</span></span>
1. <span data-ttu-id="33f29-112">Ein Parser **müssen** überprüfen mithilfe des Schemas (erforderlichen Eigenschaften usw.)</span><span class="sxs-lookup"><span data-stu-id="33f29-112">A parser **MUST** validate against the schema (required properties, etc)</span></span>
1. <span data-ttu-id="33f29-113">Die oben genannten Fehler **müssen** gemeldet werden, für die Host-app (Ausnahme oder Äquivalent)</span><span class="sxs-lookup"><span data-stu-id="33f29-113">The above errors **MUST** be reported to the host app (exception or equivalent)</span></span>

### <a name="unknown-types"></a><span data-ttu-id="33f29-114">Unbekannte Typen</span><span class="sxs-lookup"><span data-stu-id="33f29-114">Unknown types</span></span>
1. <span data-ttu-id="33f29-115">Wenn unbekannte "Typen" auftreten, werden sie **müssen gelöscht werden,** aus dem Ergebnis</span><span class="sxs-lookup"><span data-stu-id="33f29-115">If unknown "types" are encountered they **MUST BE DROPPED** from the result</span></span>
1. <span data-ttu-id="33f29-116">Alle Änderungen der Nutzlast (wie weiter oben) **sollte** als Warnungen an, die Host-app gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="33f29-116">Any alterations of the payload (like above) **SHOULD** be reported as warnings to the host app</span></span>

### <a name="unknown-properties"></a><span data-ttu-id="33f29-117">Eigenschaften von Unbekannter</span><span class="sxs-lookup"><span data-stu-id="33f29-117">Unknown properties</span></span>
1. <span data-ttu-id="33f29-118">Ein Parser **müssen** enthalten **zusätzliche** Eigenschaften für Elemente</span><span class="sxs-lookup"><span data-stu-id="33f29-118">A parser **MUST** include **additional** properties on elements</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="33f29-119">Weitere Aspekte</span><span class="sxs-lookup"><span data-stu-id="33f29-119">Additional considerations</span></span>
1. <span data-ttu-id="33f29-120">Die `speak` -Eigenschaft kann die SSML-Code enthalten und **müssen** zurückgegeben werden, für die Host-app, die als angegeben</span><span class="sxs-lookup"><span data-stu-id="33f29-120">The `speak` property may contain SSML markup and **MUST** be returned to the host app as-specified</span></span>

## <a name="parsing-host-config"></a><span data-ttu-id="33f29-121">Analysieren der Host-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="33f29-121">Parsing Host Config</span></span>
1. <span data-ttu-id="33f29-122">TODO</span><span class="sxs-lookup"><span data-stu-id="33f29-122">TODO</span></span>

## <a name="versioning"></a><span data-ttu-id="33f29-123">Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="33f29-123">Versioning</span></span>

1. <span data-ttu-id="33f29-124">Ein Renderer **müssen** implementieren Sie eine bestimmte Version des Schemas.</span><span class="sxs-lookup"><span data-stu-id="33f29-124">A renderer **MUST** implement a particular version of the schema.</span></span> 
1. <span data-ttu-id="33f29-125">Die `AdaptiveCard` Konstruktor **müssen** geben die `version` Eigenschaft ein Standardwert auf der aktuellen Schemaversion basierend</span><span class="sxs-lookup"><span data-stu-id="33f29-125">The `AdaptiveCard` constructor **MUST** give the `version` property a default value based on the current schema version</span></span> 
1. <span data-ttu-id="33f29-126">Wenn ein Renderer auftritt ein `version` -Eigenschaft in der `AdaptiveCard` ist höher als die unterstützte Version, es **müssen** Zurückgeben der `fallbackText` stattdessen.</span><span class="sxs-lookup"><span data-stu-id="33f29-126">If a renderer encounters a `version` property in the `AdaptiveCard` that is higher than the supported version, it **MUST** return the `fallbackText` instead.</span></span>

## <a name="rendering"></a><span data-ttu-id="33f29-127">Rendering</span><span class="sxs-lookup"><span data-stu-id="33f29-127">Rendering</span></span>

<span data-ttu-id="33f29-128">Ein `AdaptiveCard` besteht aus einem `body` und `actions`.</span><span class="sxs-lookup"><span data-stu-id="33f29-128">An `AdaptiveCard` consists of a `body` and `actions`.</span></span> <span data-ttu-id="33f29-129">Die `body` ist eine Sammlung von `CardElement`s, die ein Renderer aufgelistet und in der Reihenfolge gerendert.</span><span class="sxs-lookup"><span data-stu-id="33f29-129">The `body` is a collection of `CardElement`s that a renderer will enumerate and render in order.</span></span> 

1. <span data-ttu-id="33f29-130">Jedes Element **müssen** Stretch der Breite seines übergeordneten Elements (denken `display: block` im HTML-Format).</span><span class="sxs-lookup"><span data-stu-id="33f29-130">Each Element **MUST** stretch to the width of its parent (think `display: block` in HTML).</span></span>
1. <span data-ttu-id="33f29-131">Ein Renderer **müssen** unbekannte Elementtypen ignorieren und fortfahren, Rendern den Rest der Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="33f29-131">A renderer **MUST** ignore unknown element types, and continue rendering the rest of the payload.</span></span>

### <a name="spacing-and-separators"></a><span data-ttu-id="33f29-132">Abstand und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="33f29-132">Spacing and Separators</span></span>

1. <span data-ttu-id="33f29-133">Die `spacing` Eigenschaft für jedes Element wirkt sich auf den Abstand zwischen den **aktuelle** -Element und der **vor** es.</span><span class="sxs-lookup"><span data-stu-id="33f29-133">The `spacing` property on every element influences the amount of space between the **CURRENT** element and the one **BEFORE** it.</span></span>
1. <span data-ttu-id="33f29-134">Der Abstand **muss nur** angewendet, wenn tatsächlich ein Element mit dem vorhergehenden.</span><span class="sxs-lookup"><span data-stu-id="33f29-134">Spacing **MUST ONLY** apply when there actually is an element preceding it.</span></span> <span data-ttu-id="33f29-135">(Z. B. nicht auf das erste Element in einem Array anwenden)</span><span class="sxs-lookup"><span data-stu-id="33f29-135">(E.g., won't apply to the first item in an array)</span></span>
1. <span data-ttu-id="33f29-136">Ein Renderer **müssen** suchen Sie die Menge des Speicherplatzes für die Verwendung von der `hostConfig` Abstand für den Enum-Wert, der auf das aktuelle Element angewendet.</span><span class="sxs-lookup"><span data-stu-id="33f29-136">A renderer **MUST** look up the amount of space to use from the `hostConfig` spacing for the enum value applied to the current element.</span></span>
1. <span data-ttu-id="33f29-137">Wenn das Element verfügt ein `separator` Wert `true`, klicken Sie dann eine sichtbare Zeile **müssen** zwischen dem aktuellen Element und vor es gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-137">If the element has a `separator` value of `true`, then a visible line **MUST** be drawn between the current element and the one before it.</span></span>
1. <span data-ttu-id="33f29-138">Trennlinie **müssen** werden gezeichnet wird, mit der `container.style.default.foregroundColor`.</span><span class="sxs-lookup"><span data-stu-id="33f29-138">The separator line **MUST** be drawn using the `container.style.default.foregroundColor`.</span></span>
1. <span data-ttu-id="33f29-139">Ein Trennzeichen **muss nur** gezeichnet werden, wenn das Element **IS NOT** die zuerst im Array.</span><span class="sxs-lookup"><span data-stu-id="33f29-139">A separator **MUST ONLY** be drawn if the item **IS NOT** the first in the array.</span></span>

### <a name="columns"></a><span data-ttu-id="33f29-140">Spalten</span><span class="sxs-lookup"><span data-stu-id="33f29-140">Columns</span></span>

1. <span data-ttu-id="33f29-141">`Column` `width` **MUSS** von "Auto", "stretch" oder ein Verhältnis von gewichteten interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-141">`Column` `width` **MUST** be interpreted by "auto", "stretch" or a weighted ratio.</span></span>

### <a name="textblock"></a><span data-ttu-id="33f29-142">TextBlock</span><span class="sxs-lookup"><span data-stu-id="33f29-142">TextBlock</span></span>

1. <span data-ttu-id="33f29-143">Ein TextBlock-Element **müssen** dauern, bis eine einzelne Zeile, wenn die `wrap` Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="33f29-143">A TextBlock **MUST** take up a single line unless the `wrap` property is `true`.</span></span> 
1. <span data-ttu-id="33f29-144">Der TextBlock **sollte** überschüssige Text mit einem Auslassungszeichen (...) kürzen</span><span class="sxs-lookup"><span data-stu-id="33f29-144">The text block **SHOULD** trim any excess text with an ellipsis (...)</span></span>

#### <a name="markdown"></a><span data-ttu-id="33f29-145">Markdown</span><span class="sxs-lookup"><span data-stu-id="33f29-145">Markdown</span></span>

1. <span data-ttu-id="33f29-146">Mit Adaptive Cards können für eine Teilmenge von Markdown und **sollte** in unterstützt `TextBlock`.</span><span class="sxs-lookup"><span data-stu-id="33f29-146">Adaptive Cards allow for a subset of Markdown and **SHOULD** be supported in `TextBlock`.</span></span> 
1. <span data-ttu-id="33f29-147">Siehe vollständige [Markdown-Anforderungen](../authoring-cards/text-features.md)</span><span class="sxs-lookup"><span data-stu-id="33f29-147">See full [markdown requirements](../authoring-cards/text-features.md)</span></span>

#### <a name="formatting-functions"></a><span data-ttu-id="33f29-148">Formatierungsoptionen</span><span class="sxs-lookup"><span data-stu-id="33f29-148">Formatting functions</span></span>

1. <span data-ttu-id="33f29-149">`TextBlock` ermöglicht das [DATUMS-und UHRZEITFORMATIERUNG Funktionen](../authoring-cards/text-features.md) , **müssen** auf jeder Renderer unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-149">`TextBlock` allows [DATE/TIME formatting functions](../authoring-cards/text-features.md) that **MUST** be supported on every renderer.</span></span>
1. <span data-ttu-id="33f29-150">**ALLE Fehler müssen** die unformatierte Zeichenfolge in der Karte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33f29-150">**ALL FAILURES MUST** display the raw string in the card.</span></span> <span data-ttu-id="33f29-151">Keine Meldung versucht.</span><span class="sxs-lookup"><span data-stu-id="33f29-151">No friendly message attempted.</span></span> <span data-ttu-id="33f29-152">(Das Ziel, die mit den Entwickler es sofort aufmerksam zu machen ist ein Problem aufgetreten.)</span><span class="sxs-lookup"><span data-stu-id="33f29-152">(The goal being to make the developer immediately aware there is a problem)</span></span>

1. <span data-ttu-id="33f29-153">TODO: Einschließen von regex</span><span class="sxs-lookup"><span data-stu-id="33f29-153">TODO: Include regex</span></span>

### <a name="images"></a><span data-ttu-id="33f29-154">Abbilder</span><span class="sxs-lookup"><span data-stu-id="33f29-154">Images</span></span>

1. <span data-ttu-id="33f29-155">Ein Renderer **sollte** zulassen apps hosten, wissen Sie, wenn alle HTTP-Images heruntergeladen wurden und dass die Karte "vollständig Rendererd"</span><span class="sxs-lookup"><span data-stu-id="33f29-155">A renderer **SHOULD** allow host apps to know when all HTTP images have been downloaded and the card is "fully rendererd"</span></span>
1. <span data-ttu-id="33f29-156">Ein Renderer **müssen** überprüfen Sie die Hosts Config `maxImageSize` Param beim Herunterladen von HTTP-Images</span><span class="sxs-lookup"><span data-stu-id="33f29-156">A renderer **MUST** inspect the Host Config `maxImageSize` param when downloading HTTP images</span></span>
1. <span data-ttu-id="33f29-157">Ein Renderer **müssen** unterstützen `.png` und `.jpeg`</span><span class="sxs-lookup"><span data-stu-id="33f29-157">A renderer **MUST** support `.png` and `.jpeg`</span></span>
1. <span data-ttu-id="33f29-158">Ein Renderer **sollte** unterstützen `.gif` Images</span><span class="sxs-lookup"><span data-stu-id="33f29-158">A renderer **SHOULD** support `.gif` images</span></span>

### <a name="host-config"></a><span data-ttu-id="33f29-159">Host-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="33f29-159">Host Config</span></span>

* <span data-ttu-id="33f29-160">TODO: Was sollten folgende Standardwerte verwendet werden?</span><span class="sxs-lookup"><span data-stu-id="33f29-160">TODO: What should the defaults be?</span></span> <span data-ttu-id="33f29-161">Sollten sie sie freigeben?</span><span class="sxs-lookup"><span data-stu-id="33f29-161">Should they all share it?</span></span> <span data-ttu-id="33f29-162">Sollten wir eine gemeinsame hostConfig.json-Datei in den Binärdateien einbetten?</span><span class="sxs-lookup"><span data-stu-id="33f29-162">Should we embed a common hostConfig.json file in the binaries?</span></span>
* <span data-ttu-id="33f29-163">TODO: Ich denke, dass HostConfig sowie für die Analyse mit Versionsangaben versehen werden muss?</span><span class="sxs-lookup"><span data-stu-id="33f29-163">TODO: I think HostConfig needs to be versioned as well for parsing?</span></span>

<span data-ttu-id="33f29-164">[`HostConfig`](host-config.md) ist eine Konfiguration für shared-Objekt, das angibt, wie eine Adaptive Card Renderer UI generiert.</span><span class="sxs-lookup"><span data-stu-id="33f29-164">[`HostConfig`](host-config.md) is a shared configuration object that specifies how an Adaptive Card Renderer generates UI.</span></span>  

<span data-ttu-id="33f29-165">Dadurch können die Eigenschaften, die plattformunabhängig von Renderern, die auf verschiedenen Plattformen und Geräten gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-165">This allows properties which are platform agnostic to be shared among renderers on different platforms and devices.</span></span> <span data-ttu-id="33f29-166">Darüber hinaus können Tools erstellt werden, wodurch Sie sich ein Überblick über das Aussehen und Verhalten, die Karte müssten für eine bestimmte Umgebung.</span><span class="sxs-lookup"><span data-stu-id="33f29-166">It also allows tooling to be created which gives you an idea of the look and feel that card would have for a given environment.</span></span>

1. <span data-ttu-id="33f29-167">Renderer **müssen** verfügbar zu machen eine **Hosts Config** Parameter zum Hosten von apps</span><span class="sxs-lookup"><span data-stu-id="33f29-167">Renderers **MUST** expose a **Host Config** parameter to host apps</span></span>
1. <span data-ttu-id="33f29-168">Alle Elemente **müssen** formatiert werden, entsprechend ihrer jeweiligen Einstellungen für die Host-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="33f29-168">All elements **MUST** be styled according to their respective Host Config settings</span></span>

### <a name="native-platform-styling"></a><span data-ttu-id="33f29-169">Systemeigene Plattform erstellen</span><span class="sxs-lookup"><span data-stu-id="33f29-169">Native platform styling</span></span>

1. <span data-ttu-id="33f29-170">Der Typ jedes Elements **sollte** fügen Sie einen native Plattform-Stil mit dem generierten UI-Element.</span><span class="sxs-lookup"><span data-stu-id="33f29-170">Each element type **SHOULD** attach a native platform style with the generated UI element.</span></span> <span data-ttu-id="33f29-171">Z. B. in HTML wir eine CSS-Klasse hinzugefügt, um den Elementtypen, und in XAML, die wir weisen eines bestimmten Format.</span><span class="sxs-lookup"><span data-stu-id="33f29-171">E.g., in HTML we added a CSS class to the element types, and in XAML we assign a specific Style.</span></span>

## <a name="extensibility"></a><span data-ttu-id="33f29-172">Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="33f29-172">Extensibility</span></span> 

1. <span data-ttu-id="33f29-173">Ein Renderer **müssen** Host Apps Zugriff auf Standard-Element-Renderer zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="33f29-173">A renderer **MUST** allow host apps to override default element renderers.</span></span> <span data-ttu-id="33f29-174">Ersetzen Sie z. B. `TextBlock` rendering mit ihrer eigenen Logik.</span><span class="sxs-lookup"><span data-stu-id="33f29-174">E.g., replace `TextBlock` rendering with their own logic.</span></span>
1. <span data-ttu-id="33f29-175">Ein Renderer **müssen** Host Apps Zugriff auf benutzerdefinierte Elementtypen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="33f29-175">A renderer **MUST** allow host apps to register custom element types.</span></span> <span data-ttu-id="33f29-176">Z. B. Hinzufügen von Unterstützung für eine benutzerdefinierte `Rating` Element</span><span class="sxs-lookup"><span data-stu-id="33f29-176">E.g., add support for a custom `Rating` element</span></span>
1. <span data-ttu-id="33f29-177">Ein Renderer **müssen** ermöglichen apps hosten, um Unterstützung für eine Default-Element zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="33f29-177">A renderer **MUST** allow host apps to remove support for a default element.</span></span> <span data-ttu-id="33f29-178">Entfernen Sie z. B. `Action.Submit` bei Bedarf unterstützt nicht.</span><span class="sxs-lookup"><span data-stu-id="33f29-178">E.g., remove `Action.Submit` if they don't want it supported.</span></span>

## <a name="actions"></a><span data-ttu-id="33f29-179">Aktionen</span><span class="sxs-lookup"><span data-stu-id="33f29-179">Actions</span></span>

1. <span data-ttu-id="33f29-180">Wenn HostConfig `supportsInteractivity` ist `false`, einen Renderer **darf keinen** Maßnahmen, die zu rendern.</span><span class="sxs-lookup"><span data-stu-id="33f29-180">If HostConfig `supportsInteractivity` is `false`, a renderer **MUST NOT** render any actions.</span></span>
1. <span data-ttu-id="33f29-181">Die `actions` Eigenschaft **müssen** als Schaltflächen in einer Art Aktionsleiste in der Regel am unteren Rand der Karte gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-181">The `actions` property **MUST** be rendered as buttons in some kind of action bar, usually at the bottom of the card.</span></span> 
1. <span data-ttu-id="33f29-182">Wenn eine Schaltfläche getippt wird es **müssen** ermöglichen die Host-app zum Behandeln des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="33f29-182">When a button is tapped it **MUST** allow the host app to handle the event.</span></span> 
1. <span data-ttu-id="33f29-183">Das Ereignis **müssen** Bahn entlang allen zugehörigen Eigenschaften mit der Aktion</span><span class="sxs-lookup"><span data-stu-id="33f29-183">The event **MUST** pass along all associated properties with the action</span></span>
1. <span data-ttu-id="33f29-184">Das Ereignis **müssen** übergibt die `AdaptiveCard` die ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="33f29-184">The event **MUST** pass along the `AdaptiveCard` which was executed</span></span>

<span data-ttu-id="33f29-185">Aktion</span><span class="sxs-lookup"><span data-stu-id="33f29-185">Action</span></span> | <span data-ttu-id="33f29-186">Verhalten</span><span class="sxs-lookup"><span data-stu-id="33f29-186">Behavior</span></span>
--- | ---
<span data-ttu-id="33f29-187">**Action.OpenUrl**</span><span class="sxs-lookup"><span data-stu-id="33f29-187">**Action.OpenUrl**</span></span> | <span data-ttu-id="33f29-188">Öffnen Sie eine externe URL für die Anzeige</span><span class="sxs-lookup"><span data-stu-id="33f29-188">Open an external URL for viewing</span></span>
<span data-ttu-id="33f29-189">**Action.ShowCard**</span><span class="sxs-lookup"><span data-stu-id="33f29-189">**Action.ShowCard**</span></span> | <span data-ttu-id="33f29-190">Fordert eine untergeordnete Karte, die dem Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-190">Requests a sub-card to be shown to the user.</span></span>
<span data-ttu-id="33f29-191">**Action.Submit**</span><span class="sxs-lookup"><span data-stu-id="33f29-191">**Action.Submit**</span></span> | <span data-ttu-id="33f29-192">Stellen Sie für alle Elemente mit der Eingabe in ein Objekt gesammelt werden, um die über eine Methode, die von der hostanwendung definiert dann an Sie gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="33f29-192">Ask for all of the input elements to be gathered up into an object which is then sent to you through some method defined by the host application.</span></span>

### <a name="actionopenurl"></a><span data-ttu-id="33f29-193">Action.OpenUrl</span><span class="sxs-lookup"><span data-stu-id="33f29-193">Action.OpenUrl</span></span>
1. <span data-ttu-id="33f29-194">`Action.OpenUrl` **SOLLTE** öffnen Sie eine URL mit der nativen Plattform-Mechanismus</span><span class="sxs-lookup"><span data-stu-id="33f29-194">`Action.OpenUrl` **SHOULD** open a URL using the native platform mechanism</span></span>
1. <span data-ttu-id="33f29-195">Wenn dies nicht möglich ist es **müssen** Auslösen eines Ereignisses für die Host-app, behandeln Sie die URL öffnen.</span><span class="sxs-lookup"><span data-stu-id="33f29-195">If this is not possible it **MUST** raise an event to the host app to handle opening the URL.</span></span> <span data-ttu-id="33f29-196">Dieses Ereignis **müssen** Host-app das Standardverhalten außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="33f29-196">This event **MUST** allow the host app to override the default behavior.</span></span> <span data-ttu-id="33f29-197">Beispielsweise können sie die URL in ihre eigene app zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="33f29-197">E.g., let them open the URL within their own app.</span></span>

### <a name="actionshowcard"></a><span data-ttu-id="33f29-198">Action.ShowCard</span><span class="sxs-lookup"><span data-stu-id="33f29-198">Action.ShowCard</span></span>

1. <span data-ttu-id="33f29-199">`Action.ShowCard` **MUSS** in irgendeiner Form, die entsprechend der HostConfig unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="33f29-199">`Action.ShowCard` **MUST** be supported in some way, based on the hostConfig setting.</span></span> <span data-ttu-id="33f29-200">Es gibt zwei Modi: Inline, und den popupausrichtungspunkt.</span><span class="sxs-lookup"><span data-stu-id="33f29-200">There are two modes: inline, and popup.</span></span> <span data-ttu-id="33f29-201">Inline-Karten **sollte** ein-oder ausblenden, Karte automatisch.</span><span class="sxs-lookup"><span data-stu-id="33f29-201">Inline cards **SHOULD** toggle the card visibility automatically.</span></span> <span data-ttu-id="33f29-202">Im Modus "Popup" ein Ereignis **sollte** ausgelöst werden, für die Host-app auf die Karte auf irgendeine Weise anzeigen.</span><span class="sxs-lookup"><span data-stu-id="33f29-202">In popup mode, an event **SHOULD** be fired to the host app to show the card in some way.</span></span>

### <a name="actionsubmit"></a><span data-ttu-id="33f29-203">Action.Submit</span><span class="sxs-lookup"><span data-stu-id="33f29-203">Action.Submit</span></span>

<span data-ttu-id="33f29-204">Die Aktion senden verhält sich wie ein HTML-Formular übermitteln, mit dem Unterschied, dass, in dem HTML in der Regel HTTP Post auf, mit Adaptive Cards löst sie bis zu verlassen jeder Host-app, um zu bestimmen, was "Absenden" bedeutet, dass sie.</span><span class="sxs-lookup"><span data-stu-id="33f29-204">The Submit Action behaves like an HTML form submit, except that where HTML typically triggers an HTTP post, Adaptive Cards leaves it up to each host app to determine what "submit" means to them.</span></span> 

1. <span data-ttu-id="33f29-205">Wenn dies **müssen** lösen ein Ereignis der Benutzer tippt der Invokved Aktion.</span><span class="sxs-lookup"><span data-stu-id="33f29-205">When this **MUST** raise an event the user taps the action invokved.</span></span>  
1. <span data-ttu-id="33f29-206">Die `data` Eigenschaft **müssen** in die Rückruf-Nutzlast enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="33f29-206">The `data` property **MUST** be included in the callback payload.</span></span>
1. <span data-ttu-id="33f29-207">Für `Action.Submit`, einen Renderer **müssen** sammeln Sie alle Eingaben auf der Karte und deren Werte abrufen.</span><span class="sxs-lookup"><span data-stu-id="33f29-207">For `Action.Submit`, a renderer **MUST** gather all inputs on the card and retrieve their values.</span></span> 

### <a name="selectaction"></a><span data-ttu-id="33f29-208">selectAction</span><span class="sxs-lookup"><span data-stu-id="33f29-208">selectAction</span></span>

1. <span data-ttu-id="33f29-209">Wenn Hosts Config `supportedInteractivity` ist `false` ein `selectAction` **darf nicht** als Touch-Ziel gerendert.</span><span class="sxs-lookup"><span data-stu-id="33f29-209">If Host Config `supportedInteractivity` is `false` then a `selectAction` **MUST NOT** render as a touch target.</span></span>
1. <span data-ttu-id="33f29-210">`Image`, `ColumnSet`, und `Column` bieten eine `selectAction` -Eigenschaft, die **sollte** ausgeführt werden, wenn der Benutzer, z. B. ruft durch Tippen auf das Element.</span><span class="sxs-lookup"><span data-stu-id="33f29-210">`Image`, `ColumnSet`, and `Column` offer a `selectAction` property, which **SHOULD** be executed when the user invokes it, e.g., by tapping the element.</span></span>

## <a name="inputs"></a><span data-ttu-id="33f29-211">Eingaben</span><span class="sxs-lookup"><span data-stu-id="33f29-211">Inputs</span></span>

1. <span data-ttu-id="33f29-212">Wenn HostConfig `supportsInteractivity` ist `false` einen Renderer **darf keinen** Eingaben zu rendern.</span><span class="sxs-lookup"><span data-stu-id="33f29-212">If HostConfig `supportsInteractivity` is `false` a renderer **MUST NOT** render any inputs.</span></span>
2. <span data-ttu-id="33f29-213">Eingaben **sollte** Rendern mit der höchsten Genauigkeit möglich.</span><span class="sxs-lookup"><span data-stu-id="33f29-213">Inputs **SHOULD** render with the highest fidelity possible.</span></span> <span data-ttu-id="33f29-214">Z. B. eine `Input.Date` würde im Idealfall eine Datumsauswahl für einem Benutzer, aber wenn ist dies nicht möglich für Ihre UI-Stack, und klicken Sie dann auf den Renderer bieten **müssen** ein Fallback auf das ein normales Textfeld zu rendern.</span><span class="sxs-lookup"><span data-stu-id="33f29-214">For example, an `Input.Date` would ideally offer a date picker to a user, but if this isn't possible on your UI stack, then the renderer **MUST** fall back to rendering a standard text box.</span></span>
3. <span data-ttu-id="33f29-215">Ein Renderer **sollte** Anzeigen der `placeholderText` möglichst</span><span class="sxs-lookup"><span data-stu-id="33f29-215">A renderer **SHOULD** display the `placeholderText` if possible</span></span>
4. <span data-ttu-id="33f29-216">Ein Renderer **nicht** Validierungen der Eingabe zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="33f29-216">A renderer **DOES NOT** have to implement validation of the input.</span></span> <span data-ttu-id="33f29-217">Benutzer mit Adaptive Cards müssen planen, empfangene Daten auf ihrer Seite zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="33f29-217">Users of Adaptive Cards must plan to validate any receieved data on their end.</span></span>
5. <span data-ttu-id="33f29-218">Geben Sie die wertbindung **müssen** ordnungsgemäß mit Escapezeichen versehen werden</span><span class="sxs-lookup"><span data-stu-id="33f29-218">Input value binding **MUST** be properly escaped</span></span>

6. <span data-ttu-id="33f29-219">Das Objekt **müssen** an den Host-app wie folgt zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="33f29-219">The object **MUST** be returned to the host app as follows:</span></span>

   <span data-ttu-id="33f29-220">Wir machen Versprechen, die Überprüfung der Eingabe nicht in mit adaptive Cards, ist es also an die empfangende Partei, ordnungsgemäß Analysieren der Antwort.</span><span class="sxs-lookup"><span data-stu-id="33f29-220">We do not make any promises of input validation in adaptive cards, so it's up to the receiving party to properly parse the response.</span></span> <span data-ttu-id="33f29-221">Z. B. eine Input.Number konnte "hello" zurück, und sie dafür vorbereitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="33f29-221">E.g., a Input.Number could return "hello" and they need to be prepared for that.</span></span>


## <a name="events"></a><span data-ttu-id="33f29-222">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="33f29-222">Events</span></span>

1. <span data-ttu-id="33f29-223">Ein Renderer **sollte** ein Ereignis, wenn die Sichtbarkeit eines Elements geändert wurde, ermöglicht es der Host-app in die Position die Karte zu scrollen, ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="33f29-223">A renderer **SHOULD** fire an event when an element's visibility has changed, allowing the host app to scroll the card into position.</span></span>
