# flask-kube-example

This repo aims at summarizing the configuration needed to deploy a **flask** application in a docker container and then run it with a **kubernetes** cluster.

More in details the interesting objective of the repo is to explore the different implementations to expose a flask service with or without a secured connection with TLS.

To have a bettere understanding there are more branch available each one with a different configuration implemented:
- [http](https://github.com/atoserik/flask-kube-example/tree/http): the flask expose a simple http service, and this is exposed with a LoadBalancer service
- [https](https://github.com/atoserik/flask-kube-example/tree/https): the flask expose a http over tls service, and this is exposed with a LoadBalancer service
- [http-ingress](https://github.com/atoserik/flask-kube-example/tree/http-ingress): the flask expose a simple http service, and this is exposed with an ingress
- [https-ingress](https://github.com/atoserik/flask-kube-example/tree/https-ingress): the flask expose a http over tls service, and this is exposed with an ingress
- [http-ingress-tls](https://github.com/atoserik/flask-kube-example/tree/http-ingress-tls): the flask expose a simple http service, and this is exposed with an ingress that accept ciphred over tls connection
- [https-ingress-tls](https://github.com/atoserik/flask-kube-example/tree/https-ingress-tls): the flask expose a https service, and this is exposed with an ingress that accept ciphred over tls connection

For each branch a different README will give more detail about the implemented solution. 

Moving from the `http` branch to the `https-ingress-tls` one in the exposed order is useful to perform all the steps, to have a quick reference the key steps are summarized:

  * A simple flask (without tls) is implemented
  * Is dockerized with `docker build -f ../docker/Dockerfile -t atoserik/flask-kube-example:http .`
  * A couple of key/cert is created with `openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365`
  * The key/cert is used in the flask app adding the proper `ssl_context()`
  * The new version of the app is dockerized `docker build -f ../docker/Dockerfile -t atoserik/flask-kube-example:https .`
  * As ingress, I've choosen the nginx one. To deploy the same on your cluster follow [this guide](https://kubernetes.github.io/ingress-nginx/deploy/)
  * To better manage the ingress and to go deeper in the annotations of the nginx ingress [this repo](https://github.com/kubernetes/ingress-nginx/blob/master/docs/user-guide/nginx-configuration/annotations.md) is what you are looking for. 

Any contribute or feedback is appreciated. 

Hope this will be useful for those who are approaching to deploy some simple applications in a non-production environment. 
