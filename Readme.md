# Important to know about external and internal reachability/routing of/to the FROST-server 

The attribute "ports" defines the mapping from external to internal port of a docker container (left=external, right = internal: 8080:8080). <br/>
**Don't change the internal port**, only the external port when setting up a new FROST-Server container (i.e. **keep 8080 AND 1883 fixed**).

## Case 1: Default
For the (default) case that FROST-server shall be reachable at the standard server adresse (can be URL or IP) but with generic port adress:

    services:

      web:

        image: fraunhoferiosb/frost-server:latest

        environment:

          - serviceRootUrl=http://<IP-adresse/main-server-URL>:<PORT-number>/FROST-Server

          - ...

        ports:

          - 8080:8080

          - 1883:1883


## Case 2: URL-Specific
For the case that FROST-server shall be reachable at a specific URL, it must be specified to be reachable inside only from the localhost (127.0.0.1) and from outside only by a reverse proxy (needs to be configured elsewhere at e.g. apache or Tomcat server):


    services:
  
      web:

        image: fraunhoferiosb/frost-server:latest

        environment:

          - serviceRootUrl=https://sensor-server.hef.tum.de/frost

          - ...

        ports:

          - 127.0.0.1:8080:8080

          - 127.0.0.1:1883:1883
        

