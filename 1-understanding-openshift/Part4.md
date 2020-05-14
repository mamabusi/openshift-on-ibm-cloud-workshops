## Claiming Your Red Hat OpenShift Cluster for This Workshop

### Step1:
For the purpose of this workshop organizers pre-provisioned for attendees free Red Hat OpenShift Clusters. Thanks to that you can try and learn on how to use them.
Use the following URL: https://osbangalore.mybluemix.net to claim the clusters.

OS Lab Key: oslab

![OS_claimcluster](images/os_claimcluster.png)

### Step2:
Enter the Lab Key given by your instructor, as well as the email address associated with your IBM Cloud account.
After you hit submit, you will be given a cluster for the duration of the workshop.
You should be given the result page showing the successful assignment.

![OS_clusteraccess](images/os_clustersuccess.png)

Click on Login to IBM Cloud account to view the cluster.

### Step3:
Upon login you should be able to view the cluster as below:
![OS_clusterhome](images/os_clusterhome.png)

## Access the OpenShift Webconsole

### Step1:
Click on the cluster.
![OS_clusterinfo](images/os_clusterinfo.png)

### Step2:
Click on 'OpenShift web console' button.
Verify that pop-ups are enabled on the browser for this site.

![OS_openconsole](images/os_webconsole.png)

## Access the Command Line Interface

### Step1:
Use the following url to open the Cloud shell:  https://shell.cloud.ibm.com/
![OS_cloudshell](images/os_cloudshell.png)

### Step2:
To login to connect to your OpenShift cluster,

(i) Click on your account button displayed on the top right corner. From the dropdown, click on 'Copy Login Command'
![OS_copylogin](images/os_copylogin.png)

(ii) A new browser window is opened. Click on 'Display Token' to view the account details.
![OS_displaytoken](images/os_diplaytoken.png)

(iii) You should be able to view the login details. Copy the login command under the section: "Login with this token"
![OS_copytoken](images/os_copytoken.png)

(iv) Paste it in the opened cloud shell command prompt and click 'Enter'
![OS_cslogin](images/os_cslogin.png)

You should now be able to login successfully to your cluster.



## Deploy an application on OpenShift on the IBM Cloud

The above setup of the OpenShift cluster must be completed to be able to run through this workshop. 

This workshop is divided in two sections:

  A. Working with the OpenShift Web Console 
  
  B. Working with the `oc`command line tool


### A. Deploy an application from the Web Console
Go to the OpenShift Web Console page.
![OS_Webconsole](images/os_webconsole.png)

1. In the OpenShift Web Console, click "+Add" in the options available on the left.
![OS_AddProject](images/os_addproject.png)

2. Click on "create a project" and in the pop-up page, give your project a name, e.g. "myfirstproject". Click "Create".

![OS_CreateProject](images/os_createproject.png)
![OS_ProjectDetails](images/os_projectdetails.png)

2. You see that it is displaying the content of your project but currently it has no workloads. It offers a bunch of options to create in your project. 

![OS Project Overview](images/os_project_overview.png)

3. Click on "Container Image". We will be deploying an existing image from an image registry.

![OS Deploy_image](images/os_selectcontainerimage.png)

4. Select "Image Name" and enter `openshiftkatacoda/blog-django-py` as name, then click on the "magnifying glass". 

![OS Deploy 1](images/os_deploy_1.png)

5. OpenShift reads details from the image and displays them. It fills in a name, based on the image name, and a label "app" whose content is also based on the image name. 

![OS Deploy 2](images/os_deploy_2.png)

6. Leave the defaults and click "Create". 

![OS Deploy 3](images/os_deploy_3.png)

7. You should see that the pod is being deployed.

![OS_Deployed](images/os_deployingpod.png)


8. Click on the "Open URL" option to view the deployed application on the browser. 

![OS_PodOpenURL](images/os_pod_openurl.png)

9. Click on "List view" to see the pod overview and resources. 

![OS_Pod_ListView](images/os_pod_listview.png)
![OS_Pod_OverView](images/os_pod_overview.png)
![OS_Pod_Resources](images/os_pod_resources.png)

10. You can scale the number of pods and reduce them as well in the "Overview" page. 

![OS_Pod_Scale](images/os_pod_scaling.png)
![OS_Pod_Scale](images/os_pod_scaled.png)


### B. Deploy an application with `oc` from the command line 

The OpenShift `oc` command line tool includes all the functionality of the Kubernetes native `kubectl` CLI but it has also all the function required for OpenShift specifics, e.g. a `login` command to access the OpenShift cluster.

### Install the OpenShift `oc` CLI

