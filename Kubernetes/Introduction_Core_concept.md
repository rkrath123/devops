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





