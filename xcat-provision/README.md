xCAT Provision
=========

Role that run on mangement node to define multiple compute nodes, groups and osimages 


Requirements
------------

Supported operating systems:

Redhat >= 7.0


-------------------------------------------------------
Role Variables
--------------

### defaults


| Variable   | Comments  |
| :---        | :---             |
| `Xcat_nodes` | compute node paramters (name, ip, mac, arch ,netboot method, os: os name,mode: intstallation mode, postscript name (located in files folder) | 
|------------------------------|-----------------------------------|
| `Xcat_groups` |  group defination (name, arch)|
| `osimages_paths`  |  list of ISO images paths |
| `site`  | site paramters (dns forwarders, gateway) |
|`system_user`| the system user and password on the compute nodes (user,password)|