Go back to the IBM Cloud Dashboard and display your OpenShift cluster. If you closed the IBM Cloud Dashboard you can find OpenShift clusters [here](https://cloud.ibm.com/kubernetes/clusters?platformType=openshift).

In the "Access" section of your cluster is detailed information about installing the `oc`CLI and and the different methods to get access to your cluster.

![OS Access](images/os_access.png)

### Login to the OpenShift Cluster

Once `oc` is installed, copy the login command from the OpenShift Web Console and paste it into a command window (shell). It will look similar to this:

```
$ oc login https://c100-e.us-south.containers.cloud.ibm.com:30*** --token=z5cuqxABC-9QdqE1ivXYZ1z_Y6Tghj1qxN-abCWc1Bg
```

If login is successfull you will see all the projects on OpenShift that you have access to. 

Keep the command line open but go back to the OpenShift Web Console.

### Working with the `oc` CLI


1. Go back to your command line where you used `oc`to logon to your OpenShift cluster.

2. Switch to the project you created in the Web Console with:

```
$ oc project blog

Now using project "blog" on server "https://c100-e.us-south.containers.cloud.ibm.com:30***".
```

3. Display all objects that belong to your project:

```
$ oc get all -o name

pod/blog-django-py-1-qk7d9
replicationcontroller/blog-django-py-1
service/blog-django-py
deploymentconfig.apps.openshift.io/blog-django-py
imagestream.image.openshift.io/blog-django-py
route.route.openshift.io/blog-django-py
```

4. Display all objects that are labeled with your app name, the list should be the same as before:

```
$ oc get all -l app=blog-django-py -o name

pod/blog-django-py-1-qk7d9
replicationcontroller/blog-django-py-1
service/blog-django-py
deploymentconfig.apps.openshift.io/blog-django-py
imagestream.image.openshift.io/blog-django-py
route.route.openshift.io/blog-django-py
```

5. Delete them with:

```
$ oc delete all -l app=blog-django-py -o name

pod/blog-django-py-1-qk7d9
replicationcontroller/blog-django-py-1
service/blog-django-py
deploymentconfig.apps.openshift.io/blog-django-py
imagestream.image.openshift.io/blog-django-py
route.route.openshift.io/blog-django-py
```

   If you go back to the Web Console you should see that it updated the Overview which now should be empty again.

### Deploy an application from the command line

1. Check if the image is available:

```
$ oc new-app --search openshiftkatacoda/blog-django-py

Docker images (oc new-app --docker-image=<docker-image> [--code=<source>])
-----
openshiftkatacoda/blog-django-py
  Registry: Docker Hub
  Tags:     latest

```

2. Deploy the image as an application:

```
$ oc new-app openshiftkatacoda/blog-django-py

--> Found Docker image 927f823 (2 months old) from Docker Hub for "openshiftkatacoda/blog-django-py"

    Python 3.5 
    ---------- 
    Python 3.5 available as container is a base platform for building and running various Python 3.5 applications and frameworks. Python is an easy to learn, powerful programming language. It has efficient high-level data structures and a simple but effective approach to object-oriented programming. Python's elegant syntax and dynamic typing, together with its interpreted nature, make it an ideal language for scripting and rapid application development in many areas on most platforms.

    Tags: builder, python, python35, python-35, rh-python35

    * An image stream tag will be created as "blog-django-py:latest" that will track this image
    * This image will be deployed in deployment config "blog-django-py"
    * Port 8080/tcp will be load balanced by service "blog-django-py"
      * Other containers can access this service through the hostname "blog-django-py"

--> Creating resources ...
    imagestream.image.openshift.io "blog-django-py" created
    deploymentconfig.apps.openshift.io "blog-django-py" created
    service "blog-django-py" created
--> Success
    Application is not exposed. You can expose services to the outside world by executing one or more of the commands below:
     'oc expose svc/blog-django-py' 
    Run 'oc status' to view your app.
```

3. Check the status of your deployment:

```
$ oc status --suggest

In project blog on server https://c100-e.us-south.containers.cloud.ibm.com:30634

svc/blog-django-py - 172.21.51.187:8080
  dc/blog-django-py deploys istag/blog-django-py:latest 
    deployment #1 deployed 56 seconds ago - 1 pod

Info:
  * dc/blog-django-py has no readiness probe to verify pods are ready to accept traffic or ensure deployment is successful.
    try: oc set probe dc/blog-django-py --readiness ...
  * dc/blog-django-py has no liveness probe to verify pods are still running.
    try: oc set probe dc/blog-django-py --liveness ...

```

The --suggest options even gives you infos on things that are missing in your configuration.

4. Your application needs a Route to expose it externally:

```
$ oc expose service/blog-django-py

route.route.openshift.io/blog-django-py exposed
```

5. Display the URL of the Route:

```
$ oc get route/blog-django-py

NAME             HOST/PORT                                                                                                               PATH      SERVICES         PORT       TERMINATION   WILDCARD
blog-django-py   blog-django-py-blog.harald-uebele-openshift-5290c8c8e5797924dc1ad5d1bcdb37c0-0001.us-south.containers.appdomain.cloud             blog-django-py   8080-tcp                 None
```

You can see the very long URL. If you want, copy it and open it in your browser.

6. Cleanup. This deletes everything including your project!
   This command takes a while to complete.

```
$ oc delete project blog

project.project.openshift.io "blog" deleted
```
You can also delete a complete project from the Web Console.

---


Congratulations! You have completed this workshop!  



__Continue with the second workshop__ in this series: "[Deploying Java Microservices to OpenShift on IBM Cloud](https://github.com/nheidloff/openshift-on-ibm-cloud-workshops/tree/master/2-deploying-to-openshift#deploying-java-microservices-to-openshift-on-ibm-cloud)".


__Back to the [overview](https://github.com/nheidloff/openshift-on-ibm-cloud-workshops#openshift-on-ibm-cloud-workshops)__
