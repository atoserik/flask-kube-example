# flask-kube-example

This repo aims to summarize the configuration needed to deploy a **flask** application in a docker container and then orchestrated with a **kubernetes** cluster. 

More in details the interesting objective of the repo is to expose a flask service with a secured connection with TLS, this can be obtained in multiple ways depending on where the connection need to be deciphered. 

To have a bettere understanding there are more branch available each one with a different configuration implemented:
- http: the flask expose a simple http service, and this is exposed with a ClusterIp service
- https: the flask expose a http over tls service, and this is exposed with a ClusterIp service
- http-ingress: the flask expose a simple http service, and this is exposed with an ingress
- https-ingress: the flask expose a http over tls service, and this is exposed with an ingress
- http-ingress-tls: the flask expose a simple http service, and this is exposed with an ingress that accept ciphred over tls connection

For each branch a different README will give more detail about the implemented solution. 

Any contribute or feedback is appreciated. 

Hope this will be useful at least to some noob like me that faced this trying to deploy some simple application in a non-production environment. 
