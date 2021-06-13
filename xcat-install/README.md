xCat Installation
=========


Role to install and configure xcat on mangement node.

---------------------------------------------------------------------
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
| `network` | network paramters (ip, dns, ifname, connection name, gateway)      | The internet hostname of this mail systems |
| `hostname` |  hostname of mangement node |
| `xcat_core`  |  xCAT’s main software package (baseurl, gpgkey) |
| `xcat_dep`  | xCAT’s dependency package (baseurl, gpgkey) |

-------------------------------------
### vars

| Variable   | Comments  |
| :---        | :---             |
| `ports` | xCAT port usage list as described in docs https://xcat-docs.readthedocs.io/en/latest/advanced/ports/xcat_ports.html?highlight=ports |


