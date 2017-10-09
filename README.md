# docker-predictionio
PredictionIO is an open-source Machine Learning server for developers and data scientists to build and deploy predictive applications in a fraction of the time.

This container uses Apache Spark (1.6.3), HBase (1.2.6) and Elasticsearch(1.7.6). The PredictionIO version is the latest stable version 0.11.0.
####Use it interactively for development:
1. First, do either i) or ii) below:
  i.(faster; stable version) obtain docker image from public docker registry:

    ```Bash
    $ docker run -it -p 8000:8000 maitruong/predictionio /bin/bash
    ```
  ii. (slower) build docker image from local Dockerfile: cd to the path containing the Dockerfile, then:
    
    ```Bash
    $ docker build -t predictionio .
    ```
    then:
    
    ```Bash
    $ docker run -p 8000:8000 --name predictionio_instance -it predictionio /bin/bash
    ```
    
2. Then in docker container, start all services and check they are started
  ```Bash
  $ pio-start-all
  or 
  $ pio eventserver &  # if using PostgreSQL or MySQL
  $
  $ pio status # to check everything is okay
  ```
