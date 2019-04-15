---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 735f0f8ed1f0d3fdc78f1c840a7aba1892faa5d4
ms.sourcegitcommit: 99c7b64d6fc66da336c454951406fb42cd2a7427
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59553362"
---
# <a name="extensibility---android"></a><span data-ttu-id="51717-102">Erweiterbarkeit – Android</span><span class="sxs-lookup"><span data-stu-id="51717-102">Extensibility - Android</span></span>

## <a name="custom-parsing-of-card-elements"></a><span data-ttu-id="51717-103">Benutzerdefinierte Analyse der Elemente mit Karte</span><span class="sxs-lookup"><span data-stu-id="51717-103">Custom Parsing of Card Elements</span></span>

<span data-ttu-id="51717-104">Sie können den Parser Support Karte Elemente erweitern, die Sie definiert haben.</span><span class="sxs-lookup"><span data-stu-id="51717-104">You may extend the parser to suport card elements that you have defined.</span></span> <span data-ttu-id="51717-105">Angenommen Sie, dass es sich um einen neuen Elementtyp gibt, der folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="51717-105">For example, say we have a new element type that looks like this:</span></span>
```json
{
    "type" : "MyType",
    "MyTypeData" : "My data"
}
```

<span data-ttu-id="51717-106">Klicken Sie dann veranschaulichen die folgenden Zeilen in einer CardElement analysieren, der von der BaseCardElement erweitert:</span><span class="sxs-lookup"><span data-stu-id="51717-106">Then the following lines demonstrate how to parse it into a CardElement that extends from the BaseCardElement:</span></span>
```java
public class MyCustomCardElement extends BaseCardElement
{

    public MyCustomCardElement(CardElementType type) {
        super(type);
    }

    public String getMyTypeData()
    {
        return myTypeData;
    }

    public void setMyTypeData(String data)
    {
        myTypeData = data;
    }

    private String myTypeData;
}

public class MyCardElementParser extends BaseCardElementParser
{
    @Override
    public BaseCardElement Deserialize(ElementParserRegistration elementParserRegistration, ActionParserRegistration actionParserRegistration, JsonValue value)
    {
        MyCustomCardElement element = new CustomCardElement(CardElementType.Custom);
        element.SetElementTypeString("MyType");
        String val = value.getString();
        try {
            JSONObject obj = new JSONObject(val);
            element.setMyTypeData(obj.getString("secret"));
        } catch (JSONException e) {
            e.printStackTrace();
            element.setMyTypeData("Failed");
        }
        return element;
    }
}
```

<span data-ttu-id="51717-107">Und dies ist das Registrieren des Parsers und erhalten ein AdaptiveCard-Objekt, das benutzerdefinierte Element enthält:</span><span class="sxs-lookup"><span data-stu-id="51717-107">And this is how to register the parser and get an AdaptiveCard object that contains the custom element:</span></span>
```java
// Create an ElementParserRegistrationObject and add your parser to it
ElementParserRegistration elementParserRegistration = new ElementParserRegistration();
elementParserRegistration.AddParser("MyType", new MyCardElementParser());

AdaptiveCard adaptiveCard = AdaptiveCard.DeserializeFromString(jsonText, elementParserRegistration);
```

<span data-ttu-id="51717-108">Als Nächstes folgt das benutzerdefinierte Element Rendern</span><span class="sxs-lookup"><span data-stu-id="51717-108">Next comes rendering the custom element</span></span>

## <a name="custom-rendering-of-card-elements"></a><span data-ttu-id="51717-109">Benutzerdefiniertes Rendern der Elemente mit Karte</span><span class="sxs-lookup"><span data-stu-id="51717-109">Custom Rendering of Card Elements</span></span>

<span data-ttu-id="51717-110">Um unseren benutzerdefinierten Renderers für unsere zu definieren, müssen wir zuerst eine Klasse erstellen, die von BaseCardElementParser erweitert:</span><span class="sxs-lookup"><span data-stu-id="51717-110">To define our own custom renderer for our type, we must first create a class that extends from BaseCardElementParser:</span></span>
```java
public class MyCardElementRenderer extends BaseCardElementRenderer
{
    @Override
    public View render(Context context, FragmentManager fragmentManager, ViewGroup viewGroup, BaseCardElement baseCardElement, Vector<IInputHandler> inputActionHandlerList, ICardActionHandler cardActionHandler, HostConfig hostConfig, ContainerStyle containerStyle) {

        //Call findImplObj on baseCardElement to get the instace we returned at parse. We can then cast that object to our type
        CustomCardElement element = (CustomCardElement) baseCardElement.findImplObj();

        //Create some view and add it to the view group
        TextView textView = new TextView(context);
        textView.setText(element.getMyTypeData());
        textView.setAllCaps(true);
        viewGroup.addView(textView);

        //return the view
        return textView;
    }
}
```

<span data-ttu-id="51717-111">Wir registrieren dann diesen Renderer wie folgt:</span><span class="sxs-lookup"><span data-stu-id="51717-111">We then register this renderer like so:</span></span>
```java
CardRendererRegistration.getInstance().registerRenderer("MyType", new CustomBlahRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
```

