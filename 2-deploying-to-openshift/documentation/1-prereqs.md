### Access to the IBM Cloud

An IBM Cloud account is needed. [Register](http://bit.ly/OSworkshop2) if you do not have one.

### Access to the OpenShift cluster

We will use the pre-provisioned Openshift cluster on IBM Cloud in this hands-on workshop.

[Login](https://oswtbain.mybluemix.net) with your registered email id used for IBM Cloud account and enter lab key as: **oslab**

![Key](images/os-login.png)
  
Login to IBM Cloud and access the cluster

![Key](images/os-cloudLogin.png)
  
  
Click on the cluster:
![Key](images/os-clusterView.png)
  
 
Open the **OpenShift web console**
![Key](images/os-viewWebconsole.png)


This is the OpenShift Web Console
![Key](images/os-consoleHomepage.png)

### Get our access token for the 'oc' CLI. 

From the dropdown menu in the upper right of the console page, click 'Copy Login Command'. 
![Key](images/os-consHomePageToken.png)




### Access the Cloud shell (command prompt)
1. You will need the [Cloud shell](https://shell.cloud.ibm.com/) to connect to the OpenShift cluster via command prompt.

Paste the copied access token command into your terminal.

2. Verify 'oc' CLI

```
$ oc login https://c100-e.eu-de.containers.cloud.ibm.com:32177 --token=xxxxxx'
$ oc projects
```

3. Verify 'kubectl' CLI

```
$ kubectl get pods
```
---

Go back to lab 1. Build and Save the container image' in ['Step 1'](./4-openshift.md#step-1-create-an-open-shift-project)

