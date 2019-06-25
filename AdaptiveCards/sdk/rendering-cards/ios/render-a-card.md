---
title: Rendern einer Karte – iOS SDK
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: 7d8d8410c030584dc5a518af7e6473d1d51f3991
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134329"
---
# <a name="render-a-card---ios"></a><span data-ttu-id="4aaca-102">Rendern einer Karte – iOS</span><span class="sxs-lookup"><span data-stu-id="4aaca-102">Render a card - iOS</span></span>

<span data-ttu-id="4aaca-103">Hier findest du Informationen zum Rendern einer Karte mit dem iOS SDK.</span><span class="sxs-lookup"><span data-stu-id="4aaca-103">Here's how to render a card using the iOS SDK.</span></span>

## <a name="create-a-card-from-a-json-string"></a><span data-ttu-id="4aaca-104">Erstellen einer Karte aus einer JSON-Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="4aaca-104">Create a card from a JSON string</span></span>

<span data-ttu-id="4aaca-105">AdaptiveCard wird aus einer JSON-Zeichenfolge generiert.</span><span class="sxs-lookup"><span data-stu-id="4aaca-105">AdaptiveCard is generated from JSON string</span></span>

```objective-c

NSString *jsonStr = @"{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";
ACOAdaptiveCardParseResult *cardParseResult = [ACOAdaptiveCard fromJson:jsonStr];

/// access for parse warnings and errors
NSArray<NSError *> errors = cardParseResult.parseErrors;
NSArray<ACRParseWarning *> warnings = cardPraseResult.parseWarnings;
```

## <a name="render-a-card"></a><span data-ttu-id="4aaca-106">Rendern einer Karte</span><span class="sxs-lookup"><span data-stu-id="4aaca-106">Render a Card</span></span>

<span data-ttu-id="4aaca-107">Der Renderer verwendet die adaptive Karte und die Hostkonfiguration. HostConfig kann „nil“ sein. In dem Fall wird der Standardwert verwendet.</span><span class="sxs-lookup"><span data-stu-id="4aaca-107">Rederer takes adaptive card and host config. HostConfig can be nil, and if nil, default value will be used.</span></span>
<span data-ttu-id="4aaca-108">Das zurückgegebene UIView-Element verwendet ein Autolayout.</span><span class="sxs-lookup"><span data-stu-id="4aaca-108">Returned UIView uses autolayout.</span></span> <span data-ttu-id="4aaca-109">Die Breite wird auf den Wert eingeschränkt, der von widthConstraint festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="4aaca-109">Width will be constraint to the value set by widthConstraint.</span></span> <span data-ttu-id="4aaca-110">Wenn der Wert 0 verwendet wird, gilt keine Begrenzung.</span><span class="sxs-lookup"><span data-stu-id="4aaca-110">If 0 value is used, it won't be bound.</span></span>
<span data-ttu-id="4aaca-111">Die Höhe ist nicht begrenzt. Nach dem Zurückgeben ist sie so groß wie die Höhe der Summen aller gerenderten Inhalte.</span><span class="sxs-lookup"><span data-stu-id="4aaca-111">Height is not bound, and when returned it will have the height of sums of all contents rendered.</span></span> <span data-ttu-id="4aaca-112">Verwende NSLayoutConstraint, um die Ansichtsdimension zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="4aaca-112">To bound the view dimension, please use NSLayoutConstraint.</span></span> <span data-ttu-id="4aaca-113">Auf die genaue Dimension kann aus dem Kontext von viewDidLayoutSubview der viewcontroller-Überansicht oder die Methode mit dem gleichen Namen zugegriffen werden, wenn ACRViewController verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4aaca-113">The exact dimension is accessible from the context of viewDidLayoutSubview of its superview's viewcontroller or its method with the same name if ACRViewController is used.</span></span>

```objective-c
ACRRenderResult *renderResult;
if(cardParseResult.isValid){
    renderResult = [ACRRenderer render:cardParseResult.card config:nil widthConstraint:335];
}
``` 
### <a name="example"></a><span data-ttu-id="4aaca-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4aaca-114">Example</span></span>

