# http-ingress branch

This is a quite better implementation since the native service is not externally exposed, even in this case no ciphered connection are obtained. 

To expose the service is used an ingress which is a resource generally well documented.
In this repo an ngix-ingress is choosen, and to deploy the ingress-controller [this](https://kubernetes.github.io/ingress-nginx/deploy/) is the proper guide. 

Once the ingress-controller is up&running can be deployed all the yaml file contained in the kube directory. 
