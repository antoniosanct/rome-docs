# Content

!!! warning "TODO"
    This page needs to be revised

This plugin is for use content:encoded in feeds.

### Sample Usage

```java
SyndFeedInput input = new SyndFeedInput();
SyndFeed syndfeed = input.build(new XmlReader(feed.toURL()));

Module module = syndfeed.getModule("http://purl.org/rss/1.0/modules/content/");
ContentModule content = (ContentModule) module;

Iterator it = content.getEncodeds().iterator();
System.out.println( it.next() );
```