```objective-c
--------------------------------------------------------------------------------
ViewController.m
--------------------------------------------------------------------------------
#import "ViewController.h"
#import <SafariServices/SafariServices.h>

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];

    NSString *jsonStr = @"{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";
    ACRRenderResult *renderResult;
    ACOAdaptiveCardParseResult *cardParseResult = [ACOAdaptiveCard fromJson:jsonStr];
    if(cardParseResult.isValid){
        renderResult = [ACRRenderer render:cardParseResult.card config:nil widthConstraint:335];
    }

    if(renderResult.succeeded)
    {
        ACRView *ad = renderResult.view;
        ad.acrActionDelegate = self;
        
        UIView *view = self.view;
        view.autoresizingMask |= UIViewAutoresizingFlexibleHeight;
        [self.view addSubview:ad];
        ad.translatesAutoresizingMaskIntoConstraints = NO;
        
        [NSLayoutConstraint constraintWithItem:ad attribute:NSLayoutAttributeCenterX relatedBy:NSLayoutRelationEqual toItem:view attribute:NSLayoutAttributeCenterX multiplier:1.0 constant:0].active = YES;

        [NSLayoutConstraint constraintWithItem:ad attribute:NSLayoutAttributeCenterY relatedBy:NSLayoutRelationEqual toItem:view attribute:NSLayoutAttributeCenterY multiplier:1.0 constant:3].active = YES;
    }
}

- (void)didFetchUserResponses:(ACOAdaptiveCard *)card action:(ACOBaseActionElement *)action
{
    if(action.type == ACROpenUrl){
        NSURL *url = [NSURL URLWithString:[action url]];
        SFSafariViewController *svc = [[SFSafariViewController alloc] initWithURL:url];
        [self presentViewController:svc animated:YES completion:nil];
    }
}

@end

```

```swift
--------------------------------------------------------------------------------
ViewController.swft
--------------------------------------------------------------------------------

import UIKit
import SafariServices

class ViewController: UIViewController, ACRActionDelegate {

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        let jsonStr = "{ \"type\": \"AdaptiveCard\", \"version\": \"1.0\", \"body\": [ { \"type\": \"Image\", \"url\": \"http://adaptivecards.io/content/adaptive-card-50.png\", \"horizontalAlignment\":\"center\" }, { \"type\": \"TextBlock\", \"horizontalAlignment\":\"center\", \"text\": \"Hello **Adaptive Cards!**\" } ], \"actions\": [ { \"type\": \"Action.OpenUrl\", \"title\": \"Learn more\", \"url\": \"http://adaptivecards.io\" }, { \"type\": \"Action.OpenUrl\", \"title\": \"GitHub\", \"url\": \"http://github.com/Microsoft/AdaptiveCards\" } ] }";

        let cardParseResult = ACOAdaptiveCard.fromJson(jsonStr);
        if((cardParseResult?.isValid)!){
            let renderResult = ACRRenderer.render(cardParseResult!.card, config: nil, widthConstraint: 335);

            if(renderResult?.succeeded ?? false)
            {
                let ad = renderResult?.view;
                ad!.acrActionDelegate = (self as ACRActionDelegate);
                self.view.autoresizingMask = [.flexibleHeight];
                self.view.addSubview(ad!);
                ad!.translatesAutoresizingMaskIntoConstraints = false;
    
                NSLayoutConstraint(item: ad!, attribute: .centerX, relatedBy: .equal, toItem: view, attribute: .centerX, multiplier: 1.0, constant: 0).isActive = true;
                NSLayoutConstraint(item: ad!, attribute: .centerY, relatedBy: .equal, toItem: view, attribute: .centerY, multiplier: 1.0, constant: 3).isActive = true;
            }
        }
    }

    func didFetchUserResponses(_ card: ACOAdaptiveCard, action: ACOBaseActionElement)
    {
        if(action.type == ACRActionType.openUrl){
            let url = URL.init(string:action.url());
            let svc = SFSafariViewController.init(url: url!);
            self.present(svc, animated: true, completion: nil);
        }
    }

}
```
