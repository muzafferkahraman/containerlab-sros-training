<h1>Container Lab Setup for SROS</h1>

This is to setup the lab environment for SROS, using the containerlab, as below
![](schemanew.JPG)


To install containerlab (CentOS 7)
> yum-config-manager --add-repo=https://yum.fury.io/netdevops/ && echo "gpgcheck=0" | 
> sudo tee -a /etc/yum.repos.d/yum.fury.io_netdevops_.repo <br>
>
> yum install containerlab

To setup the training lab environment
> cd / <br>
> git clone https://github.com/muzafferkahraman/sros-training-lab <br>
> cd sros-training-lab <br>
> clab dep -t sros.yml --reconfigure <br>

After the script runs sucessfully, a  <b>clab inspect --all </b> check should return an ouput like below
![](containers.JPG)

Now you must be able to ping hosts from each other <br>

from Client1: 
>ping 10.0.0.27

from Client2: 
>ping 10.0.0.25


You can connect to host nodes (ie host-11) 
> docker exec -ti clab-dc-client1 bash

You can connect to SROS nodes (ie leaf1) 
> ssh admin@172.22.22.101

Note: You should acquire a valid SROS license and copy at the folder with the name of sros-license

Thanks 








