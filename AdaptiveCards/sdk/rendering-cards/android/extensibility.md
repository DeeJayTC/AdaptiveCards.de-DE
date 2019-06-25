---
title: Android SDK
author: bekao
ms.author: bekao
ms.date: 09/27/2017
ms.topic: article
ms.openlocfilehash: 378171186599dd8d103111da183b7fc2e6e01c42
ms.sourcegitcommit: e002a988c570072d5bc24a1242eaaac0c9ce90df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2019
ms.locfileid: "67134265"
---
# <a name="extensibility---android"></a><span data-ttu-id="5c434-102">Erweiterbarkeit – Android</span><span class="sxs-lookup"><span data-stu-id="5c434-102">Extensibility - Android</span></span>

## <a name="custom-parsing-of-card-elements"></a><span data-ttu-id="5c434-103">Benutzerdefinierte Analyse von Kartenelementen</span><span class="sxs-lookup"><span data-stu-id="5c434-103">Custom Parsing of Card Elements</span></span>

<span data-ttu-id="5c434-104">Du kannst den Parser erweitern, sodass er von dir definierte Kartenelemente unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5c434-104">You may extend the parser to support card elements that you have defined.</span></span> <span data-ttu-id="5c434-105">Angenommen, wir haben einen neuen Elementtyp, der folgendermaßen aussieht:</span><span class="sxs-lookup"><span data-stu-id="5c434-105">For example, say we have a new element type that looks like this:</span></span>
```json
{
    "type" : "MyType",
    "MyTypeData" : "My data"
}
```

<span data-ttu-id="5c434-106">Die folgenden Zeilen demonstrieren, wie er in einem CardElement-Objekt analysiert wird, das eine Erweiterung von BaseCardElement darstellt:</span><span class="sxs-lookup"><span data-stu-id="5c434-106">Then the following lines demonstrate how to parse it into a CardElement that extends from the BaseCardElement:</span></span>
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

<span data-ttu-id="5c434-107">So wird der Parser registriert, und du erhältst ein AdaptiveCard-Objekt, das das benutzerdefinierte Element enthält:</span><span class="sxs-lookup"><span data-stu-id="5c434-107">And this is how to register the parser and get an AdaptiveCard object that contains the custom element:</span></span>
```java
// Create an ElementParserRegistrationObject and add your parser to it
ElementParserRegistration elementParserRegistration = new ElementParserRegistration();
elementParserRegistration.AddParser("MyType", new MyCardElementParser());

AdaptiveCard adaptiveCard = AdaptiveCard.DeserializeFromString(jsonText, elementParserRegistration);
```

<span data-ttu-id="5c434-108">Als Nächstes wird das benutzerdefinierte Element gerendert.</span><span class="sxs-lookup"><span data-stu-id="5c434-108">Next comes rendering the custom element</span></span>

## <a name="custom-rendering-of-card-elements"></a><span data-ttu-id="5c434-109">Benutzerdefiniertes Rendern von Kartenelementen</span><span class="sxs-lookup"><span data-stu-id="5c434-109">Custom Rendering of Card Elements</span></span>

<span data-ttu-id="5c434-110">Damit wir einen benutzerdefinierten Renderer für unseren Typ definieren können, müssen wir zunächst eine Klasse erstellen, die aus BaseCardElementParser erweitert wird:</span><span class="sxs-lookup"><span data-stu-id="5c434-110">To define our own custom renderer for our type, we must first create a class that extends from BaseCardElementParser:</span></span>
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

<span data-ttu-id="5c434-111">Anschließend registrieren wird diesen Renderer wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5c434-111">We then register this renderer like so:</span></span>
```java
CardRendererRegistration.getInstance().registerRenderer("MyType", new CustomBlahRenderer());

RenderedAdaptiveCard renderedCard = AdaptiveCardRenderer.getInstance().render(context, getSupportFragmentManager(), adaptiveCard, cardActionHandler, new HostConfig());
```

## <a name="custom-rendering-of-actions"></a><span data-ttu-id="5c434-112">Benutzerdefiniertes Rendern von Aktionen</span><span class="sxs-lookup"><span data-stu-id="5c434-112">Custom rendering of actions</span></span>

[!IMPORTANT]
> <span data-ttu-id="5c434-113">Änderungen am benutzerdefinierten Rendering von Aktionen sind für v1.2 geplant, aber noch nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5c434-113">Changes to the custom rendering of actions are planned for v1.2 but are not completed yet</span></span>

## <a name="custom-image-loading"></a><span data-ttu-id="5c434-114">Laden benutzerdefinierter Bilder</span><span class="sxs-lookup"><span data-stu-id="5c434-114">Custom image loading</span></span>

