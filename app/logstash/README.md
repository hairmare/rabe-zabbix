# Zabbix logstash monitoring
Monitoring of [logstash](https://www.elastic.co/products/logstash).

## Usage
1. Import the
   [`Template_App_logstash_active.xml`](Template_App_logstash_active.xml)
   into your Zabbix server (click on the `Raw` button to download).
2. Add the template to your host (or stack template)
3. Check if new data arrives

This template is part of [RaBe's Zabbix template and helpers
collection](https://github.com/radiorabe/rabe-zabbix).
## Template App logstash active
Application template for [logstash](https://www.elastic.co/products/logstash/).
### Items
* CPU utilization (total) of "java" processes (avg5) in % (`proc.cpu.util[java,logstash,total,,avg5]`)  
  5 minute average CPU utilization in percent of the logstash java process.
* Memory usage (rss) of "java" processes (`proc.mem[java,logstash,,,rss]`)  
  Memory usage in bytes of the logstash java process.
* Number of "java" processes (`proc.num[java,logstash,]`)  
  Number of running logstash `java` processes.
### Triggers
* High: No running logstash java process on {HOST.NAME}
  ```
  {Template App logstash active:proc.num[java,logstash,].last(0)}<1
  ```

## License
This template is free software: you can redistribute it and/or modify it under
the terms of the GNU Affero General Public License as published by the Free
Software Foundation, version 3 of the License.

## Copyright
Copyright (c) 2017 [Radio Bern RaBe](http://www.rabe.ch)
