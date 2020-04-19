# http-ingress-tls

This is another intreresting solution that make possible to have an ingress covered by tls that redirect over multiple services that can not expose http over tls. 

This implementation is obtained defining a secret that refers the key.pem and the cert.pem file this can be done with the command:

    kubectl create secret tls flask-example-tls --key app/key.pem --cert app/cert.pem

Then the secret is recalled in the `-ingress.yaml` file, that now don't have the annotation about the backend-protocol. 
