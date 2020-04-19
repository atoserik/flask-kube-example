# Https branch

This is the first solution, that implement a ciphred connection.

In this case the flask app expose an **https** service, to do that the `ssl_context=('cert.pem', 'key.pem')` is added in the `app.run()` method. 

The app is dockerized with the same Dockerfile contained in the Docker directory with a different tag: `https`; and deployed on the kubernetes cluster as a deployment.

This is finally exposed externally with a LoadBalancer service, to make more clear what is going on the service is exposed on a different port than the one exposed from the pods.
