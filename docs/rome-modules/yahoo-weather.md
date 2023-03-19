# Yahoo! WeatherRSS

!!! warning "TODO"
    This page needs to be revised

This plugin is for use the
[Yahoo! Weather service](http://developer.yahoo.com/weather/).

## Sample Usage

```java
SyndFeed feed = input.build( ... );
YWeatherFeedModule yfeed = (YWeatherFeedModule) feed.getModule( YWeatherFeedModule.URI );
System.out.println( yfeed.getLocation().getCity() );
SyndEntry entry = (SyndEntry) feed.getEntries().get(0);
YWeatherEntryModule yentry = (YWeatherEntryModule) entry.getModule( YWeatherEntryModule.URI );
System.out.println( yentry.getForecasts()[0].getHigh() );

//Optionally, to add Weather information to a feed:
SyndEntry entry = new SyndEntryImpl();
YWeatherEntryModule yentry = new YWeatherModuleImpl();
yentry.setCondition( Condition("Partly Cloudy", ConditionCode.PARTLY_CLOUDY, 65, new Date() ) );
entry.getModules.add(yentry);
```
