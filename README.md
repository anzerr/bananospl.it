
### `Intro`
The project is going to orangise the bug hunting, feature request and road map of feature for [bananospl.it](http://bananospl.it/).

[logo]: https://raw.githubusercontent.com/anzerr/bananospl.it/master/assets/interface.png "interface"
![alt text][logo]

### `Bug and feature request`
If you find a bug you're welcome to create a issue with info inspected outcomse and how to recreate it. 

Feature sugestion or quality of life changes can also be done throught the issues.

### `Translation files`
For the moment the transtion files are a future feature. When they are fully implemented pull request for more language support is welcome.

### `Architecture`
This project was built with a small set of tools. The http services, broker and workers are all build with typescript.
Theres backend services use a low amount of dependencies from npm a total of 4 where used

``` json
["mongodb","reflect-metadata", "@elastic/elasticsearch", "ws"]
```

The two databases used are mongodb and elastic. Mongodb to store the state of the applications and Elastic to store all the information that is searchable
The front api has a http and ws interface there's a Haproxy load balancer infront to do the routing/filtering to the services.
Other then that there's netdata for the logging stats.
So In total there's 19 services in this stack there's 7 workers, 5 http services, 2 database, 1 haproxy, 1 netdata, 1 client, 1 broker and 1 node
The image below should explain the links between the services and workers better.

[logo]: https://raw.githubusercontent.com/anzerr/bananospl.it/master/assets/service.png "service"
![alt text][logo]