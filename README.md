Kafka_Cluster_Ansible_Role
=========

A role to build and configure a 3-broker Kafka cluster.

Requirements
------------
- 3 Ubuntu EC2 Instances

Role Variables
--------------

```
kafka_download_url: <Kafka_Download_URL>
kafka_download_location: /home/<USER_USED>/kafka_2.13-3.1.0.tgz
kafka_extraction_location: /home/<USER_USED/

nodes:
- <node1_hostname> # ansible_nodename
- <node2_hostname>
- <node3_hostname>

blocks:
- | 
  initLimit=5
  syncLimit=2
  tickTime=2000
  # list of servers
  server.1=0.0.0.0:2888:3888
  server.2=<private_ip of second server>:2888:3888
  server.3=<private_ip of third server>:2888:3888

- | 
  initLimit=5
  syncLimit=2
  tickTime=2000
  # list of servers
  server.1=<private_ip of first server>:2888:3888
  server.2=0.0.0.0:2888:3888
  server.3=<private_ip of third server>:2888:3888

- |
  initLimit=5
  syncLimit=2
  tickTime=2000
  # list of servers
  server.1=<private_ip of first server>:2888:3888
  server.2=<private_ip of second server>:2888:3888
  server.3=0.0.0.0:2888:3888

ips:
- <node1_private_ip>
- <node2_private_ip>
- <node3_private_ip>


```

Example Playbook
----------------


    - name: running the role
      hosts: kafka
      roles:
      - kafka-cluster

License
-------

BSD

Author Information
------------------

<a href="https://www.linkedin.com/in/zainabsabry/">
<img src="https://www.vectorlogo.zone/logos/linkedin/linkedin-icon.svg
" alt="architecture" width="30" height="30" />
</a>


