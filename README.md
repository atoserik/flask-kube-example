# https-ingress-tls

This is someway the more complex solution, but also the more customizable solutions, in fact gives the possibility to have a couple of key/cert for the main ingress and then other couple key/cert for each service on which the ingress redirect calls. 

The software is obtained merging the http-ingress-tls branch (taking the ingress and the service configurations) with the https-ingress branch (taking the deployment that refers to the https tagged docker image). 
