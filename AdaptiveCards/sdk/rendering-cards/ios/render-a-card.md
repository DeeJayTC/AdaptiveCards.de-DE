---
title: Rendern einer Karte - SDK für iOS
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 625701e38389cc1a54682b72ce2315c14180e576
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59552472"
---
# <a name="render-a-card---ios"></a><span data-ttu-id="535bd-102">Rendern einer Karte – iOS</span><span class="sxs-lookup"><span data-stu-id="535bd-102">Render a card - iOS</span></span>

<span data-ttu-id="535bd-103">Hier ist eine Karte mit dem iOS-SDK darstellen.</span><span class="sxs-lookup"><span data-stu-id="535bd-103">Here's how to render a card using the iOS SDK.</span></span>

## <a name="create-a-card-from-a-json-string"></a><span data-ttu-id="535bd-104">Erstellen Sie eine Karte aus einem JSON-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="535bd-104">Create a card from a JSON string</span></span>

<span data-ttu-id="535bd-105">AdaptiveCard wird aus JSON-Zeichenfolge generiert.</span><span class="sxs-lookup"><span data-stu-id="535bd-105">AdaptiveCard is generated from JSON string</span></span>

```objective-c
ACOParseResult *cardParseResult = [ACOAdaptiveCards FromJson:jsonStr];
/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a><span data-ttu-id="535bd-106">Rendern einer Karte</span><span class="sxs-lookup"><span data-stu-id="535bd-106">Render a Card</span></span>

<span data-ttu-id="535bd-107">Rederer dauert adaptive Card und Host-Konfiguration. HostConfig kann NULL sein, und wenn NULL, Standardwert verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="535bd-107">Rederer takes adaptive card and host config. HostConfig can be nil, and if nil, default value will be used.</span></span>

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:nil
                   widthConstraint:300.0];
``` 

### <a name="example"></a><span data-ttu-id="535bd-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="535bd-108">Example</span></span>

```objective-c
ACRRenderResult *renderResult;
ACOHostConfigParseResult *hostconfigParseResult = [ACOHostConfig FromJson:self.hostconfig];
ACOAdaptiveCardsParseResult *cardParseResult       = [ACOAdaptiveCards FromJson:jsonStr];

// checking parse result
if(hostconfigParseResult.IsValid == YES && cardParseResult.IsValid == YES)
{
    renderResult = [ACRRenderer render:cardParseResult.card
                                config:hostconfigParseResult.config
                       widthConstraint:300.0];
}   
    
if(renderResult.Suceeded == YES)
{
    // access returned UIView object
    ACRView *adaptiveView = renderResult.view;
    [self.view addSubview:adcVc.view];
}
```

### <a name="render-a-card-as-uiviewcontroller"></a><span data-ttu-id="535bd-109">Eine Karte als UIViewController Rendern</span><span class="sxs-lookup"><span data-stu-id="535bd-109">Render a Card as UIViewController</span></span>

<span data-ttu-id="535bd-110">AdaptiveCard-Renderer kann UIViewController zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="535bd-110">AdaptiveCard renderer can also return UIViewController.</span></span>

```objective-c
ACRRenderResult *renderResult = [ACRRenderer renderAsViewController:card config:config frame:frame delegate:acrActionDelegate];

renderResult.viewif(renderResult.Suceeded == YES)
{
    ACRViewController *adaptiveViewController = renderResult.viewcontroller;
    [self addChildViewController:adaptiveViewController];
    [self.view addSubview:adaptiveViewController.view];
    [adaptiveViewController didMoveToParentViewController:self];
    ...
}
```

<span data-ttu-id="535bd-111">Zurückgegeben, UIView Autolayout verwendet.</span><span class="sxs-lookup"><span data-stu-id="535bd-111">Returned UIView uses autolayout.</span></span> <span data-ttu-id="535bd-112">Breite werden die Einschränkung, die durch WidthConstraint festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="535bd-112">Width will be constraint to the value set by widthConstraint.</span></span> <span data-ttu-id="535bd-113">Wenn der Wert 0 verwendet wird, wird nicht gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="535bd-113">If 0 value is used, it won't be bound.</span></span>
<span data-ttu-id="535bd-114">Höhe nicht gebunden ist, und wenn zurückgegeben wird, muss die Höhe der Summen aller Inhalte gerendert.</span><span class="sxs-lookup"><span data-stu-id="535bd-114">Height is not bound, and when returned it will have the height of sums of all contents rendered.</span></span> <span data-ttu-id="535bd-115">Um die Dimension der Ansicht gebunden ist, verwenden Sie NSLayoutConstraint.</span><span class="sxs-lookup"><span data-stu-id="535bd-115">To bound the view dimension, please use NSLayoutConstraint.</span></span> <span data-ttu-id="535bd-116">Die genaue Dimension ist aus dem Kontext der ViewDidLayoutSubview der Überblicksansicht der Viewcontroller oder die Methode mit dem gleichen Namen zugegriffen werden kann, wenn ACRViewController verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="535bd-116">The exact dimension is accessible from the context of viewDidLayoutSubview of its superview's viewcontroller or its method with the same name if ACRViewController is used.</span></span>


### <a name="compact-style-inputchoiceset"></a><span data-ttu-id="535bd-117">Compact Stil Input.ChoiceSet</span><span class="sxs-lookup"><span data-stu-id="535bd-117">Compact Style Input.ChoiceSet</span></span>

<span data-ttu-id="535bd-118">Darstellung der Benutzeroberfläche Input.ChoiceSet hat UINavigationController, und er muss auf einem derzeit aktiven uiviewcontroller-Element für den Übergang in UIView angezeigt, das Benutzerauswahl ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="535bd-118">UI representation of Input.ChoiceSet has UINavigationController, and it needs to be presented to a presently active UIViewController to transition into UIView that allows user selection.</span></span>

<span data-ttu-id="535bd-119">Implementieren Sie DidFecthSecondaryView von ACRActionDelegate, um das zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="535bd-119">To accomplish that, please implement didFecthSecondaryView of ACRActionDelegate.</span></span>

```objective-c
- (void)didFetchSecondaryView:(ACOAdaptiveCard *)card navigationController:(UINavigationController *)navigationController{
    [self presentViewController:navigationController animated:YES completion:nil];
}  
```

<span data-ttu-id="535bd-120">Wenn indem der Delegat nicht eingebunden wurde, holen Sie dies.</span><span class="sxs-lookup"><span data-stu-id="535bd-120">If the delgate has not been hooked up, do so.</span></span>

```objective-c
adaptiveView.acrActionDelegate = self
```