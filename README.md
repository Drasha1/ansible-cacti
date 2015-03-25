Cacti
====================
Overview
-------------------------
this is a basic cacti server that graphs cpu, memory, load average, and eth trafficthis is a basic cacti server that graphs cpu, memory, load average, and eth trafficthis is a basic cacti server that graphs cpu, memory, load average, and eth trafficthis is a basic cacti server that graphs cpu, memory, load average, and eth traffic. snmp3 is used to get data from the server. This role can be run on any servers you want to monitor and you specify the cacti server with the cacti group and run this role on it for setup

Requirements
---------------------
- server in the cacti group in your ansible_hosts file
- snmp3 must be configured on the server you are monitoring. I have a snmp repo that will do this for you if you need it
- mysql or mardiadb for storage
- a my.cnf file in /root so auto login is possible
- epel repos

Ansible Variables
-----------------------
- mysql_cacti_password=password  || has to be set for the cacti server
- htaccessuser=cacti             || user for login to cacti only needed on cacti server
- htaccesspass=password          || password for login to cacti only needed on cacti server
- snmp3user=snmpuse              || needed for servers being graphedr
- snmp3password=snmppass         || needed for servers being graphed

Files
-------------------------
- /usr/share/cacti/               || web directory
- /usr/share/cacti/cli            || cli scripts
- /var/log/cacti/cacti.log        || cacti error log

Ports
--------------------------
- outgoing udp on port 23
- outgoing snmp tcp on port 161
- in coming tcp to snmpd on port 199
- in/out tcp to httpd on port 80
- in/out tcp to mysql on port 3306
