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
# <a name="render-a-card---ios"></a>Rendern einer Karte – iOS

Hier ist eine Karte mit dem iOS-SDK darstellen.

## <a name="create-a-card-from-a-json-string"></a>Erstellen Sie eine Karte aus einem JSON-Zeichenfolge

AdaptiveCard wird aus JSON-Zeichenfolge generiert.

```objective-c
ACOParseResult *cardParseResult = [ACOAdaptiveCards FromJson:jsonStr];
/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a>Rendern einer Karte

Rederer dauert adaptive Card und Host-Konfiguration. HostConfig kann NULL sein, und wenn NULL, Standardwert verwendet werden.

```objective-c
ACRRenderResult *renderResult;
renderResult = [ACRRenderer render:cardParseResult.card
                            config:nil
                   widthConstraint:300.0];
``` 

### <a name="example"></a>Beispiel

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

### <a name="render-a-card-as-uiviewcontroller"></a>Eine Karte als UIViewController Rendern

AdaptiveCard-Renderer kann UIViewController zurückgegeben werden.

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

Zurückgegeben, UIView Autolayout verwendet. Breite werden die Einschränkung, die durch WidthConstraint festgelegten Wert. Wenn der Wert 0 verwendet wird, wird nicht gebunden werden.
Höhe nicht gebunden ist, und wenn zurückgegeben wird, muss die Höhe der Summen aller Inhalte gerendert. Um die Dimension der Ansicht gebunden ist, verwenden Sie NSLayoutConstraint. Die genaue Dimension ist aus dem Kontext der ViewDidLayoutSubview der Überblicksansicht der Viewcontroller oder die Methode mit dem gleichen Namen zugegriffen werden kann, wenn ACRViewController verwendet wird.


### <a name="compact-style-inputchoiceset"></a>Compact Stil Input.ChoiceSet

Darstellung der Benutzeroberfläche Input.ChoiceSet hat UINavigationController, und er muss auf einem derzeit aktiven uiviewcontroller-Element für den Übergang in UIView angezeigt, das Benutzerauswahl ermöglicht.

Implementieren Sie DidFecthSecondaryView von ACRActionDelegate, um das zu erreichen.

```objective-c
- (void)didFetchSecondaryView:(ACOAdaptiveCard *)card navigationController:(UINavigationController *)navigationController{
    [self presentViewController:navigationController animated:YES completion:nil];
}  
```

Wenn indem der Delegat nicht eingebunden wurde, holen Sie dies.

```objective-c
adaptiveView.acrActionDelegate = self
```