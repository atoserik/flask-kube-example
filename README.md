# http-ingress branch

This is a quite better implementation since the native service is not externally exposed, even in this case no ciphered connection are obtained. 

To expose the service is used an ingress which is a resource generally well documented.
In this repo an ngix-ingress is choosen, and to deploy the ingress-controller [this](https://kubernetes.github.io/ingress-nginx/deploy/) is the proper guide. 

Once the ingress-controller is up&running all the yaml file contained in the kube directory can be applyed.

It's important to highlight that the `-service.yaml` is changed: now the type of the service is ClusterIP which is the default and that does't expose the service outide the kube cluster. 

Moreover there is the new `-ingress.yaml` file, with the proper configurations.
