Challanges with files in  Container Writable layer
==================================================

![image](https://user-images.githubusercontent.com/53966749/201319700-f2566982-f3db-49c3-b4b0-7e2ee8dcc743.png)
![image](https://user-images.githubusercontent.com/53966749/201320262-d99f6402-f1fc-495f-9f34-b51b49d774bd.png)

```
sles15sp3:~ # docker run -it -d  nginx
d2bd07c6a9be642fed590825a13e37738cfd84c073d77a2e983d9c47fbf8b330

sles15sp3:~ # ls /var/lib/docker/overlay2/
1e8b68a3b7b8bd133d1b4397e6d37842a199aa0747d39030a2703624c6b253a5  c584ab937fa70070431ac07cd0872bb068f5494d973903c7574aeaad534475a6
30c58a1a30fcbc3a9afb38a8ce9e4b620ecc6b33995a68b0af2756c0b0f11c30  c876f6b9872e86e3b88062798a3497781c1b6fd2414adf15234a2aa7e8f55f0b
6826b19e40e2b6d86692e7f3de4de490bc06939100fc2a82b68cbd174178786f  c876f6b9872e86e3b88062798a3497781c1b6fd2414adf15234a2aa7e8f55f0b-init
6bbeba56a4ea331bddbdf4e26f60e584946df53ced0c20bee0a3eac80a342bf3  d4e1c185a3096841d30ec6ecf6bfef5ece9478c26462660a6ca2a82e3f1d425c
8f8f1943aab474f20b823038143182511c521ecc47dabc10d5f203f3e1e9e83a  l
sles15sp3:~ #
sles15sp3:~ # ls /var/lib/docker/overlay2/ | wc -l
10
sles15sp3:~ # docker rm -f d2bd07c6a9be
d2bd07c6a9be
sles15sp3:~ # ls /var/lib/docker/overlay2/ | wc -l
8


-----------------------
sles15sp3:~ # docker volume ls
DRIVER    VOLUME NAME
sles15sp3:~ #
sles15sp3:~ #
sles15sp3:~ # docker volume create myvolume
myvolume
sles15sp3:~ # docker volume ls
DRIVER    VOLUME NAME
local     myvolume
sles15sp3:~ # docker run -it -d --name busybox -v myvolume:/etc busybox sh
0f61268e08cc90d9665dec0e2fe8f68ef8c8b8005c03f02617fb39eb69141614
sles15sp3:~ # docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED         STATUS         PORTS     NAMES
0f61268e08cc   busybox   "sh"      4 seconds ago   Up 3 seconds             busybox
sles15sp3:~ # docker volume inspect myvolume
[
    {
        "CreatedAt": "2022-11-11T10:33:43Z",
        "Driver": "local",
        "Labels": {},
        "Mountpoint": "/var/lib/docker/volumes/myvolume/_data",
        "Name": "myvolume",
        "Options": {},
        "Scope": "local"
    }
]
sles15sp3:~ # cd /var/lib/docker/volumes/myvolume/_data
sles15sp3:/var/lib/docker/volumes/myvolume/_data # ls
group  hostname  hosts  localtime  mtab  network  passwd  resolv.conf  shadow
sles15sp3:/var/lib/docker/volumes/myvolume/_data # docker exec -it busybox sh
/ # ls /etc/
group        hostname     hosts        localtime    mtab         network      passwd       resolv.conf  shadow
/ # df -h
Filesystem                Size      Used Available Use% Mounted on
overlay                  49.1G      4.8G     42.3G  10% /
tmpfs                    64.0M         0     64.0M   0% /dev
tmpfs                     1.5G         0      1.5G   0% /sys/fs/cgroup
shm                      64.0M         0     64.0M   0% /dev/shm
/dev/vda3                49.1G      4.8G     42.3G  10% /etc
/dev/vda3                49.1G      4.8G     42.3G  10% /etc/resolv.conf
/dev/vda3                49.1G      4.8G     42.3G  10% /etc/hostname
/dev/vda3                49.1G      4.8G     42.3G  10% /etc/hosts
tmpfs                     1.5G         0      1.5G   0% /run/secrets/credentials.d
tmpfs                     1.5G         0      1.5G   0% /proc/acpi
tmpfs                    64.0M         0     64.0M   0% /proc/kcore
tmpfs                    64.0M         0     64.0M   0% /proc/keys
tmpfs                    64.0M         0     64.0M   0% /proc/latency_stats
tmpfs                    64.0M         0     64.0M   0% /proc/timer_list
tmpfs                    64.0M         0     64.0M   0% /proc/sched_debug
tmpfs                     1.5G         0      1.5G   0% /proc/scsi
tmpfs                     1.5G         0      1.5G   0% /sys/firmware
/ # exit
sles15sp3:/var/lib/docker/volumes/myvolume/_data # docker rm -f busybox
busybox
sles15sp3:/var/lib/docker/volumes/myvolume/_data # ls
group  hostname  hosts  localtime  mtab  network  passwd  resolv.conf  shadow
sles15sp3:/var/lib/docker/volumes/myvolume/_data # cd ~
sles15sp3:~ # docker volume ls
DRIVER    VOLUME NAME
local     myvolume
sles15sp3:~ # docker volume rm myvolume
myvolume
sles15sp3:~ # docker volume ls
DRIVER    VOLUME NAME
sles15sp3:~ #

```
![image](https://user-images.githubusercontent.com/53966749/201324647-093b5387-a352-4df6-b2b4-c206443d7c83.png)
![image](https://user-images.githubusercontent.com/53966749/201324719-f48557a2-8e6d-4039-98ef-917a2fc4864b.png)
![image](https://user-images.githubusercontent.com/53966749/201325017-1c03b708-4acc-4758-951b-1aa99e142eee.png)
![image](https://user-images.githubusercontent.com/53966749/201325055-f58d7849-8314-4d54-b68a-69d9be331621.png)
![image](https://user-images.githubusercontent.com/53966749/201325513-e977635c-7e30-4658-832e-56fa07dec853.png)
![image](https://user-images.githubusercontent.com/53966749/201325627-52c65ed4-7417-4b7e-8912-80944a46d07f.png)

![image](https://user-images.githubusercontent.com/53966749/201325741-29e40675-81df-479c-992d-c4c16cde0837.png)