### <a name="ionlineimageloader"></a><span data-ttu-id="5c434-115">IOnlineImageLoader</span><span class="sxs-lookup"><span data-stu-id="5c434-115">IOnlineImageLoader</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c434-116">**Nur ein IOnlineImageLoader-Element kann registriert werden, und es hat Vorrang vor der Standardmethode zum Abrufen von Bildern.**</span><span class="sxs-lookup"><span data-stu-id="5c434-116">**Only one IOnlineImageLoader can be registered and it takes precedence against the default way of retrieving images**</span></span>

<span data-ttu-id="5c434-117">Damit Entwickler Bilder abrufen können, die von einer Onlinequelle nicht heruntergeladen oder abgerufen werden konnten, oder wenn zuerst einige Schritte ausgeführt werden müssen, um diese abzurufen, wurde IOnlineImageLoader hinzugefügt, um solche Situationen zu beheben.</span><span class="sxs-lookup"><span data-stu-id="5c434-117">In order to allow developers to get images that could not just be downloaded or retrieved from an online source or required previous steps before they could be retrieved, the IOnlineImageLoader was added to solve this kind of situations.</span></span> <span data-ttu-id="5c434-118">Zum Implementieren von OnlineImageLoader musst du nur die Methode implementieren.</span><span class="sxs-lookup"><span data-stu-id="5c434-118">To implement an OnlineImageLoader you must only implement the method</span></span> 

```java
public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
```

<span data-ttu-id="5c434-119">Hier findest du ein Beispiel für ein OnlineImageLoader-Element, das alle Bilder für ein Katzenbild ändern.</span><span class="sxs-lookup"><span data-stu-id="5c434-119">Here's an example of an OnlineImageLoader which changes all images for a cat image</span></span>

```java
public class OnlineImageLoader implements IOnlineImageLoader
{
    public OnlineImageLoader(){}

    @Override
    public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException
    {
        String catImnageUri = "http://adaptivecards.io/content/cats/1.png";
        byte[] bytes = HttpRequestHelper.get(catImnageUri);
        if (bytes == null)
        {
            throw new IOException("Failed to retrieve content from " + catImnageUri);
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

<span data-ttu-id="5c434-120">Zum Registrieren des Bildladeprogramms musst du lediglich diese Zeile zu deinem Code hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5c434-120">Finally, to register this image loader, you must only add this line to your code.</span></span>

```java
CardRendererRegistration.getInstance().registerOnlineImageLoader(new OnlineImageLoader());
```

### <a name="iresourceresolver-deprecates-ionlineimageloader"></a><span data-ttu-id="5c434-121">IResourceResolver (ersetzt IOnlineImageLoader)</span><span class="sxs-lookup"><span data-stu-id="5c434-121">IResourceResolver (deprecates IOnlineImageLoader)</span></span>

<span data-ttu-id="5c434-122">Für v1.2 wurde Unterstützung für vollständige ResourceResolvers zum Android-Renderer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5c434-122">For v1.2, the support for full ResourceResolvers was added to the android renderer.</span></span> <span data-ttu-id="5c434-123">Die Implementierung eines Ressourcenresolvers ähnelt der von IOnlineImageLoader. Wenn ein Entwickler über ResourceResolvers verfügt, kann er jedoch mehrere Möglichkeiten zum Abrufen von Bildern von jeder beliebigen Datenquelle in einer einzelnen Karte hinzufügen. Dies erfolgt durch das Verknüpfen aller ResourceResolvers mit einem eindeutigen Präfix, das beim Abrufen eines Bilds abgefragt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c434-123">The implementation of a resource resolver is really similar to that of a IOnlineImageLoader but having ResourceResolvers allows a developer to add multiple ways to retrieve images from any kind of source in a single card, this is done by linking each ResourceResolver to a unique prefix which will be queried when trying to retrieve an image.</span></span> 

<span data-ttu-id="5c434-124">Du kannst ResourceResolver wie folgt implementieren:</span><span class="sxs-lookup"><span data-stu-id="5c434-124">You can implement a ResourceResolver similar to this</span></span>

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

<span data-ttu-id="5c434-125">Wie bereits erwähnt kannst du mehrere ResourceResolvers registrieren. Du kannst wie folgt vorgehen, um einen ResourceResolver zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="5c434-125">As mentioned previously, you can register multiple ResourceResolvers, to register a ResourceResolver you can do this</span></span>

```java
 CardRendererRegistration.getInstance().registerResourceResolver("data", new ResourceResolver());
 CardRendererRegistration.getInstance().registerResourceResolver("anotherPrefix", new AnotherResourceResolver());
