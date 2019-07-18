---
title: Aktionen – Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 49b0b45abeb54381bd7b4b548219a09ad5da10c1
ms.sourcegitcommit: 8c8067206f283d97a5aa4ec65ba23d3fe18962f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299523"
---
# <a name="actions---android"></a><span data-ttu-id="5c744-102">Aktionen – Android</span><span class="sxs-lookup"><span data-stu-id="5c744-102">Actions - Android</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c744-103">**Liste der wichtigen Änderungen**</span><span class="sxs-lookup"><span data-stu-id="5c744-103">**List of Breaking changes**</span></span>
> 
> [<span data-ttu-id="5c744-104">Wichtige Änderungen in v 1.1</span><span class="sxs-lookup"><span data-stu-id="5c744-104">Breaking changes in v1.1</span></span>](#breaking-changes-in-v11)
> 

<span data-ttu-id="5c744-105">Wenn eine Cards-Aktion ausgeführt wird, wird die Klasse aufgerufen, die an den Rendering-Aufruf ```ICardActionHandler``` , der die-Schnittstelle implementiert, übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="5c744-105">When a cards action is executed, the class that was passed to the render call that implements the ```ICardActionHandler``` interface gets invoked.</span></span> <span data-ttu-id="5c744-106">So wird ein Aktionshandler definiert:</span><span class="sxs-lookup"><span data-stu-id="5c744-106">Here is how to define your action handler:</span></span>

```java
public class ActionHandler implements ICardActionHandler
{
    @Override
    public void onAction(BaseActionElement actionElement, RenderedAdaptiveCard renderedCard)
    {
        ActionType actionType = actionElement.GetElementType();
        if (actionType == ActionType.Submit)
        {
            onSubmit(actionElement, renderedCard);
        }
        else if (actionType == ActionType.ShowCard)
        {
            onShowCard(actionElement);
        }
        else if (actionType == ActionType.OpenUrl)
        {
            onOpenUrl(actionElement);
        }
        else if (actionType == ActionType.Custom)
        {
            //Handle activation of custom actions
            ...
        }
    }

    private void onSubmit(BaseActionElement actionElement, RenderedAdaptiveCard renderedAdaptiveCard)
    {
        SubmitAction submitAction = null;
        if (actionElement instanceof SubmitAction)
        {
            submitAction = (SubmitAction) actionElement;
        }
        else if ((submitAction = SubmitAction.dynamic_cast(actionElement)) == null)
        {
            throw new InternalError("Unable to convert BaseActionElement to ShowCardAction object model.");
        }

        String data = submitAction.GetDataJson();
        Map<String, String> keyValueMap = renderedAdaptiveCard.getInputs();
        if (!data.isEmpty())
        {
            try
            {
                JSONObject object = new JSONObject(data);
                showToast("Submit data: " + object.toString() + "\nInput: " + keyValueMap.toString(), Toast.LENGTH_LONG);
            }
            catch (JSONException e)
            {
                showToast(e.toString(), Toast.LENGTH_LONG);
            }
        }
        else
        {
            showToast("Submit input: " + keyValueMap.toString(), Toast.LENGTH_LONG);
        }
    }

    private void onShowCard(BaseActionElement actionElement)
    {
        ShowCardAction showCardAction = null;
        if (actionElement instanceof ShowCardAction)
        {
            showCardAction = (ShowCardAction) actionElement;
        }
        else if ((showCardAction = ShowCardAction.dynamic_cast(actionElement)) == null)
        {
            throw new InternalError("Unable to convert BaseActionElement to ShowCardAction object model.");
        }

        //Get the card from show card and create a view
        RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, showCardAction.GetCard(), cardActionHandler, hostConfig);

        ViewGroup viewGroup = (ViewGroup) renderedCard.getView();
        ...
    }

    private void onOpenUrl(BaseActionElement actionElement)
    {
        OpenUrlAction openUrlAction = null;
        if (actionElement instanceof ShowCardAction)
        {
            openUrlAction = (OpenUrlAction) actionElement;
        }
        else if ((openUrlAction = OpenUrlAction.dynamic_cast(actionElement)) == null)
        {
            throw new InternalError("Unable to convert BaseActionElement to ShowCardAction object model.");
        }

        Intent browserIntent = new Intent(Intent.ACTION_VIEW, Uri.parse(openUrlAction.GetUrl()));
        this.startActivity(browserIntent);
    }
}
```

## <a name="breaking-changes-in-v11"></a><span data-ttu-id="5c744-107">Wichtige Änderungen in v 1.1</span><span class="sxs-lookup"><span data-stu-id="5c744-107">Breaking changes in v1.1</span></span>

<span data-ttu-id="5c744-108">Das in dieser Version enthaltene Medien Element erfordert, dass zwei neue Methoden von den Klassen implementiert werden, ```ICardActionHandler```die implementieren. diese Methoden lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5c744-108">The media element included in this version requires two new methods to be implemented by the classes that implement ```ICardActionHandler```, these methods are:</span></span>

* <span data-ttu-id="5c744-109">```onMediaPlay```wird aufgerufen, wenn die Wiedergabe Schaltfläche zum ersten Mal in einem beliebigen Medien Element gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="5c744-109">```onMediaPlay``` is invoked when the play button is pressed for the first time in any media element</span></span>
* <span data-ttu-id="5c744-110">```onMediaStop```wird aufgerufen, wenn das Medium das Ende erreicht.</span><span class="sxs-lookup"><span data-stu-id="5c744-110">```onMediaStop``` is invoked when the media reaches it's end</span></span>

<span data-ttu-id="5c744-111">Die Signaturen für diese Methoden lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5c744-111">The signatures for these methods are:</span></span>

```java
public void onMediaPlay(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
public void onMediaStop(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
```

<span data-ttu-id="5c744-112">Die Implementierung für den Aktions Handler aus dem vorherigen Beispiel sieht nun etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5c744-112">And the implementation for the ActionHandler from the previous example would now look similar to this:</span></span>

```java
public class ActionHandler implements ICardActionHandler
{
    @Override
    public void onAction(BaseActionElement actionElement, RenderedAdaptiveCard renderedCard)
    { }

    private void onSubmit(BaseActionElement actionElement, RenderedAdaptiveCard renderedAdaptiveCard) 
    { }

    private void onShowCard(BaseActionElement actionElement)
    { }

    private void onOpenUrl(BaseActionElement actionElement)
    { }

    @Override
    public void onMediaPlay(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
    {
        // Your logic here, i.e.
        showToast("Media started: " + mediaElement, Toast.LENGTH_LONG);
    }

    @Override
    public void onMediaStop(BaseCardElement mediaElement, RenderedAdaptiveCard renderedAdaptiveCard)
    {
        // Your logic here, i.e.
        showToast("Media ended playing: " + mediaElement, Toast.LENGTH_LONG);
    }
}
```
