# Http branch

This is the **simplest** solution, no ciphred connection implemented.

In this case the flask app expose a standard **http** service, except the listening port no other changes are mede from the default. 

The app is dockerized with the Dockerfile contained in the Docker directory with the `http` tag with the command:
    
    docker build -f ../docker/Dockerfile -t atoserik/flask-kube-example:http .

The docker image is executed from the Kubernetes cluster as deployment as described in the `-deployment.yaml` file contained in the kube directory.  

This is finally exposed externally with a LoadBalancer service, to make more clear what is going on the service is exposed on a different port than the one exposed from the pods.
