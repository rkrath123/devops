Upgrade k8s cluster
==================

1) Determine which version to upgrade to

$ apt update
$ apt-cache madison kubeadm
apt-cache madison kubeadm

![image](https://github.com/rkrath123/devops/assets/53966749/dc4e1082-629c-4eca-a898-d5edbbe65372)

2) On the control plane node, run:

$ kubeadm upgrade plan

![image](https://github.com/rkrath123/devops/assets/53966749/e8ef515f-c7fb-476b-a385-cf8429d808a1)

3) Upgrading kubeadm tool

$ apt-mark unhold kubeadm && \
apt-get update && apt-get install -y kubeadm=1.26.3-00 && \
apt-mark hold kubeadm

![image](https://github.com/rkrath123/devops/assets/53966749/1fe45ebc-ff35-4d01-8f9d-94ee4ccd48b9)

4) Verify that the download works and has the expected version:

$ kubeadm version

![image](https://github.com/rkrath123/devops/assets/53966749/d0ce63f3-3972-4af2-a784-3754fdeccda9)

5) Drain the control plane node:

 replace <Node-Name> with the name of your control plane node
$ kubectl drain <Node-Name> --ignore-daemon sets --delete-local-data

![image](https://github.com/rkrath123/devops/assets/53966749/d6b1817e-1460-4098-87dd-562e78ecccec)

6) On the control plane node, run:

$ kubeadm upgrade plan

7) On the control plane node, run:

$ kubeadm upgrade apply v1.26.3

![image](https://github.com/rkrath123/devops/assets/53966749/7a69b8e3-a360-405b-8d54-e9595f03c247)

![image](https://github.com/rkrath123/devops/assets/53966749/30ce25a4-9d67-4951-a48c-c5b8cb97cd9a)

8) Uncordon the control plane node:

$ kubectl uncordon <node name>
$ kubectl uncordon master

9) Upgrade kubelet and kubectl

$ apt-mark unhold kubelet kubectl && \
apt-get update && apt-get install -y kubelet=1.26.3-00 kubectl=1.26.3-00 && \
apt-mark hold kubelet kubectl

![image](https://github.com/rkrath123/devops/assets/53966749/e7ebbb57-4b0c-410f-9dfb-efa7e0f04480)

10) Restart the kubelet

$ systemctl daemon-reload
$ systemctl restart kubelet
11) Check Version

$ kubectl get nodes

![image](https://github.com/rkrath123/devops/assets/53966749/8b7aeed4-b0ab-4927-a18d-0ecf8a6ddfcf)

Upgrade worker nodes
The upgrade procedure on worker nodes should be executed one node at a time or few nodes at a time, without compromising the minimum required capacity for running your workloads.

Note: Follow this section on each of your worker nodes you want to update.

Upgrading the worker nodes consist of the following steps:

Drain the node
Upgrade kubeadm on the node
Upgrade the kubelet configuration (kubeadm upgrade node)
Upgrade kubelet & kubectl
Uncordon the node

1) Check the Version of the worker node From master machine

$ Kubectl get nodes
2) Upgrade kubeadm perform this on Worker Machine

$ apt-mark unhold kubeadm && \
apt-get update && apt-get install -y kubeadm=1.26.3-00 && \
apt-mark hold kubeadm

3) Drain the Worker Node (perform this on master Machine)

$ kubectl drain <node-to-drain> --ignore-daemonsets
$ kubectl drain worker-02 --ignore-daemonsets

4) Upgrade kubelet config on worker node (perform this on Worker Machine)

$ kubeadm upgrade node

5) Upgrade kubelet and kubectl (perform this on Worker Machine)

$ apt-mark unhold kubelet kubectl && \
apt-get update && apt-get install -y kubelet=1.18.8-00 kubectl=1.18.8-00 && \
apt-mark hold kubelet kubectl

6) Restart the kubelet

$ systemctl daemon-reload
$ systemctl restart kubelet
7) Uncordon the node (perform this on master Machine)

$ kubectl uncordon worker-02
 

8) Verify the status of the cluster

$ kubectl get nodes


