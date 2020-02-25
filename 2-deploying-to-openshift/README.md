
# Deploying Java Microservices to OpenShift on IBM Cloud

This workshop demonstrates how to build a microservice with Java and how to deploy it to OpenShift on the IBM Cloud.

The microservice is kept as simple as possible, so that it can be used as a starting point for other microservices. The microservice has been developed with Java EE and [Eclipse MicroProfile](https://microprofile.io/).

There are [various ways to deploy applications to OpenShift](http://heidloff.net/article/deploying-open-liberty-microservices-openshift/). The options have different advantages and disadvantages which are explained in the following labs.

## Labs

1. Deploying to OpenShift via 'oc' CLI: [lab](documentation/4-openshift.md) and [video (14:32 mins)](https://youtu.be/4MDfalo2Fg0)
2. Deploying existing images to OpenShift: [lab](documentation/5-existing-image.md) and [video (7:09 mins)](https://youtu.be/JhxsS7l6DhA)
3. Deployments of code in GitHub repos: [lab](documentation/6-github.md) and [video (3:52 mins)](https://youtu.be/b3upMuZOpsY)
4. Source to Image deployments: [lab](documentation/7-source-to-image.md) and [video (7:06 mins)](https://youtu.be/p6lVc6MDrcM)
5. Distributed logging with LogDNA and OpenShift on IBM Cloud: [lab](documentation/8-logdna-openshift.md)

The first four labs explain four different ways to deploy applications to OpenShift with their pros and cons in this specific scenario:

| Option | Dockerfile | yaml Files | Java Build | Docker Build |
| - | - | - | - | - |
| Lab 1: Kubernetes-like | required | required | OpenShift | OpenShift |
| Lab 2: Existing Image  | not required  | not required | N/A | N/A |
| Lab 3: Git Repo | required  | not required | OpenShift | OpenShift |
| Lab 4: Source to Image | not required | not required | Desktop | OpenShift |

The last lab shows how to create a LogDNA logging service on IBM Cloud and connect it with OpenShift to collect distributed logs.
