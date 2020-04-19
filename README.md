# Http branch

This is the **simplest** solution, no ciphred connection implemented.

In this case the flask app expose a standard **http** service, except the listening port no other changes are mede from the default. 

The app is dockerized with the Dockerfile contained in the Docker directory with the `http` tag and deployed on the kubernetes cluster as a deployment. 

This is finally exposed externally with a LoadBalancer service, to make more clear what is going on the service is exposed on a different port than the one exposed from the pods.
