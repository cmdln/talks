# Reproducible Builds for Secure, Reliable Containers

* http://gist-reveal.it/623376518b1d7a941f87
* OpenShift provides developer convenience on top of other tools, in particular Kubernetes
  * K8s provides object model, or primitives, for automation
  * OpenShift adds a few more object types
* Each object has a yaml or json representation
  * Can be posted to a K8s end point
  * Will then be automated in some way
* Pod - set of containers that are a unit of deployment, scale
  * If any container in a pod fails, who pod is torn down and re-built
  * For instance, app server, database, logging agent
* ReplicationController - works to automated from actual status to desired scale of workloads
* Notary - docker content trust, image signing and validating
  * https://blog.docker.com/2015/08/content-trust-docker-1-8/
  * openshift has an integrated docker registry
* Question: can this easily use AWS ECS/ELB?
  * If so, could make managing multiple micro-services easier
  * How does openshift/K8s interact with docker-compose and docker-machine?
* openshift supports webhooks, both generic and for github
