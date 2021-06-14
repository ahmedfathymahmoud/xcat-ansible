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
| `Xcat_groups` |  group defination (name, arch)|
| `osimages_paths`  |  list of ISO images paths |
| `site`  | site paramters (dns forwarders, gateway) |
|`system_user`| the system user and password on the compute nodes (user,password)|

Example Playbook
----------------

  - hosts: mangement
    remote_user: root
    gather_facts: yes 
    roles:
      - role: xcat-provision
        vars:
          Xcat_nodes:
          - name: "cn1"
            ip: 10.10.10.20
            mac: "08:00:27:03:15:9D"
            netboot: "pxe"
            arch: "x86_64"
            groups: "all,group1"
            os: centos8
            mode: install
            postscripts: testy


          - name: "cn2"
            ip: 10.10.10.40
            mac: "08:00:27:1C:05:40"
            netboot: "pxe"
            arch: "x86_64"
            groups: "all,group2"
            os: centos7
            mode: netboot 
          
        Xcat_groups:
          - name: "group1"
            arch: "x86_64"

          - name: "group2"
            arch: "x86_64"

        osimages_paths: 
          - "/opt/CentOS-7-x86_64-Minimal-2003.iso"
          - "/opt/CentOS-8.2.2004-x86_64-minimal.iso"

        site:
          forwarders: 8.8.8.8,8.8.4.4
          gateway: 10.10.10.1


        system_user:
          user: root
          passwd: $1$BJ1kwyBR$cCKQmlq1reH9u./loc4IK0



