Introduction
=============

![image](https://user-images.githubusercontent.com/53966749/200154391-74f0b1a1-9721-4fb4-ba4e-afff752f5c9b.png)
![image](https://user-images.githubusercontent.com/53966749/200154424-fb684a69-dfb6-4ba9-ba52-eb15e7e9b964.png)
![image](https://user-images.githubusercontent.com/53966749/200154511-df7dccc1-7ca5-470b-80f6-2f201dbc94ab.png)
![image](https://user-images.githubusercontent.com/53966749/200154592-f8557045-4f94-4ada-ba16-4368415ce254.png)
![image](https://user-images.githubusercontent.com/53966749/200154722-bf20ff59-2833-4fdd-b677-7b0387ff4f0a.png)
![image](https://user-images.githubusercontent.com/53966749/200154757-1138c9a4-6ee8-4a9c-aeb1-5075cbe1a4ac.png)

Kubectl
-------

![image](https://user-images.githubusercontent.com/53966749/200155214-eaca9892-59ed-4dfb-9781-4ef488202747.png)
![image](https://user-images.githubusercontent.com/53966749/200155242-634ff5f4-e7b4-4f4f-9d77-38ff38323fa7.png)

Docker vs Kubernetes
--------------------

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




