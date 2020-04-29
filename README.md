# http-ingress-tls

This is another intreresting solution that make possible to have an ingress covered by tls that redirect over multiple services that don't expose http over tls. 

This implementation is obtained creating the couple of key/cert file with the command:
    
    openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365
    
And defining a secret that refers the key.pem and the cert.pem files with the command:

    kubectl create secret tls flask-example-tls --key <path>/key.pem --cert <path>/cert.pem

Then the secret is mentioned in the `-ingress.yaml` file. 
