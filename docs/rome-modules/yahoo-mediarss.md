# Yahoo! MediaRSS

!!! warning "TODO"
    This page needs to be revised

This plugin is for use with Yahoo! MediaRSS/Flickr Photostreams

## Sample Usage

```java
SyndFeed feed =  input.build( myRSSFile );
List entries = feed.getEntries();
for( int i = 0; i < entries.size(); i++ ){
    System.out.println( ((SyndEntry) entries.get(i)).getModule( MediaModule.URI ) );
}

//Alternatively, to add a media item to an entry:

MediaContent[] contents = new MediaContent[1];
MediaContent myItem = new MediaContent( new UrlReference("http://me.com/movie.mpg") );
contents[0] = myItem();
Metadata md = new Metadata();
Thumbnail[] thumbs = new Thumbnail[2];
thumbs[0] = new Thumbnail( new URL("http://me.com/movie1.jpg") );
thumbs[1] = new Thumbnail( new URL("http://me.com/movie2.jpg") );
md.setThumbnail( thumbs );
myItem.setMetadata( md );
MediaEntryModuleImpl module = new MediaEntryModuleImpl();
module.setMediaContents( contents );
mySyndEntry.getModules().add( module );
```
