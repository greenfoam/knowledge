Aaron Patterson和Mike Dalessio开发了一个新的Ruby解析HTML/XML的ruby库 － Nokogiri。他的速度比目前应用的最广泛的Hpricot还要快许多。经过Benchmark测试表明，Nokogiri在加载XML文档的速度是Hpricot的7倍，在XPATH搜索的速度是Hpricot的5倍，而在CSS选择器的搜索上面是Hpricot的1.62倍。

因此Nokogiri被认为有可能取代Hpricot的新一代Ruby的解析库，他能够解析HTML/XML文件，能够提供XPATH支持，CSS选择器支持。安装Nokogiri的办法很简单： gem install nokogiri
[nokogiri](http://www.oschina.net/p/nokogiri)