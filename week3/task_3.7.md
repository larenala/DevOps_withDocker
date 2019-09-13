# Short introduction to why and when to use Kubernetes

Kubernetes is a system that handles multiple containers. It can help you to
make sure that if, in a production environment, one container fails, another
will go up. In a project with many containers, it is hard to make them work
together efficiently, and so that they can be scalable. Kubernetes helps with 
orchestrating the various parts so they work as a whole, and the application
can easily scale up or down. On the Kubernetes website the most important 
benefits for using Kubernetes are listed as: service discovery and load balancing, 
storage orchestration, automated rollouts and rollbacks, automatic bin packing, 
self-healing, and secret and configuration management.      

Kubernetes is most useful in an environment with more than a few host machines
that also have several containers. Kubernetes can be used for a canary deployment. Kubernetes
can also launch an application in any environment, which is useful in the modern 
era with the popularity of cloud services.
