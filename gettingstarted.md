---
layout: page
title:  "Getting started with Bigtop"
permalink: /getting-started/
---
To start a single node cluster using Ambari 2.7.5 in docker (Bigtop 3.2.0), execute the following commands:

```
git clone https://github.com/apache/bigtop
cd bigtop/provisioner/bigtop-stack-provisioner/docker/centos7
./build-image.sh
./clear-containers.sh
./build-containers.sh
```

```
-FROM centos:7
+FROM rockylinux:8
```


```
docker run -d -p 3306:3306 -p 5005:5005 -p 8080:8080 --name ambari-server --hostname ambari-server --network ambari --privileged -e "container=docker" -v /sys/fs/cgroup:/sys/fs/cgroup:rw --cgroupns=host ambari:2.7.5 /usr/sbin/init
```


