# https-ingress branch

In this branch an intresting solution in implemented: the ingress is "open" and the cert/key are refered to the single service (the flask app in the case). With a little more experience on the annotations of the ingress (rewrite-target among the others) more sofisticated implementations are possible each one with its key/cert couple if needed. It is also to expose different services some of those that requires https and other that don't. 

The deployment refers to the https tagged image of the docker image, the ingress is defined to comunicate with the flask service over HTTPS. 
