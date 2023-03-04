# GeoRSS

!!! warning "TODO"
    This page needs to be revised

This ROME plugin is for adding location information to RSS/Atom.

### Sample Usage

```java
SyndFeedInput input = new SyndFeedInput();
SyndFeed feed = input.build(new XmlReader(new URL("http://www.geonames.org/recent-changes.xml")));

List<SyndEntry>; entries = feed.getEntries();
for (SyndEntry entry : entries) {
    GeoRSSModule geoRSSModule = GeoRSSUtils.getGeoRSS(entry);
    System.out.println(entry.getTitle() + " : lat="
        + geoRSSModule.getLatitude() + ",lng="
        + geoRSSModule.getLongitude() + ", desc="
        + entry.getDescription().getValue() + "; time="
        + entry.getPublishedDate());
}

//to generate a GeoRSS item

GeoRSSModule geoRSSModule = new W3CGeoModuleImpl();
//GeoRSSModule geoRSSModule = new SimpleModuleImpl();
geoRSSModule.setLatitude(47.0);
geoRSSModule.setLongitude(9.0);
entry.getModules().add(geoRSSModule);
```

More information here:
[http://georss.geonames.org/](http://georss.geonames.org/)
