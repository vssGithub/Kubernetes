# Kubernetes
### Planes
Kubernetes architecture, at a high-level can be thought of as a Master Node (or Control Plane) and Worker Nodes.

<!-- ![](img/01.png) -->

<div align="center">
	<img src="img/01.png">
</div>

#
### Components
Some of the components that make up the Master Node and the Worker Node are visualized below.
<p align="center">
	<img src="img/02.png">
</p>

<p align="center">
	<img src="img/03.png">
</p>

#
### High-Level Architecture
The architecture between Master and Worker Nodes can be visualized as follows

![](img/04.png)

#
The Worker Node contains, at the lowest level, an app running in a container.
This pulls in the docker image.
In kubernetes, the smallest unit/component is a pod...so this container is wrapped within a pod.
And that pod runs on a node.

<!-- ![](img/05.png) -->

<div align="center">
	<img src="img/05.png">
</div>

#
### Internal Comms

The API server exposes a ReST api.
Commands sent (eg. kubectl get pods) are sent to via a request

<div align="center">
	<img src="img/06.png">
</div>

<br/>

The communications between components is visualized in the following diagram

<div align="center">
	<img src="img/07.png">
</div>

#
## Configs
Kubernetes consumes the config files in order to create the objects required.
As an example, let's consider a simple pod.  
[Pods](https://kubernetes.io/docs/concepts/workloads/pods/) are the smallest deployable units of computing that you can create and manage in Kubernetes.  
We can create this pod via the imperative method, or the declarative method. For just now, let us ignore these definitions.  
We shall re-visit this shortly.
Let's 
1. create a pod config/file, 
2. apply this, 
3. Interrogate and see this in Kubernetes

<br/>

### Creating a sample Pod Config
Create a file, with the yaml extension (as below).  
<div align="center">
	<img src="img/08a.png">
</div>

<br/>

This file is blank (for now; below).  
Now, we create the config.  
<div align="center">
	<img src="img/08b.png">
</div>

<br/>

In the newly created blank yaml file, start typing out <strong>pod</strong>.  
VS Code intellisense kicks in and gives us the option to apply a Kubernetes pod template.  
<div align="center">
	<img src="img/08c.png">
</div>

<br/>

Click on the option for pod and we see as follows  
<div align="left
">
	<img src="img/08d.png">
</div>

<br/>

Now, we'll edit this file to create a barebones sample pod.  
We'll just rename the spec name to nginx and the image to pull the latest nginx image.  
<div align="left">
	<img src="img/08e.png">
</div>

### Applying the sample Pod Config
Ok. We have the config. Now what?  
In order to see this in action, we need to apply this in Kubernetes.  
Ensure that Kubernetes is running (I have docker-desktop installed, and started).  
As can be seen, there's no pods running.

<div align="left">
	<img src="img/09a.png">
</div>

<br/>

<div align="left">
	<img width="500" height="280" src="img/09b.png">
</div>

<br/>

We apply the config using the command
  - kubectl apply -f <filename>
    eg. kubectl apply -f samplePod.yaml  

And querying the pods, we see as follows.  

<br/>

<div align="left">
	<img src="img/09c.png">
</div>

<br/>

Let's apply port-fowarding so that we can reach the pod.
We can do this via the command
  - kubectl port-forward localport:remoteport
    eg. kubectl port-forward 1122:80  

<br/>

<div align="left">
	<img src="img/09d.png">
</div>

<br/>

Navigating in the browser, we see as follows.

<div align="left">
	<img width="500" height="250" src="img/09e.png">
</div>

<br/>



#
## Links
[Kubernetes Internals](https://github.com/shubheksha/kubernetes-internals)
