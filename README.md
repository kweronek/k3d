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
git clone https://github.com/kweronek/k3d
./prepare
That's all!

## Launch Cluster
To launch a cluster you need to define 3 parameters:
  the name of your cluster,
  the number of worker nodes,
  the nuberr of master nodes

Then launch you cluster like this:  

launchK3sCluster <name> <#worker> <#master>
laucnhK3sCluster test 3 1

## Explanation

