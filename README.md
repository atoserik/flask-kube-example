# Https branch

This is a solution that implement a ciphred connection.

The first step is to create the couple of key/cert files:

    openssl req -x509 -newkey rsa:4096 -nodes -out cert.pem -keyout key.pem -days 365    

Then the flask app is modified to expose an **https** service; to do that the `ssl_context=('cert.pem', 'key.pem')` is added in the `app.run()` method. 

Finally the app is dockerized with the same Dockerfile contained in the Docker directory, but with a different tag: `https`; and deployed on the kubernetes cluster as a deployment.

The service is exposed externally with a LoadBalancer service as in the `http` branch.