```

#### <a name="transforming-an-ionlineimageloader-to-an-iresourceresolver"></a><span data-ttu-id="5c434-126">Transformieren eines IOnlineImageLoader in einen IResourceResolver</span><span class="sxs-lookup"><span data-stu-id="5c434-126">Transforming an IOnlineImageLoader to an IResourceResolver</span></span> 

<span data-ttu-id="5c434-127">Das Transformieren eines IOnlineImageLoader in einen IResourceResolver ist eine ziemlich einfache Aufgabe, da wir die Methoden für die letztgenannte Aufgabe so ähnlich wie die Methoden für den IOnlineImageLoader gestaltet haben.</span><span class="sxs-lookup"><span data-stu-id="5c434-127">Transforming an IOnlineImageLoader to an IResourceResolver is a fairly easy task as the methods for the latter were tried to keep as similar as the IOnlineImageLoader as possible</span></span>

```java
 // IOnlineImageLoader
 public HttpRequestResult<Bitmap> loadOnlineImage(String url, GenericImageLoaderAsync loader) throws IOException, URISyntaxException

 // IResourceResolver
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync) throws IOException, URISyntaxException
 public HttpRequestResult<Bitmap> resolveImageResource(String uri, GenericImageLoaderAsync genericImageLoaderAsync, int maxWidth) throws IOException, URISyntaxException
```

<span data-ttu-id="5c434-128">Wie du siehst, sind dies die größten Änderungen:</span><span class="sxs-lookup"><span data-stu-id="5c434-128">As you can see, the biggest changes are</span></span>
* <span data-ttu-id="5c434-129">loadOnlineImage(String, GenericImageLoaderAsync) wurde in resolveImageResource(String, GenericImageLoaderAsync) umbenannt</span><span class="sxs-lookup"><span data-stu-id="5c434-129">loadOnlineImage(String, GenericImageLoaderAsync) was renamed to resolveImageResource(String, GenericImageLoaderAsync)</span></span>
* <span data-ttu-id="5c434-130">Eine Überladung für resolveImageResource(String, GenericImageLoaderAsync) wurde als resolveImageResource(String, GenericImageLoaderAsync, int) hinzugefügt, um Szenarien zu unterstützen, in denen eine maximale Breite erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="5c434-130">an overload for resolveImageResource(String, GenericImageLoaderAsync) was added as resolveImageResource(String, GenericImageLoaderAsync, int) in order to support scenarios where the max width is required</span></span>

## <a name="custom-media-loading"></a><span data-ttu-id="5c434-131">Benutzerdefiniertes Laden von Medien</span><span class="sxs-lookup"><span data-stu-id="5c434-131">Custom media loading</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c434-132">**Nicht vergessen: IOnlineMediaLoader erfordert, dass MediaDataSource in API-Ebene 23 oder Android M hinzugefügt wurde.**</span><span class="sxs-lookup"><span data-stu-id="5c434-132">**Remember IOnlineMediaLoader requires MediaDataSource was added in API level 23 or Android M**</span></span>

<span data-ttu-id="5c434-133">Zusammen mit der Einbeziehung des Medienelements wurde auch die IOnlineMediaLoader-Benutzeroberfläche einbezogen, die es Entwicklern ermöglicht, das [MediaDataSource](https://developer.android.com/reference/android/media/MediaDataSource)-Element außer Kraft zu setzen, das für das zugrunde liegende mediaPlayer-Element verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5c434-133">Along with the inclusion of the media element, also was the inclusion of the IOnlineMediaLoader interface which allows developers to override the [MediaDataSource](https://developer.android.com/reference/android/media/MediaDataSource) used for the underlying mediaPlayer element.</span></span> <span data-ttu-id="5c434-134">**(Erfordert Android M)**</span><span class="sxs-lookup"><span data-stu-id="5c434-134">**(Requires android M)**</span></span>

<span data-ttu-id="5c434-135">Der erste erforderliche Schritt besteht darin, eine Klasse zu erstellen, die IOnlineImageLoader implementiert.</span><span class="sxs-lookup"><span data-stu-id="5c434-135">The first needed thing to do is creating a class that implements IOnlineImageLoader</span></span>

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

<span data-ttu-id="5c434-136">Wenn diese Klasse implementiert wurde, kannst du deine OnlineMediaLoader-Klasse registrieren, indem du Folgendes hinzufügst:</span><span class="sxs-lookup"><span data-stu-id="5c434-136">Once this class has been implemented, you can register your OnlineMediaLoader class by adding</span></span> 
```java
  CardRendererRegistration.getInstance().registerOnlineMediaLoader(new OnlineMediaLoader());
```
