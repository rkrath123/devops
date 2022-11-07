Maintance of nodes
===================
```

sles15sp3:~/test # kubectl create deployment my-nginx --image=nginx --replicas=7
deployment.apps/my-nginx created

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
 A Kubernetes job is a workload controller object that performs one or more finite tasks in a cluster. The finite nature of jobs differentiates them from most controller objects, such as deployments, replica sets, stateful sets, and daemon sets.

While these objects permanently maintain the desired state and number of pods in the cluster, jobs run until they complete the task and then terminate the associated pods.

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
To configure a job to perform the same task more than once, add the completions field in the spec section of the YAML manifest.
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
Kubernetes can execute more than one task instance at the same time. With sufficient resources, this action improves the speed of job completion.

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
Include the spec.activeDeadlineSeconds field in the job's YAML manifest to limit the duration of the job. The number value corresponds to the number of seconds after which the job terminates, regardless of whether it was fully performed.

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
A Job is a Kubernetes object type whose purpose is to allow administrators to perform finite tasks inside a cluster. Unlike other Kubernetes objects, which ensure the desired number of pods are always running, Jobs terminate pods once the operation finishes.

Regular Kubernetes Jobs can run multiple times if the number of completions declared in the YAML file is larger than one. However, each job instance runs either simultaneously with others or immediately after the previous one completes. To schedule job instances for a later time, use the CronJob controller.

What is Kubernetes CronJob?
----------------------------
The CronJob is a Kubernetes controller that creates Jobs on a repeating schedule. It utilizes the Cron scheduling format used in Linux for script and command scheduling.

CronJobs are used for regularly repeating cluster actions, such as report generation and backups. Furthermore, they allow administrators to schedule an individual task for a later time, such as a period of low activity in the cluster.

How to Configure CronJob
The cron syntax in the spec.schedule field is five characters long, and each character represents one division of time. The table below shows the numbers that can populate each field.

*	*	*	*	*
Minutes
(0-59)	Hours
(0-23)	Days in a month
(1-31)	Months
(1-12)	Weekdays
(0-6)
(Sunday to Saturday)
An asterisk symbol in an expression signifies the unrestricted value. The example below schedules a job for 10 PM every Friday, regardless of the date:
0 22 * * 5
The next example schedules the job for August 28 at 9:15 AM.
15 9 28 8 *
You can also schedule tasks to be performed at a time interval. For example, to schedule a task every hour, type:
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

