# Short introduction to why and when to use Kubernetes

Kubernetes is a system that handles multiple containers. In a project with many containers, it is hard to make them work
together efficiently, and so that they can be scalable. Kubernetes helps with 
orchestrating the various parts so they work as a whole, and the application
can easily scale up or down. On the Kubernetes website the most important 
benefits for using Kubernetes are listed as: service discovery and load balancing, 
storage orchestration, automated rollouts and rollbacks, automatic bin packing, 
self-healing, and secret and configuration management. Kubernetes can be used for 
canary deployment, or more generally to help ensure that when in a production environment, if one container
fails, another container will go up.      

Kubernetes is most useful in an environment with more than a few host machines
that also have several containers. In smaller environments it might not be necessary or reasonable to use. 
Kubernetes can also launch an application in any environment, which is useful in the modern 
era with the popularity of cloud services. The Kubernetes service is described in the
Wikipedia as a set of pods that together constitute a service. For example the backend
can consist of its own set of pods that are joined to the frontend pods. Similarly to Docker,
you can use volumes in Docker for storage. 
