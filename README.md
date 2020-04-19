# flask-kube-example

This repo aims to summarize the configuration needed to deploy a **flask** application in a docker container and then orchestrated with a **kubernetes** cluster. 

More in details the interesting objective of the repo is to expose a flask service with a secured connection with TLS, this can be obtained in multiple ways depending on where the connection need to be deciphered. 

To have a bettere understanding there are more branch available each one with a different configuration implemented:
- [http](https://github.com/atoserik/flask-kube-example/tree/http): the flask expose a simple http service, and this is exposed with a LoadBalancer service
- [https](https://github.com/atoserik/flask-kube-example/tree/https): the flask expose a http over tls service, and this is exposed with a LoadBalancer service
- [http-ingress](https://github.com/atoserik/flask-kube-example/tree/http-ingress): the flask expose a simple http service, and this is exposed with an ingress
- [https-ingress](https://github.com/atoserik/flask-kube-example/tree/https-ingress): the flask expose a http over tls service, and this is exposed with an ingress
- [http-ingress-tls](https://github.com/atoserik/flask-kube-example/tree/http-ingress-tls): the flask expose a simple http service, and this is exposed with an ingress that accept ciphred over tls connection

For each branch a different README will give more detail about the implemented solution. 

Any contribute or feedback is appreciated. 

Hope this will be useful at least to some noob like me that faced this trying to deploy some simple application in a non-production environment. 
