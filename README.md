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
## Links
[Kubernetes Internals](https://github.com/shubheksha/kubernetes-internals)
