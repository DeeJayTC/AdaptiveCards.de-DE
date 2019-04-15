---
title: Erweiterbarkeit – SDK für iOS
author: matthidinger
ms.author: mahiding
ms.date: 06/26/2017
ms.topic: article
ms.openlocfilehash: c3dcae7ef2347201b5f7ce02baf3204db7ee27d6
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553562"
---
# <a name="extensibility---ios"></a><span data-ttu-id="c8e3a-102">Erweiterbarkeit – iOS</span><span class="sxs-lookup"><span data-stu-id="c8e3a-102">Extensibility - iOS</span></span>

## <a name="changing-per-element-rendering"></a><span data-ttu-id="c8e3a-103">Pro Element-Textrendering ändern</span><span class="sxs-lookup"><span data-stu-id="c8e3a-103">Changing per element rendering</span></span>

<span data-ttu-id="c8e3a-104">Entwickler können das Aussehen der Renderred AdaptiveCards Elemente wie z. B. TextBlock anpassen.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-104">Developers can customize the look of renderred AdaptiveCards elements such as TextBlock.</span></span>
<span data-ttu-id="c8e3a-105">Folgende Beispiel zeigt, wie eine Hintergrundfarbe des NumberInput ändern kann.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-105">Following example shows how one can change background color of NumberInput.</span></span>

```objective-c
ACRRegistration *registration = [ACRRegistration getInstance];
// register custom renderer with registration
// custom renderer must implement ACRIBaseCardElementRenderer protocol
// for more information, please refer to CustomInputNumberRenderer.mm
 [registration setBaseCardElementRenderer:[CustomInputNumberRenderer getInstance] cardElementType:ACRNumberInput];
 ...
/// CustiomInputNumberRenderer.mm
- (UIView *)render:(UIView<ACRIContentHoldingView> *)viewGroup
              rootViewController:(UIViewController *)vc
              inputs:(NSArray *)inputs
     baseCardElement:(ACOBaseCardElement *)acoElem
          hostConfig:(ACOHostConfig *)acoConfig
  {
      ACRInputNumberRenderer *defaultRenderer = [ACRInputNumberRenderer getInstance];
 
      UIView *input = [defaultRenderer render:viewGroup
                           rootViewController:vc
                                       inputs:inputs
                              baseCardElement:acoElem
                                   hostConfig:acoConfig];
      if(input)
      {   
          // customize background color of input
          [input setBackgroundColor: [UIColor colorWithRed:1.0
                                                     green:59.0/255.0
                                                      blue:48.0/255.0
                                                     alpha:1.0]];
      }
      return input;
  }
  ```

 ## <a name="additional-property"></a><span data-ttu-id="c8e3a-106">Zusätzliche Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c8e3a-106">Additional Property</span></span>

 <span data-ttu-id="c8e3a-107">Entwickler können auch in zusätzlichen Eigenschaften als Teil des JSON-Nutzlast senden.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-107">Developers can also send in additional properties as part of json payload.</span></span>
<span data-ttu-id="c8e3a-108">Beispielsweise kann zusätzlich zu "Abstand" und "Id" der JSON-Nutzlast für BaseCardElement, eine Radius für Ecken des TextBlock dessen JSON-Nutzlast hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-108">For example, in addition to "spacing" and "id" of json payload for BaseCardElement, one can add radius for corners of TextBlock to its json payload.</span></span>

 ```objective-c
 "type":"TextBlock",
 ...
 "radius":20,
 ...
 ```

 ```objective-c
         NSData *additionalProperty = [acoElem additionalProperty];
          if(additionalProperty) {
              NSDictionary *dictionary = [NSJSONSerialization JSONObjectWithData:additionalProperty options:NSJSONReadingMutableLeaves error:nil];
              radiusForMyTextBlock = dictionary[@"radius"];
          ...
```
 ## <a name="custom-parsing"></a><span data-ttu-id="c8e3a-109">Benutzerdefinierte Analyse</span><span class="sxs-lookup"><span data-stu-id="c8e3a-109">Custom Parsing</span></span>

<span data-ttu-id="c8e3a-110">Entwickler können auch haben benutzerdefinierte Analyse und neues UI-Element Adpative-Karte wie z. B. Statusanzeige hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-110">Developers can also have custom parsing and have new UI element added to adpative card such as progress bar.</span></span> <span data-ttu-id="c8e3a-111">Finden Sie CustomProgressBarRenderer.mm Details.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-111">Please check CustomProgressBarRenderer.mm for detail.</span></span>
<span data-ttu-id="c8e3a-112">Benutzerdefinierter Parser muss ACOIBaseCardElementParser-Protokoll implementieren.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-112">Custom parser must implement ACOIBaseCardElementParser protocol.</span></span> <span data-ttu-id="c8e3a-113">DeserializeToCustomElement-Methode analysiert, die JSON-Nutzlast, die als NSData erhalten soll, und geben einen Zeiger auf UIView-Objekt, das gerendert AdaptiveCard-Objekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c8e3a-113">deserializeToCustomElement method should parses given json payload given as NSData and return a pointer to UIView object that will be added to AdaptiveCard rendered object.</span></span>

```objective-c
      CustomProgressBarRenderer *progressBarRenderer = [[CustomProgressBarRenderer alloc] init];
      [registration setCustomElementParser:progressBarRenderer];
```objective-c