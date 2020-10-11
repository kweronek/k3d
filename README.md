# k3d : Launch a K3D-CLuster on Ubuntu
The script gives you an easy possibility to create a Kubernetes Cluster based on K3S/K3D on Ubuntu.
The files also gives a demo of useful commands to manage the cluster.

## Prerequisites
As hardware you may use your PC or an apropriate AWS-instance (or other cloud services like Azure or GoogleCloud)
### Using AWS (optional)
You should have a key-pair before continueing.  
Create an EC2-instances (c5.large recommended).  
Make sure your security allows any2any traffic (this must be changed in production).  
Connect to your server using ssh. (AWS will provide you with a predefined string..

### Prepare machine
(Assuming git is installed)
`git clone https://github.com/kweronek/k3d`
`./prepare` 
That's all!

## Launch Cluster
To launch a cluster you need to define 3 parameters:
* the name of your cluster,
*  the number of worker nodes,
*  the nuberr of master nodes

Then launch you cluster like this:  

`launchK3sCluster <name> <#worker> <#master>`
`launchK3sCluster test 3 1`

## Hints to manage your Cluster
K3D comes with a help function (just typ `k3d`). This will not be repeated here. However most useful commands are:
```
* k3d cluster list/start/stop/delete
* k3d node list/start/stop/create/delete 
```

The K8S-CLI `kubectl` also has a help function (just type `kubectl`). Most useful command are:
```
* kubectl cluster-info
* kubectl get nodes
* kubectl get pods --all-namespaces
* kubectl get deployments --all-namespaces
```
Thees are used in the script `launchK3SCluster` as an example.




## Explanation

