# Prometheus and Grafana on kubernetes
Any kind of dynamic provisioning can be used for storing prometheus and grafana data.
## NFS Setup for dynamic provisioning
Setup NFS mount on a server which can be dynamically provisioned through Storage Class.
```
yum install git wget -y
git clone https://github.com/aruntony005/nfs-setup.git

CLIENT_IP='all'
NFS_DIR='/mnt/nfs'
systemctl stop firewalld
sh nfs-setup/nfs-server.sh $CLIENT_IP $NFS_DIR
```
Here all client IPs are allowed to provision nfs volumes. It can be restricted by providing the kubernetes node IP as CLIENT_IP.

## Prometheus Setup

