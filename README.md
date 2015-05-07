# Open Graph Protocol
The Open Graph protocol enables any web page to become a rich object in a social graph. For instance, this is used on Facebook to allow any web page to have the same functionality as any other object on Facebook.

Moreover, they use specal facebook widgets like: ‘Like’, ‘Share’, ‘Comments’ and ‘Recommend’ on their websites. The Open Graph Meta tags (or Facebook Open Graph API) that I am going to describe today will help you control over information to be shared on facebook (like url, title, image and description).

## <a name='TOC'>Table of Contents</a>

  1. [Basic Metadata](#BasicMetadata)
    - [Overview](#overView)
    - [Optional Metadata](#optionalMetadata)

## <a name='BasicMetadata'>Basic Metadata</a>

### <a name='overView'>Overview</a>
To turn your web pages into graph objects, you need to add basic metadata to your page. We've based the initial version of the protocol on RDFa which means that you'll place additional <meta> tags in the <head> of your web page. The four required properties for every page are:

```
og:title - The title of your object as it should appear within the graph, e.g., "The Rock".
og:type - The type of your object, e.g., "video.movie". Depending on the type you specify, other properties may also be required.
og:image - An image URL which should represent your object within the graph.
og:url - The canonical URL of your object that will be used as its permanent ID in the graph, e.g., "http://www.imdb.com/title/tt0117500/".
```
As an example, the following is the Open Graph protocol markup for The Rock on IMDB:
```html
<html prefix="og: http://ogp.me/ns#">
<head>
<title>The Rock (1996)</title>
<meta property="og:title" content="The Rock" />
<meta property="og:type" content="video.movie" />
<meta property="og:url" content="http://www.imdb.com/title/tt0117500/" />
<meta property="og:image" content="http://ia.media-imdb.com/images/rock.jpg" />
...
</head>
...
</html>
```

### <a name='optionalMetadata'>Optional Metadata</a>
The following properties are optional for any object and are generally recommended:
```
og:audio - A URL to an audio file to accompany this object.
og:description - A one to two sentence description of your object.
og:determiner - The word that appears before this object's title in a sentence. An enum of (a, an, the, "", auto). If auto is chosen, the consumer of your data should chose between "a" or "an". Default is "" (blank).
og:locale - The locale these tags are marked up in. Of the format language_TERRITORY. Default is en_US.
og:locale:alternate - An array of other locales this page is available in.
og:site_name - If your object is part of a larger web site, the name which should be displayed for the overall site. e.g., "IMDb".
og:video - A URL to a video file that complements this object.
For example (line-break solely for display purposes):
```

```html
<meta property="og:audio" content="http://example.com/bond/theme.mp3" />
<meta property="og:description"
  content="Sean Connery found fame and fortune as the
           suave, sophisticated British agent, James Bond." />
<meta property="og:determiner" content="the" />
<meta property="og:locale" content="en_GB" />
<meta property="og:locale:alternate" content="fr_FR" />
<meta property="og:locale:alternate" content="es_ES" />
<meta property="og:site_name" content="IMDb" />
<meta property="og:video" content="http://example.com/bond/trailer.swf" />
```
