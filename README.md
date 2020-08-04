
### `Intro`
The project is going to organise the bug hunting, feature request and road maps for [bananospl.it](http://bananospl.it/).

[interface]: https://raw.githubusercontent.com/anzerr/bananospl.it/master/assets/interface.png "interface"
![alt text][interface]

### `Bug and feature request`
If you find a bug you're welcome to create an issue with info inspected outcomes and how to recreate it Feature suggestion or quality of life changes can also be done through the issues.

### `Translation files`
For the moment the transition files are a future feature. When they are fully implemented pull requests for more language support is welcome.

### `Architecture`
This project was built with a small set of tools. The http services, broker and workers are all built with typescript.Theres backend services use a low amount of dependencies from npm a total of 4 where used

``` json
["mongodb","reflect-metadata", "@elastic/elasticsearch", "ws"]
```

The two databases used are mongodb and elastic. 
Mongodb to store the state of the applications and Elastic to store all the information that is searchable. 
The front api has a http and ws interface there's a Haproxy load balancer infront to do the routing/filtering to the services.
Other than that there's netdata for the logging stats.
So In total there are 19 services in this stack there's 7 workers, 5 http services, 2 databases, 1 haproxy, 1 netdata, 1 client,1 broker and 1 node.

The image below should explain the links between the services and workers better.

[service]: https://raw.githubusercontent.com/anzerr/bananospl.it/master/assets/service.png "service"
![alt text][service]