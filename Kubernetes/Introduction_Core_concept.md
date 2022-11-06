Introduction
=============

![image](https://user-images.githubusercontent.com/53966749/200154391-74f0b1a1-9721-4fb4-ba4e-afff752f5c9b.png)
![image](https://user-images.githubusercontent.com/53966749/200154424-fb684a69-dfb6-4ba9-ba52-eb15e7e9b964.png)
![image](https://user-images.githubusercontent.com/53966749/200154511-df7dccc1-7ca5-470b-80f6-2f201dbc94ab.png)
![image](https://user-images.githubusercontent.com/53966749/200154592-f8557045-4f94-4ada-ba16-4368415ce254.png)
![image](https://user-images.githubusercontent.com/53966749/200154722-bf20ff59-2833-4fdd-b677-7b0387ff4f0a.png)
![image](https://user-images.githubusercontent.com/53966749/200154757-1138c9a4-6ee8-4a9c-aeb1-5075cbe1a4ac.png)

Kubectl
=========

![image](https://user-images.githubusercontent.com/53966749/200155214-eaca9892-59ed-4dfb-9781-4ef488202747.png)
![image](https://user-images.githubusercontent.com/53966749/200155242-634ff5f4-e7b4-4f4f-9d77-38ff38323fa7.png)

Docker vs Kubernetes
====================

![image](https://user-images.githubusercontent.com/53966749/200155364-8d09e5c1-2afa-4e0a-acfe-e60b69bd635a.png)
![image](https://user-images.githubusercontent.com/53966749/200155384-d5c1f995-efed-477e-9477-e931f7fb0e28.png)

```
sles15sp3:~ # kubectl run nginx --image=nginx
pod/nginx created
sles15sp3:~ #
sles15sp3:~ # kubectl get pods
NAME    READY   STATUS    RESTARTS   AGE
nginx   1/1     Running   0          7s
sles15sp3:~ # kubectl exec -it nginx -- bash
root@nginx:/# ls
bin  boot  dev  docker-entrypoint.d  docker-entrypoint.sh  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@nginx:/# exit
exit
sles15sp3:~ # kubectl exec -it nginx -- ls
bin   docker-entrypoint.d   home   media  proc  sbin  tmp
boot  docker-entrypoint.sh  lib    mnt    root  srv   usr
dev   etc                   lib64  opt    run   sys   var

sles15sp3:~ # docker run -it -d --name mywebserver nginx
625b68316ec75550f1c27cb096836e2f67d6d6ac8bab901b13f56769d24d48b3
sles15sp3:~ #
sles15sp3:~ # docker exec -it mywebserver bash
root@625b68316ec7:/# ls
bin  boot  dev  docker-entrypoint.d  docker-entrypoint.sh  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
root@625b68316ec7:/#
```

Pod
====
![image](https://user-images.githubusercontent.com/53966749/200155584-a0d00ae3-5146-4ad4-b877-2a1b5b616baa.png)
![image](https://user-images.githubusercontent.com/53966749/200155623-d65d1419-093b-4824-9f60-df9663287cf8.png)
![image](https://user-images.githubusercontent.com/53966749/200155637-15d4b33f-6ca4-42e7-b9f7-d08dcdea578d.png)
![image](https://user-images.githubusercontent.com/53966749/200155645-cf585510-f13b-4061-9f74-8eaa57ae33cd.png)



Kubernetes object
=================
![image](https://user-images.githubusercontent.com/53966749/200155772-3ed99e10-d09c-43fc-b488-22f5e5aa0360.png)
![image](https://user-images.githubusercontent.com/53966749/200155788-63712cd9-9b55-447f-9f51-d66d26a5d3ee.png)
![image](https://user-images.githubusercontent.com/53966749/200156052-055fd324-b304-4f36-b2e2-10bb66545064.png)
![image](https://user-images.githubusercontent.com/53966749/200156068-54f218d2-9286-4fca-97ea-09f71f1c9e9e.png)

```
sles15sp3:~ # cat 1.yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginxwebserver
spec:
  containers:
     -    image: nginx
          name: democontainer
          
          
sles15sp3:~ # kubectl apply -f 1.yaml
pod/nginxwebserver created

sles15sp3:~ # kubectl get pods
NAME             READY   STATUS    RESTARTS   AGE
nginx            1/1     Running   0          22m
nginxwebserver   1/1     Running   0          107s
sles15sp3:~ #

```

Kubernetes Architecture
========================
![image](https://user-images.githubusercontent.com/53966749/200156115-ff0537e5-6cdd-4967-b703-3df05b62af0e.png)
![image](https://user-images.githubusercontent.com/53966749/200156143-ee653fc3-41f9-4226-ab30-3d7c502f5e35.png)
![image](https://user-images.githubusercontent.com/53966749/200156163-83b9bf91-fed1-4226-9c0f-fd0b2ef36143.png)

etcd
=====
![image](https://user-images.githubusercontent.com/53966749/200156202-0afd2b8c-77b8-45d6-b9fb-948a9d601fd0.png)
![image](https://user-images.githubusercontent.com/53966749/200156219-25dd7689-60fa-4b18-a8c0-a9160944a577.png)
![image](https://user-images.githubusercontent.com/53966749/200156262-dfa2f702-a634-4d9f-a102-5f952cd30be9.png)
![image](https://user-images.githubusercontent.com/53966749/200156279-63337e0f-dfc0-4660-b13d-96acec090189.png)

kube-apiserver
==============

![image](https://user-images.githubusercontent.com/53966749/200156362-75e9b271-2450-4a32-8320-0d0af344f4a9.png)
![image](https://user-images.githubusercontent.com/53966749/200156377-85104850-c5c4-425e-8cc4-6ffafb3f8861.png)
![image](https://user-images.githubusercontent.com/53966749/200156390-31e1c1de-566f-426c-a2e1-56fb47a83647.png)

![image](https://user-images.githubusercontent.com/53966749/200156456-d0089fc8-e02e-45ef-86d8-e94a916f2d54.png)
![image](https://user-images.githubusercontent.com/53966749/200156472-8e5943e5-9a1c-41ad-8f89-e903a3b42111.png)
![image](https://user-images.githubusercontent.com/53966749/200156552-315a2d99-2840-424a-9474-a70ecf8f3a57.png)

API
===

![image](https://user-images.githubusercontent.com/53966749/200156621-525a55a6-c1cd-4b38-8002-c44a65a871fa.png)
![image](https://user-images.githubusercontent.com/53966749/200156679-d601d105-7953-4f16-a251-ef126c4108d3.png)
![image](https://user-images.githubusercontent.com/53966749/200156763-361888fd-8154-4cd0-a4c4-ad0aaff0784c.png)
![image](https://user-images.githubusercontent.com/53966749/200156834-29e60c90-4cf2-4162-9c91-2604b38ce9b8.png)
![image](https://user-images.githubusercontent.com/53966749/200157017-ec76163b-7e10-4237-9e79-72a9d268cde7.png)
![image](https://user-images.githubusercontent.com/53966749/200157178-eaf2e4fe-4150-41c6-855f-e8e6e2535712.png)
![image](https://user-images.githubusercontent.com/53966749/200157208-69db8cc7-522e-49ed-a008-b1d3cc55384f.png)


Understand import fields 
========================

![image](https://user-images.githubusercontent.com/53966749/200157253-3ce93fb1-02b6-4699-8dd4-f317c9fb02a5.png)

![image](https://user-images.githubusercontent.com/53966749/200157314-b074b5fc-8857-40f8-8c41-b501da8d97a5.png)

```
sles15sp3:~ # kubectl explain pod
KIND:     Pod
VERSION:  v1

DESCRIPTION:
     Pod is a collection of containers that can run on a host. This resource is
     created by clients and scheduled onto hosts.

FIELDS:
   apiVersion   <string>
     APIVersion defines the versioned schema of this representation of an
     object. Servers should convert recognized schemas to the latest internal
     value, and may reject unrecognized values. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#resources

   kind <string>
     Kind is a string value representing the REST resource this object
     represents. Servers may infer this from the endpoint the client submits
     requests to. Cannot be updated. In CamelCase. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#types-kinds

   metadata     <Object>
     Standard object's metadata. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#metadata

   spec <Object>
     Specification of the desired behavior of the pod. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#spec-and-status

   status       <Object>
     Most recently observed status of the pod. This data may not be up to date.
     Populated by the system. Read-only. More info:
     https://git.k8s.io/community/contributors/devel/sig-architecture/api-conventions.md#spec-and-status
     
  ```
  
```
Multicontainer pods
===================
```
sles15sp3:~ # cat 1.yaml
apiVersion: v1
kind: Pod
metadata:
     name: nginxwebserver
spec:
  containers:
     -    image: nginx
          name: democontainer

     -    image: busybox
          name: mybusybox
          command:
            - sleep
            - "3600"

sles15sp3:~ # kubectl apply -f 1.yaml
pod/nginxwebserver created
sles15sp3:~ # kubectl get pods
NAME             READY   STATUS    RESTARTS   AGE
nginxwebserver   2/2     Running   0          9s
```
![image](https://user-images.githubusercontent.com/53966749/200158272-43e77618-2d59-4163-9833-447bdef12ed7.png)
```
sles15sp3:~ # kubectl exec  -it nginxwebserver -- bash
Defaulted container "democontainer" out of: democontainer, mybusybox
root@nginxwebserver:/# apt-get update && apt-get install net-tools
Get:1 http://deb.debian.org/debian bullseye InRelease [116 kB]

root@nginxwebserver:/# netstat -ntpl
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      1/nginx: master pro
tcp6       0      0 :::80                   :::*                    LISTEN      1/nginx: master pro
root@nginxwebserver:/#

root@nginxwebserver:/# ifconfig eth0
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1460
        inet 10.8.0.14  netmask 255.255.255.0  broadcast 10.8.0.255
        ether 7e:01:53:f8:90:21  txqueuelen 0  (Ethernet)
        RX packets 466  bytes 8887070 (8.4 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 340  bytes 24286 (23.7 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0


sles15sp3:~ # kubectl exec  -it nginxwebserver -c mybusybox sh
kubectl exec [POD] [COMMAND] is DEPRECATED and will be removed in a future version. Use kubectl exec [POD] -- [COMMAND] instead.
/ # netstat -ntpl
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      -
tcp        0      0 :::80                   :::*                    LISTEN      -
/ # curl 127.0.0.1:80
sh: curl: not found
/ # wget  127.0.0.1:80
Connecting to 127.0.0.1:80 (127.0.0.1:80)
saving to 'index.html'
index.html           100% |*********************************************************************************************************************************************************|   615  0:00:00 ETA
'index.html' saved
/ # cat index.html
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

/ #
```
