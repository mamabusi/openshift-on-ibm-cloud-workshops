
# OpenShift on IBM Cloud Workshops

![logo](images/os_logo.png)

[Red Hat OpenShift on IBM Cloud](https://cloud.ibm.com/docs/openshift?topic=openshift-why_openshift) is an extension of the IBM Cloud Kubernetes Service, where IBM manages OpenShift Container Platform for you. 

With Red Hat OpenShift on IBM Cloud developers have a fast and secure way to containerize and deploy enterprise workloads in Kubernetes clusters. OpenShift clusters build on Kubernetes container orchestration that offers consistency and flexibility for your development lifecycle operations.

This repository holds a series of workshops that help you as a developer to become familiar with Red Hat OpenShift, how it can be deployed on the IBM Cloud, and how to deploy applications on and with OpenShift.

In order to run these workshops, you need an [IBM Cloud account](https://cloud.ibm.com/registration).

## Workshop: [Deploying Java Microservices to OpenShift on IBM Cloud](https://github.com/nheidloff/openshift-on-ibm-cloud-workshops/tree/master/2-deploying-to-openshift#deploying-java-microservices-to-openshift-on-ibm-cloud)

This workshop demonstrates how to build a microservice with Java and how to deploy it to OpenShift on the IBM Cloud.

The microservice is kept as simple as possible, so that it can be used as a starting point for other microservices. The microservice has been developed with Java EE and Eclipse MicroProfile.

<kbd><img src="images/workshop-2.png" /></kbd>

**Labs**

0. [Overview video (1:41 mins)](https://youtu.be/8361HGR_O_s)
1. Installing prerequisites: [lab](2-deploying-to-openshift/documentation/1-prereqs.md) and [video (2:58 mins)](https://youtu.be/c5CtqijWXL4) and the [video including windows (4:11 mins)](https://youtu.be/53XccO3NNn8)
2. Running the Java microservice locally: [lab](2-deploying-to-openshift/documentation/2-docker.md) and [video (3:51 mins)](https://youtu.be/4dT2jg6wGF4)
3. Understanding the Java implementation: [lab](2-deploying-to-openshift/documentation/3-java.md) and [video (9:09 mins)](https://www.youtube.com/watch?v=ugpYSPV9jAs)
4. Deploying to OpenShift via 'oc' CLI: [lab](2-deploying-to-openshift/documentation/4-openshift.md) and [video (14:32 mins)](https://youtu.be/4MDfalo2Fg0)
5. Deploying existing images to OpenShift: [lab](2-deploying-to-openshift/documentation/5-existing-image.md) and [video (7:09 mins)](https://youtu.be/JhxsS7l6DhA)
6. Deployments of code in GitHub repos: [lab](2-deploying-to-openshift/documentation/6-github.md) and [video (3:52 mins)](https://youtu.be/b3upMuZOpsY)
7. Source to Image deployments: [lab](2-deploying-to-openshift/documentation/7-source-to-image.md) and [video (7:06 mins)](https://youtu.be/p6lVc6MDrcM)

---

## Resources and next Steps

* There are many good tutorials on the Red Hat OpenShift [Interactive Learning Portal](https://learn.openshift.com/).

* The IBM Developer Website has its own section on [Red Hat OpenShift on IBM Cloud](https://developer.ibm.com/components/redhat-openshift-ibm-cloud/).

* Our [Cloud Native Starter](https://github.com/IBM/cloud-native-starter) project on GitHub has a section on [how to deploy on OpenShift](https://github.com/IBM/cloud-native-starter/blob/master/documentation/OpenShiftIKSDeployment.md#deploy-cloud-native-starter-on-openshift-on-ibm-cloud).

* Check this IBM Cloud solution tutorial: [Scalable web application on OpenShift](https://cloud.ibm.com/docs/tutorials?topic=solution-tutorials-scalable-webapp-openshift).

