# Launch a K3D-CLuster
The script gives you an easy possibility to create a Kubernetes Cluster based on K3S/K3D on Ubuntu.
The files also gives a demo of useful commands to manage the cluster.

## Prerequisites
As hardware you may use your PC or an apropriate AWS-instance (or other cloud services like Azure or GoogleCloud)

### Harware
The minimum hardware requirements depend on the number of masters, the number of the nodes and the size of the business software.
With one master node and one worker node and a tiny software to run, you need 1 core and 1GB RAM at least.
Recommended are at least 2 cores with 4GB RAM for 1 master and 3 worker. For test purposes this will fit for 3 master and 3 workers. In the latter case there is almost no RAM left for applications.
As a thumb rule you shold plan 600MB for a master and 300MB for worker nodes

#### Using AWS (optional)
You should have a key-pair before continueing.  
Create an EC2-instances (minumum t2.micro for 1 master/1 node, c5.large recommended for 1 master/1 node).  
Make sure your security groups allows any2any traffic (this must be changed in production).  
Connect to your server using ssh. (AWS will provide you with a predefined string).

### Software
#### openSUSE 15.2/SLES 15.2
SLES 15.2 is a base linux distribution therefor we need some software installation before launching the cluster.  
Open a terminal and type:
```
sudo -s 
wget https://raw.githubusercontent.com/kweronek/k3d/master/prepare-SLES
chmod 754 prepare-SLES  
export PATH=$PATH:.   
prepare-SLES  
```

#### Ubuntu 20.04
On Ubuntu 20.04 git is already pre-installed. Open a terminal and type:  
```
sudo -s
git clone https://github.com/kweronek/k3d  
export PATH=$PATH:.    
cd k3d  
prepare-Ubuntu  
```
That's all!

## Launch Cluster
To launch a cluster you need to define 3 parameters:
* the name of your cluster,
* the number of worker nodes and
* the number of master nodes.

Then launch you cluster (needs sudo) like this:  
`launchK3sCluster <name> <#worker> <#master>`  
Example: `launchK3sCluster myCluster 3 1`

## Hints to manage your Cluster
K3D comes with a help function (just typ `k3d`). This will not be repeated here. However most useful commands are:
```
k3d cluster list/start/stop/delete  
k3d node list/start/stop/create/delete 
```

The K8S-CLI `kubectl` also has a help function (just type `kubectl`). Most useful commands are:
```
kubectl cluster-info  
kubectl get nodes  
kubectl get pods --all-namespaces  
kubectl get deployments --all-namespaces  
```
These are used in the script `launchK3SCluster` as an example.

## Explanation