Maintenance of nodes
===================
```

sles15sp3:~/test # kubectl create deployment my-nginx --image=nginx --replicas=7
deployment. apps/my-nginx created

sles15sp3:~/test # kubectl get pods -o wide
NAME                       READY   STATUS    RESTARTS   AGE   IP          NODE                                       NOMINATED NODE   READINESS GATES
my-nginx-c54945c55-4kfnw   1/1     Running   0          11s   10.8.0.16   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>
my-nginx-c54945c55-8sdt9   1/1     Running   0          12s   10.8.0.15   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>
my-nginx-c54945c55-b8fh2   1/1     Running   0          11s   10.8.1.12   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-g2dbz   1/1     Running   0          11s   10.8.1.13   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-g2qgg   1/1     Running   0          12s   10.8.0.14   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>
my-nginx-c54945c55-r4qks   1/1     Running   0          11s   10.8.2.13   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-slv5k   1/1     Running   0          12s   10.8.1.11   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>

sles15sp3:~/test # kubectl drain gke-cluster-1-default-pool-37115ec3-tzq4 --ignore-daemonsets

sles15sp3:~/test # kubectl get pods -o wide
NAME                       READY   STATUS    RESTARTS   AGE   IP          NODE                                       NOMINATED NODE   READINESS GATES
my-nginx-c54945c55-b8fh2   1/1     Running   0          86s   10.8.1.12   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-g2dbz   1/1     Running   0          86s   10.8.1.13   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-jvbzz   1/1     Running   0          20s   10.8.2.15   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-r4qks   1/1     Running   0          86s   10.8.2.13   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-rbbbc   1/1     Running   0          20s   10.8.1.14   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-rl7q2   1/1     Running   0          20s   10.8.2.14   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-slv5k   1/1     Running   0          87s   10.8.1.11   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>

sles15sp3:~/test # kubectl scale deployment my-nginx --replicas=11
deployment.apps/my-nginx scaled


sles15sp3:~/test # kubectl get pods -o wide
NAME                       READY   STATUS    RESTARTS   AGE     IP          NODE                                       NOMINATED NODE   READINESS GATES
my-nginx-c54945c55-b8fh2   1/1     Running   0          3m26s   10.8.1.12   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-g2dbz   1/1     Running   0          3m26s   10.8.1.13   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-jvbzz   1/1     Running   0          2m20s   10.8.2.15   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-nzl92   1/1     Running   0          11s     10.8.2.16   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-pc57j   1/1     Running   0          11s     10.8.1.17   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-r4qks   1/1     Running   0          3m26s   10.8.2.13   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-rbbbc   1/1     Running   0          2m20s   10.8.1.14   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-rl7q2   1/1     Running   0          2m20s   10.8.2.14   gke-cluster-1-default-pool-37115ec3-1p7j   <none>           <none>
my-nginx-c54945c55-slv5k   1/1     Running   0          3m27s   10.8.1.11   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-t6qng   1/1     Running   0          11s     10.8.1.15   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>
my-nginx-c54945c55-zzrmv   1/1     Running   0          11s     10.8.1.16   gke-cluster-1-default-pool-37115ec3-gq98   <none>           <none>

sles15sp3:~/test # kubectl describe nodes gke-cluster-1-default-pool-37115ec3-tzq4 | grep Taints
Taints:             node.kubernetes.io/unschedulable:NoSchedule
sles15sp3:~/test # kubectl uncordon gke-cluster-1-default-pool-37115ec3-tzq4
node/gke-cluster-1-default-pool-37115ec3-tzq4 uncordoned

sles15sp3:~/test # kubectl describe nodes gke-cluster-1-default-pool-37115ec3-tzq4 | grep Taints
Taints:             <none>
sles15sp3:~/test # kubectl scale deployment my-nginx --replicas=15
deployment.apps/my-nginx scaled
sles15sp3:~/test # kubectl get pods -o wide | grep gke-cluster-1-default-pool-37115ec3-tzq4
my-nginx-c54945c55-58pp4   1/1     Running   0          16s   10.8.0.21   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>
my-nginx-c54945c55-6qcg4   1/1     Running   0          16s   10.8.0.19   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>
my-nginx-c54945c55-86g9s   1/1     Running   0          15s   10.8.0.22   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>
my-nginx-c54945c55-v6xlt   1/1     Running   0          16s   10.8.0.20   gke-cluster-1-default-pool-37115ec3-tzq4   <none>           <none>


 Safely Drain a Node
 ==================
 kubectl drain <node nam
 power on/reboot node
 kubectl uncordon <node name>
```

 Kubernetes Job
 ==============
 ```
 A Kubernetes job is a workload controller object that performs one or more finite tasks in a cluster. 
 The finite nature of jobs differentiates them from most controller objects, such as deployments, replica sets, stateful sets, and daemon sets.

While these objects permanently maintain the desired state and number of pods in the cluster,
jobs run until they complete the task and then terminate the associated pods.

Kubernetes Job Use Cases
-------------------------
Kubernetes jobs can perform many important tasks in a cluster, including:

Maintenance tasks (such as performing backups).
Large calculations.
Batch tasks (such as sending emails).
Monitoring node behaviors.
Managing work queues.
Some Helm charts use jobs to install apps.

 Create Kubernetes Job
 ---------------------
 sles15sp3:~/test # cat  jobs.yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: kplabs-job
spec:
  template:
    spec:
      containers:
      - name: kplabs-pods
        image: busybox
        command: ["/bin/sh"]
        args: ["-c", "echo Hello World"]
      restartPolicy: Never

sles15sp3:~/test # kubectl apply -f jobs.yaml
job.batch/kplabs-job created
sles15sp3:~/test # kubectl get pod
NAME               READY   STATUS      RESTARTS   AGE
kplabs-job-lfx7p   0/1     Completed   0          7s
sles15sp3:~/test # kubectl describe pod kplabs-job-lfx7p
Name:         kplabs-job-lfx7p
Namespace:    default
Priority:     0
Node:         gke-cluster-1-default-pool-37115ec3-tzq4/10.128.0.33
Start Time:   Mon, 07 Nov 2022 07:36:39 +0000
Labels:       controller-uid=87585a74-1d43-48c9-9b8a-799e5908ca8b
              job-name=kplabs-job
Annotations:  <none>
Status:       Succeeded

   State:          Terminated
      Reason:       Completed
      Exit Code:    0

Execute Job More Than Once
---------------------------
To configure a job to perform the same task more than once,
add the completions field in the spec section of the YAML manifest.

sles15sp3:~/test # cat jobs.yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: kplabs-job
spec:
  completions: 10
  template:
    spec:
      containers:
      - name: kplabs-pods
        image: busybox
        command: ["/bin/sh"]
        args: ["-c", "echo Hello World"]
      restartPolicy: Never

sles15sp3:~/test # kubectl apply -f jobs.yaml
job.batch/kplabs-job created
sles15sp3:~/test # kubectl get job --watch
NAME         COMPLETIONS   DURATION   AGE
kplabs-job   1/10          6s         6s
kplabs-job   2/10          8s         8s
kplabs-job   3/10          12s        12s
kplabs-job   4/10          16s        16s
kplabs-job   5/10          20s        20s
kplabs-job   6/10          24s        24s
kplabs-job   7/10          28s        28s
kplabs-job   8/10          32s        32s
kplabs-job   9/10          36s        36s
kplabs-job   10/10         52s        52s

sles15sp3:~/test # kubectl get job
NAME         COMPLETIONS   DURATION   AGE
kplabs-job   10/10         52s        111s


Execute Parallel Job Instances
------------------------------
Kubernetes can execute more than one task instance at the same time.
With sufficient resources, this action improves the speed of job completion.

sles15sp3:~/test # cat jobs.yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: kplabs-job
spec:
  completions: 10
  parallelism: 5
  template:
    spec:
      containers:
      - name: kplabs-pods
        image: busybox
        command: ["/bin/sh"]
        args: ["-c", "echo Hello World"]
      restartPolicy: Never


sles15sp3:~/test # kubectl apply -f jobs.yaml
job.batch/kplabs-job created
sles15sp3:~/test #  kubectl get job --watch
NAME         COMPLETIONS   DURATION   AGE
kplabs-job   1/10          4s         4s
kplabs-job   2/10          4s         4s
kplabs-job   3/10          4s         4s
kplabs-job   4/10          6s         6s
kplabs-job   5/10          6s         6s
kplabs-job   6/10          7s         7s
kplabs-job   7/10          7s         7s
kplabs-job   8/10          8s         8s
kplabs-job   9/10          10s        10s
kplabs-job   10/10         10s        10s
sles15sp3:~/test # kubectl get job
NAME         COMPLETIONS   DURATION   AGE
kplabs-job   10/10         10s        22s

Limit Time for Job Completion
-----------------------------
Include the spec.activeDeadlineSeconds field in the job's YAML manifest to limit the duration of the job. 
The number value corresponds to the number of seconds after which the job terminates, 
regardless of whether it was fully performed.

sles15sp3:~/test # cat jobs.yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: kplabs-job
spec:
  completions: 10
  activeDeadlineSeconds: 10
  template:
    spec:
      containers:
      - name: kplabs-pods
        image: busybox
        command: ["/bin/sh"]
        args: ["-c", "echo Hello World"]
      restartPolicy: Never
sles15sp3:~/test #

sles15sp3:~/test # kubectl apply -f jobs.yaml
job.batch/kplabs-job created
sles15sp3:~/test # kubectl get job --watch
NAME         COMPLETIONS   DURATION   AGE
kplabs-job   0/10          3s         3s
kplabs-job   1/10          4s         4s
kplabs-job   2/10          8s         8s
kplabs-job   2/10          10s        10s

The output shows only two pods completed.

sles15sp3:~/test # kubectl get job
NAME         COMPLETIONS   DURATION   AGE
kplabs-job   2/10          45s        45s
  
 sles15sp3:~/test # kubectl describe job kplabs-job
 
 Events:
  Type     Reason            Age        From            Message
  ----     ------            ----       ----            -------
  Normal   SuccessfulCreate  <invalid>  job-controller  Created pod: kplabs-job-x8qlg
  Normal   SuccessfulCreate  <invalid>  job-controller  Created pod: kplabs-job-wb474
  Normal   SuccessfulCreate  <invalid>  job-controller  Created pod: kplabs-job-rfjm4
  Normal   SuccessfulDelete  <invalid>  job-controller  Deleted pod: kplabs-job-rfjm4
  Warning  DeadlineExceeded  <invalid>  job-controller  Job was active longer than specified deadline

delete job
----------
kubectl delete job [job-name]
kubectl delete -f [filename].yaml

```
Cron Job
=======
```
A Job is a Kubernetes object type whose purpose is to allow administrators to perform finite tasks inside a cluster.
Unlike other Kubernetes objects, which ensure the desired number of pods are always running,
Jobs terminate pods once the operation finishes.

Regular Kubernetes Jobs can run multiple times if the number of completions declared in the YAML file is larger than one.
However, each job instance runs either simultaneously with others or immediately after the previous one completes.
To schedule job instances for a later time, use the CronJob controller.

What is Kubernetes CronJob?
----------------------------
The CronJob is a Kubernetes controller that creates Jobs on a repeating schedule.
It utilizes the Cron scheduling format used in Linux for script and command scheduling.

CronJobs are used for regularly repeating cluster actions, such as report generation and backups. 
Furthermore, they allow administrators to schedule an individual task for a later time, 
such as a period of low activity in the cluster.

How to Configure CronJob
The cron syntax in the spec.schedule field is five characters long, 
and each character represents one division of time.
The table below shows the numbers that can populate each field.

*	*	*	*	*
Minutes
(0-59)	Hours
(0-23)	Days in a month
(1-31)	Months
(1-12)	Weekdays
(0-6)
(Sunday to Saturday)
An asterisk symbol in an expression signifies the unrestricted value.
The example below schedules a job for 10 PM every Friday, regardless of the date:
0 22 * * 5
The next example schedules the job for August 28 at 9:15 AM.
15 9 28 8 *
You can also schedule tasks to be performed at a time interval. 
For example, to schedule a task every hour, type:
* */1 * * *

sles15sp3:~/test # cat cron_job.yaml
----------------------------------
apiVersion: batch/v1
kind: CronJob
metadata:
  name: test-cron-job
spec:
  schedule: "*/1 * * * *"
  jobTemplate:
    metadata:
      name: test-job
    spec:
      template:
        spec:
          containers:
          - name: test
            image: alpine:latest
            command:
            - "bin/sh"
            - "-c"
            - "for i in 1 2 3 4 5 6 7 8 9 ; do echo $i ; done"
          restartPolicy: Never

sles15sp3:~/test # kubectl apply -f cron_job.yaml
Warning: batch/v1beta1 CronJob is deprecated in v1.21+, unavailable in v1.25+; use batch/v1 CronJob
cronjob.batch/test-cron-job created
sles15sp3:~/test # kubectl get cronjob --watch
NAME            SCHEDULE      SUSPEND   ACTIVE   LAST SCHEDULE   AGE
test-cron-job   */1 * * * *   False     0        <none>          11s
test-cron-job   */1 * * * *   False     1        0s              48s


to delete cron job
--------------------
kubectl delete cronjob [cronjob-name]
kubectl delete -f [filename].yaml

```
![image](https://user-images.githubusercontent.com/53966749/200277218-f7b6c82b-1322-47af-9ffe-882538e40da3.png)

Kubernetes — Liveness and Readiness Probes
==========================================

Liveness
--------
Liveness Probe
Suppose that a Pod is running our application inside a container,but due to some reason let’s say memory leak, cpu usage, 
application deadlock etc the application is not responding to our requests, and stuck in error state.

Liveness probe checks the container health as we tell it do, and if for some reason the liveness probe fails, 
it restarts the container. We can define liveness probe in 3 ways:

We are creating a container with name liveness, and as the container initialise we use the following command:

- touch /tmp/healthy; sleep 30; rm -rf /tmp/healthy; sleep 600
to create a file healthy at path /tmp/healthy, and delete it after 30 seconds.

```

apiVersion: v1
kind: Pod
metadata:
  labels:
    test: liveness
  name: liveness-exec
spec:
  containers:
  - name: liveness
    image: k8s.gcr.io/busybox
    args:
    - /bin/sh
    - -c
    - touch /tmp/healthy; sleep 30; rm -rf /tmp/healthy; sleep 600
    livenessProbe:
      exec:
        command:
        - cat
        - /tmp/healthy
      initialDelaySeconds: 3
      periodSeconds: 5
      
  --------------
 cat   commands tell the liveness probe to open file at path /tmp/healthy, 
 and if it can’t the liveness probe will fail and container will restart.

initialDelaySeconds: 3
This is the delay which tells kubelet to wait for 3 seconds before performing the first probe

periodSeconds: 5
This field specifies that kubelet should perform a probe every 5 seconds.

So, according to above example our container will start and work fine for first 30 seconds,
and after that liveness probe will fail and restart the container.

sles15sp3:~/test # kubectl apply -f pod.yaml
pod/liveness-exec created
sles15sp3:~/test #
sles15sp3:~/test # kubectl get pods
NAME            READY   STATUS    RESTARTS   AGE
liveness-exec   1/1     Running   0          10s
sles15sp3:~/test # kubectl get pods --watch
NAME            READY   STATUS    RESTARTS   AGE
liveness-exec   1/1     Running   0          15s
liveness-exec   1/1     Running   1 (1s ago)   77s
liveness-exec   1/1     Running   2 (1s ago)   2m32s

liveness-http
-------------
apiVersion: v1
kind: Pod
metadata:
  name: liveness-exec
spec:
  containers:
  - name: liveness
    image: nginx
    ports:
    - containerPort: 80
    livenessProbe:
      httpGet:
         path: /kplabs.html
         port: 80
      initialDelaySeconds: 60
      periodSeconds: 5
      
liveness nginx
--------------
  apiVersion: v1
kind: Pod
metadata:
  name: liveness
spec:
  containers:
  - name: liveness
    image: ubuntu
    tty: true
    livenessProbe:
      exec:
        command:
        - service
        - nginx
        - status
      initialDelaySeconds: 20
      periodSeconds: 5
```
Readiness Probe
---------------
In some cases we would like our application to be alive, but not serve traffic unless some conditions are met e.g, 
populating a dataset, waiting for some other service to be alive etc. 
In such cases we use readiness probe. If the condition inside readiness probe passes, only then our application can serve traffic.

Readiness probe is defined in 3 ways exactly like the Liveness probe above. We just need to replace livenessProbe with readinessProbe like this:
```
readinessProbe:
  exec:
    command:
    - cat
    - /tmp/healthy
  initialDelaySeconds: 5
  periodSeconds: 5
  
Summary
Both liveness & readiness probes are used to control the health of an application. Failing liveness probe will restart the container, whereas failing readiness probe will stop our application from serving traffic.

sles15sp3:~/test # cat readiness.yaml
---------------------------------------
apiVersion: v1
kind: Pod
metadata:
  name: readiness
spec:
  containers:
  - name: readiness
    image: ubuntu
    tty: true
    readinessProbe:
     exec:
       command:
       - cat
       - /tmp/healthy
     initialDelaySeconds: 5
     periodSeconds: 5

sles15sp3:~/test # kubectl exec -it readiness -- touch /tmp/healthy

sles15sp3:~/test # kubectl get pods
NAME        READY   STATUS    RESTARTS   AGE
readiness   0/1     Running   0          34s
sles15sp3:~/test # kubectl get pods
NAME        READY   STATUS    RESTARTS   AGE
readiness   1/1     Running   0          37s



```

