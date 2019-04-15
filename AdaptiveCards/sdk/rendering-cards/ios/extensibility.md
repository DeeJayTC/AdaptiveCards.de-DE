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
# <a name="extensibility---ios"></a>Erweiterbarkeit – iOS

## <a name="changing-per-element-rendering"></a>Pro Element-Textrendering ändern

Entwickler können das Aussehen der Renderred AdaptiveCards Elemente wie z. B. TextBlock anpassen.
Folgende Beispiel zeigt, wie eine Hintergrundfarbe des NumberInput ändern kann.

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

 ## <a name="additional-property"></a>Zusätzliche Eigenschaft

 Entwickler können auch in zusätzlichen Eigenschaften als Teil des JSON-Nutzlast senden.
Beispielsweise kann zusätzlich zu "Abstand" und "Id" der JSON-Nutzlast für BaseCardElement, eine Radius für Ecken des TextBlock dessen JSON-Nutzlast hinzufügen.

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
 ## <a name="custom-parsing"></a>Benutzerdefinierte Analyse

Entwickler können auch haben benutzerdefinierte Analyse und neues UI-Element Adpative-Karte wie z. B. Statusanzeige hinzugefügt. Finden Sie CustomProgressBarRenderer.mm Details.
Benutzerdefinierter Parser muss ACOIBaseCardElementParser-Protokoll implementieren. DeserializeToCustomElement-Methode analysiert, die JSON-Nutzlast, die als NSData erhalten soll, und geben einen Zeiger auf UIView-Objekt, das gerendert AdaptiveCard-Objekt hinzugefügt wird.

```objective-c
      CustomProgressBarRenderer *progressBarRenderer = [[CustomProgressBarRenderer alloc] init];
      [registration setCustomElementParser:progressBarRenderer];
```objective-c