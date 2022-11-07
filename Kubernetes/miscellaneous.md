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
