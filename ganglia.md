# GANGLIA INSTALLATION
### ***ON MASTER-SERVER***
-> Install the ganglia packages 
```
yum install ohpc-ganglia
```
-> Go to  ```/etc/ganglia/gmetad.conf ```file & edit this file as   
```
On line 44 Give your cluster_name as you want:
(for e.g - Ganglia Cluster) 
& keep rest of the settings default 
```
-> Now go to ```/etc/ganglia/gmond.conf``` file & edit this file as 
```
On line 30 give the Cluster_name as you given in "gmetad.conf" file (for e.g - Ganglia Cluster)

On line 50 Enter the Master_server IP instead of default IP

Comment the line 57 (mcast_join) & line 59 (bind)
```
-> Start the Ganglia services as 
```
systemctl start gmetad
systemctl status gmetad

systemctl start gmond
systemctl status gmond

systemctl start httpd
systemctl status httpd
```

### ***ON CLIENT-SERVER***
-> Install the Ganglia packages 
```
yum install ganglia-gmond-ohpc
```
-> Now go to ```/etc/ganglia/gmond.conf``` file & edit this file as 
```
On line 30 give the Cluster_name as you given in "gmetad.conf" file of master-server
 (for e.g - Ganglia Cluster)

On line 50 Enter the Master_server IP instead of default IP

Comment the line 57 (mcast_join) & line 59 (bind)
```
-> Start the Ganglia services as 
```
systemctl start gmond
systemctl status gmond
```