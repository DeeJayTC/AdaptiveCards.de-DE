---
title: Android SDK Erweiterbarkeit
author: almedina-ms
ms.author: almedina
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 1281a31c333474c1899831acab28c962ce8e4514
ms.sourcegitcommit: c921a7bb15a95c0ceb803ad375501ee3b8bef028
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83631318"
---
# <a name="extensibility---android"></a>Erweiterbarkeit – Android

Der Android-Renderer kann erweitert werden, um mehrere Szenarien zu unterstützen, darunter:
* [Benutzerdefinierte Analyse von Kartenelementen](#custom-parsing-of-card-elements)
* [Benutzerdefiniertes Rendern von Kartenelementen](#custom-rendering-of-card-elements)
* [Benutzerdefiniertes Rendering von Aktionen](#custom-rendering-of-actions) (seit v 1.2)
* [Laden benutzerdefinierter Images](#custom-image-loading) (seit v 1.0.1)
* [Benutzerdefiniertes Laden von Medien](#custom-media-loading) (seit v 1.1)

## <a name="custom-parsing-of-card-elements"></a>Benutzerdefinierte Analyse von Kartenelementen

Du kannst den Parser erweitern, sodass er von dir definierte Kartenelemente unterstützt. Angenommen, wir haben einen neuen Elementtyp, der folgendermaßen aussieht:
```json
{
    "type" : "MyType",
    "MyTypeData" : "My data"
}
```

Die folgenden Zeilen demonstrieren, wie er in einem CardElement-Objekt analysiert wird, das eine Erweiterung von BaseCardElement darstellt:
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

So wird der Parser registriert, und du erhältst ein AdaptiveCard-Objekt, das das benutzerdefinierte Element enthält:
```java
// Create an ElementParserRegistrationObject and add your parser to it
ElementParserRegistration elementParserRegistration = new ElementParserRegistration();
elementParserRegistration.AddParser("MyType", new MyCardElementParser());

AdaptiveCard adaptiveCard = AdaptiveCard.DeserializeFromString(jsonText, elementParserRegistration);
```

Als Nächstes wird das benutzerdefinierte Element gerendert.

## <a name="custom-rendering-of-card-elements"></a>Benutzerdefiniertes Rendern von Kartenelementen

> [!IMPORTANT]
>
> **Liste der wichtigen Änderungen**
>
> [Wichtige Änderungen für v1.2](#breaking-changes-for-v12)

Um unseren eigenen benutzerdefinierten Renderer für den Typ zu definieren, müssen wir zuerst eine Klasse erstellen, die sich von erstreckt ```BaseCardElementRenderer``` :
```java
public class MyCardElementRenderer extends BaseCardElementRenderer
{
    @Override
    public View render(Context context, FragmentManager fragmentManager, ViewGroup viewGroup, BaseCardElement baseCardElement, Vector<IInputHandler> inputActionHandlerList, ICardActionHandler cardActionHandler, HostConfig hostConfig, ContainerStyle containerStyle) {

        //Call findImplObj on baseCardElement to get the instance we returned at parse. We can then cast that object to our type
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

Anschließend registrieren wird diesen Renderer wie folgt:
```java
CardRendererRegistration.getInstance().registerRenderer("MyType", new CustomBlahRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler,  hostConfig);
```

### <a name="breaking-changes-for-v12"></a>Wichtige Änderungen für v1.2

Die ```render``` -Methode wurde so geändert, ```RenderedAdaptiveCard``` dass Sie den-Parameter enthält, und ```ContainerStyle``` wurde für eine renderargs geändert, in der das ContainerStyle jetzt enthalten ist, sodass eine Klasse, die den basecardelta-entrenderer erweitert, wie folgt aussehen sollte:

```
public class MyCardElementRenderer extends BaseCardElementRenderer
{
    @Override
    public View render(RenderedAdaptiveCard renderedAdaptiveCard, Context context, FragmentManager fragmentManager, ViewGroup viewGroup,
                       BaseCardElement baseCardElement, ICardActionHandler cardActionHandler, HostConfig hostConfig, RenderArgs renderArgs)
    { }
}
```

## <a name="custom-parsing-of-card-actions"></a>Benutzerdefinierte Verarbeitung von Karten Aktionen

Ähnlich wie beim Analysieren von benutzerdefinierten Karten Elementen in v 1.2 wurde die Möglichkeit, benutzerdefinierte Aktionen zu analysieren, eingeführt. Angenommen, wir haben einen neuen Aktionstyp, der wie folgt aussieht:
```json
{
    "type" : "MyAction",
    "ActionData" : "My data"
}
```

Anschließend zeigen die folgenden Zeilen, wie Sie Sie in ein "aktionelement" analysieren können, das sich von erstreckt ```BaseActionElement``` :
```java
public class MyActionElement extends BaseActionElement
{
    public MyActionElement(ActionType type) 
    {
        super(type);
    }

    public String getActionData()
    {
        return mActionData;
    }

    public void setActionData(String s)
    {
        mActionData = s;
    }

    private String mActionData;
    public static final String MyActionId = "myAction";
}

public class MyActionParser extends ActionElementParser
{
    @Override
    public BaseActionElement Deserialize(ParseContext context, JsonValue value)
    {
        MyActionElement element = new MyActionElement(ActionType.Custom);
        element.SetElementTypeString(MyActionElement.MyActionId);
        String val = value.getString();
        try {
            JSONObject obj = new JSONObject(val);
            element.setActionData(obj.getString("ActionData"));
        } catch (JSONException e) {
            e.printStackTrace();
            element.setActionData("Failure");
        }
        return element;
    }

    @Override
    public BaseActionElement DeserializeFromString(ParseContext context, String jsonString)
    {
        MyActionElement element = new MyActionElement(ActionType.Custom);
        element.SetElementTypeString(MyActionElement.MyActionId);
        try {
            JSONObject obj = new JSONObject(jsonString);
            element.setBackwardString(obj.getString("ActionData"));
        } catch (JSONException e) {
            e.printStackTrace();
            element.setBackwardString("Failure");
        }
        return element;
    }
}
```

In den nächsten Zeilen wird veranschaulicht, wie Sie den Parser registrieren und ein adaptivecard-Objekt abrufen, das das benutzerdefinierte Action-Element enthält:
```java
// Create an ActionParserRegistration and add your parser to it
ActionParserRegistration actionParserRegistration = new ActionParserRegistration();
actionParserRegistration.AddParser(MyActionElement.MyActionId, new MyActionParser());

ParseContext context = new ParseContext(null, actionParserRegistration);
ParseResult parseResult = AdaptiveCard.DeserializeFromString(jsonText, AdaptiveCardRenderer.VERSION, context);
```

Nächste Schritte zum Rendern der benutzerdefinierten Aktion

## <a name="custom-rendering-of-actions"></a>Benutzerdefiniertes Rendering von Aktionen

Um einen eigenen benutzerdefinierten aktionsrenderer für den Typ zu definieren, müssen wir zuerst eine Klasse erstellen, die sich von erstreckt ```BaseActionElementRenderer``` :
```java
public class MyActionRenderer extends BaseActionElementRenderer
{
    @Override
    public Button render(RenderedAdaptiveCard renderedCard,
                         Context context,
                         FragmentManager fragmentManager,
                         ViewGroup viewGroup,
                         BaseActionElement baseActionElement,
                         ICardActionHandler cardActionHandler,
                         HostConfig hostConfig,
                         RenderArgs renderArgs)
    {
        Button myActionButton = new Button(context);

        CustomActionElement customAction = (CustomActionElement) baseActionElement.findImplObj();

        myActionButton.setBackgroundColor(getResources().getColor(R.color.greenActionColor));
        myActionButton.setText(customAction.getMessage());
        myActionButton.setAllCaps(false);
        myActionButton.setOnClickListener(new BaseActionElementRenderer.ActionOnClickListener(renderedCard, baseActionElement, cardActionHandler));

        viewGroup.addView(myActionButton);

        return myActionButton;
    }
}
```

Anschließend registrieren wird diesen Renderer wie folgt:
```java
CardRendererRegistration.getInstance().registerActionRenderer("myAction", new CustomActionRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, fragmentManager, adaptiveCard, cardActionHandler, hostConfig);
```

## <a name="custom-rendering-of-actions"></a>Benutzerdefiniertes Rendern von Aktionen

> [!IMPORTANT]
> Änderungen am benutzerdefinierten Rendering von Aktionen sind für v1.2 geplant, aber noch nicht abgeschlossen.

## <a name="custom-image-loading"></a>Laden benutzerdefinierter Bilder

### <a name="ionlineimageloader"></a>IOnlineImageLoader

> [!IMPORTANT]
> **Nur ein IOnlineImageLoader-Element kann registriert werden, und es hat Vorrang vor der Standardmethode zum Abrufen von Bildern.**

Damit Entwickler Bilder abrufen können, die von einer Onlinequelle nicht heruntergeladen oder abgerufen werden konnten, oder wenn zuerst einige Schritte ausgeführt werden müssen, um diese abzurufen, wurde IOnlineImageLoader hinzugefügt, um solche Situationen zu beheben. Zum Implementieren von OnlineImageLoader musst du nur die Methode implementieren. 

```java
public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
```

Hier findest du ein Beispiel für ein OnlineImageLoader-Element, das alle Bilder für ein Katzenbild ändern.

```java
public class OnlineImageLoader implements IOnlineImageLoader
{
    public OnlineImageLoader(){}

    @Override
    public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
    {
        String catImageUri = "http://adaptivecards.io/content/cats/1.png";
        byte[] bytes = HttpRequestHelper.get(catImageUri);
        if (bytes == null)
        {
            throw new IOException("Failed to retrieve content from " + catImageUri);
        }

        Bitmap bitmap = BitmapFactory.decodeByteArray(bytes, 0, bytes.length);

        if (bitmap == null)
        {
            throw new IOException("Failed to convert content to bitmap: " + new String(bytes));
        }

        return new HttpRequestResult<>(bitmap);
    }
}
```

Zum Registrieren des Bildladeprogramms musst du lediglich diese Zeile zu deinem Code hinzufügen.

```java
CardRendererRegistration.getInstance().registerOnlineImageLoader(new OnlineImageLoader());
```

### <a name="iresourceresolver-deprecates-ionlineimageloader"></a>IResourceResolver (ersetzt IOnlineImageLoader)

Für v1.2 wurde Unterstützung für vollständige ResourceResolvers zum Android-Renderer hinzugefügt. Die Implementierung eines Ressourcenresolvers ähnelt der von IOnlineImageLoader. Wenn ein Entwickler über ResourceResolvers verfügt, kann er jedoch mehrere Möglichkeiten zum Abrufen von Bildern von jeder beliebigen Datenquelle in einer einzelnen Karte hinzufügen. Dies erfolgt durch das Verknüpfen aller ResourceResolvers mit einem eindeutigen Präfix, das beim Abrufen eines Bilds abgefragt werden soll. 

Du kannst ResourceResolver wie folgt implementieren:

```java
public class ResourceResolver implements IResourceResolver
{
    @Override
    public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync) throws IOException, URISyntaxException
    {
        Bitmap bitmap;
        String dataUri = AdaptiveBase64Util.ExtractDataFromUri(uri);
        CharVector decodedDataUri = AdaptiveBase64Util.Decode(dataUri);
        byte[] decodedByteArray = Util.getBytes(decodedDataUri);
        bitmap = BitmapFactory.decodeByteArray(decodedByteArray, 0, decodedByteArray.length);

        return new HttpRequestResult<>(bitmap);
    }

    @Override
    public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync, int maxWidth) throws IOException, URISyntaxException
    {
        Bitmap bitmap;
        String dataUri = AdaptiveBase64Util.ExtractDataFromUri(uri);
        CharVector decodedDataUri = AdaptiveBase64Util.Decode(dataUri);

        if (uri.startsWith("data:image/svg")) {
            String svgString = AdaptiveBase64Util.ExtractDataFromUri(uri);
            String decodedSvgString = URLDecoder.decode(svgString, "UTF-8");
            Sharp sharp = Sharp.loadString(decodedSvgString);
            Drawable drawable = sharp.getDrawable();
            bitmap = ImageUtil.drawableToBitmap(drawable, maxWidth);
        }
        else
        {
            try
            {
                return genericImageLoaderAsync.loadDataUriImage(uri);
            }
            catch (Exception e)
            {
                return new HttpRequestResult<>(e);
            }
        }

        return new HttpRequestResult<>(bitmap);
    }
}
```

Wie bereits erwähnt kannst du mehrere ResourceResolvers registrieren. Du kannst wie folgt vorgehen, um einen ResourceResolver zu registrieren:

```java
 CardRendererRegistration.getInstance().registerResourceResolver("data", new ResourceResolver());
 CardRendererRegistration.getInstance().registerResourceResolver("anotherPrefix", new AnotherResourceResolver());
```

#### <a name="transforming-an-ionlineimageloader-to-an-iresourceresolver"></a>Transformieren eines IOnlineImageLoader in einen IResourceResolver 

Das Transformieren eines IOnlineImageLoader in einen IResourceResolver ist eine ziemlich einfache Aufgabe, da wir die Methoden für die letztgenannte Aufgabe so ähnlich wie die Methoden für den IOnlineImageLoader gestaltet haben.

```java
 // IOnlineImageLoader
 public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException

 // IResourceResolver
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync) throws IOException, URISyntaxException
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync, int maxWidth) throws IOException, URISyntaxException
```

Wie du siehst, sind dies die größten Änderungen:

* ```loadOnlineImage(String, GenericImageLoaderAsync)``` wurde in ```resolveImageResource(String, GenericImageLoaderAsync)``` umbenannt.
* eine Überladung für ```resolveImageResource(String, GenericImageLoaderAsync)``` wurde hinzugefügt ```resolveImageResource(String, GenericImageLoaderAsync, int)``` , um Szenarios zu unterstützen, in denen die maximale Breite erforderlich ist.

## <a name="custom-media-loading"></a>Laden benutzerdefinierter Medien

> [!IMPORTANT]
> **Beachten ```IOnlineMediaLoader``` Sie ```MediaDataSource``` , dass die API-Ebene 23 oder Android M hinzugefügt wurde.**

Zusammen mit der Einbeziehung des Medienelements wurde auch die IOnlineMediaLoader-Benutzeroberfläche einbezogen, die es Entwicklern ermöglicht, das [MediaDataSource](https://developer.android.com/reference/android/media/MediaDataSource)-Element außer Kraft zu setzen, das für das zugrunde liegende mediaPlayer-Element verwendet wurde. **(Erfordert Android M)**

Der erste erforderliche Schritt besteht darin, eine Klasse zu erstellen, die IOnlineImageLoader implementiert.

```java
@RequiresApi(api = Build.VERSION_CODES.M)
public class OnlineMediaLoader implements IOnlineMediaLoader
{
    /* This class checks if the media source exists */
    public class OnlineFileAvailableChecker extends AsyncTask<String, Void, Boolean>
    {
        public OnlineFileAvailableChecker(String uri)
        {
            m_uri = uri;
        }

        @Override
        protected Boolean doInBackground(String... strings) {
            // if the provided uri is a valid uri or is valid with the resource resolver, then use that
            // otherwise, try to get the media from a local file
            try
            {
                HttpRequestHelper.query(m_uri);
                return true;
            }
            catch (Exception e)
            {
                // Do nothing if the media was not found at all
                e.printStackTrace();
                return false;
            }
        }

        private String m_uri;
   }

       
   @Override
   public MediaDataSource loadOnlineMedia(MediaSourceVector mediaSources, IMediaDataSourceOnPreparedListener mediaDataSourceOnPreparedListener)
   {
       final long mediaSourcesSize = mediaSources.size();
       for(int i = 0; i < mediaSourcesSize; i++)
       {
           String mediaUri = mediaSources.get(i).GetUrl();

           OnlineFileAvailableChecker checker = new OnlineFileAvailableChecker(mediaUri);
           try
           {
               Boolean fileExists = checker.execute("").get();
               if(fileExists)
               {
                   return new MediaDataSourceImpl(mediaUri, mediaDataSourceOnPreparedListener);
               }
           }
           catch (Exception e) { }
       }
       return null;
    }
}
```

Wenn diese Klasse implementiert wurde, kannst du deine OnlineMediaLoader-Klasse registrieren, indem du Folgendes hinzufügst: 
```java
  CardRendererRegistration.getInstance().registerOnlineMediaLoader(new OnlineMediaLoader());
```
