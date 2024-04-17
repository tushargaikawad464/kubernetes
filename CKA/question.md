1. You have been asked to create a new ClusterRole for a deployment pipeline and bind it to a specific ServiceAccount scoped to a specific namespace.
    - Create a new ClusterRole named deployment-clusterrole, which only allows to create the following resource types:D
    - Deployment
    - Stateful Set
    - DaemonSet
    - Create a new ServiceAccount named cicd-token in the existing namespace app-team1.
    - Bind the new ClusterRole deployment-clusterrole to the new ServiceAccount cicd-token, limited to the namespace app-team1.
2. Set the node named ek8s-node-0 as unavailable and reschedule all the pods running on it.
3. Given an existing Kubernetes cluster running version 1.22.1, upgrade all of the Kubernetes control plane and node components on the master node only to version 1.22.2.
Be sure to drain the master node before upgrading it and uncordon it after the upgrade.
4. First, create a snapshot of the existing etcd instance running at https://127.0.0.1:2379, saving the snapshot to /var/lib/backup/etcd-snapshot.db. Next, restore an existing, previous snapshot located at /var/lib/backup/etcd-snapshot-previous.db.
5. Create a new NetworkPolicy named allow-port-from-namespace in the existing namespace fubar.
Ensure that the new NetworkPolicy allows Pods in namespace internal to connect to port 9000 of Pods in namespace fubar.
Further ensure that the new NetworkPolicy:
    - does not allow access to Pods, which don't listen on port 9000
    - does not allow access from Pods, which are not in namespace internal
6. Reconfigure the existing deployment front-end and add a port specification named http exposing port 80/tcp of the existing container nginx.
Create a new service named front-end-svc exposing the container port http.
Configure the new service to also expose the individual Pods via a NodePort on the nodes on which they are scheduled.
7. Scale the deployment presentation to 3 pods.
8 Schedule a pod as follows:
    - Name: nginx-kusc00401
    - Image: nginx
    - Node selector: disk=ssd
9. Check to see how many nodes are ready (not including nodes tainted NoSchedule) and write the number to /opt/KUSC00402/kusc00402.txt.
10. Schedule a Pod as follows:
    - Name: kucc8
    - App Containers: 2
    - Container Name/Images:
    - nginx
    - consul
11. Create a persistent volume with name app-data, of capacity 2Gi and access mode ReadOnlyMany. The type of volume is hostPath and its location is /srv/app- data.
12. Monitor the logs of pod foo and:
    - Extract log lines corresponding to error file-not-found
    - Write them to /opt/KUTR00101/foo
13. An existing Pod needs to be integrated into the Kubernetes built-in logging architecture (e.g. kubectl logs). Adding a streaming sidecar container is a good and common way to accomplish this requirement.
    - Add a sidecar container named sidecar, using the busybox image, to the existing Pod big-corp-app. The new sidecar container has to run the following command:
    - Use a Volume, mounted at /var/log, to make the log file big-corp-app.log available to the sidecar container.
14. From the pod label name=overloaded-cpu, find pods running high CPU workloads and write the name of the pod consuming most CPU to the file /opt/
KUTR00401/KUTR00401.txt (which already exists).
15. A Kubernetes worker node, named wk8s-node-0 is in state NotReady. Investigate why this is the case, and perform any appropriate steps to bring the node to a Ready state, ensuring that any changes are made permanent.
16. Extract the log lines of a pod corresponding to “File-not-found” to /opt/error.txt
17. List all pvs by sorting with name and write the output into a file /opt/pvs.txt
19. List all pvs by sorting with name and write the output into a file /opt/pvs.txt
20. You are given a file that will create a pod of nginx with nginx image.under /opt/nginx-pod.yaml . Modify the file to create an init container that is supposed to create a text file workdir/file1.txt
21. create pod of mypod with the image of nginx+redis (multicontainer)
22. Create a deployment of nginx with the image of nginx of version 1.18-alpine. Now upgrade the version to 1.19-alpine and record it. Now roll back the deployment to the previous version.
23. Create a deployment of Nginx with 6 replicas
24. Create a pod of jenkins with the image jenkins in the namespace of web-frontend
25. Create a configuration file to create a pod of redis with redis image and 6 replicas with label app_env_stage=dev. The file should be placed under /opt/cka
26. Create a deployment of nginx and expose it as a service nginx-service. Use the nslookup uttility to look up the DNS records of the service and pods and write the outputs into /opt/nslookup/output.svc and /opt/nslookup/output.pod
27. Create a new service account with the name pvviewer. Grant this Service account access to list all PersistentVolumes in the cluster by creating an appropriate cluster role called pvviewer-role and ClusterRoleBinding called pvviewer-role-binding.
28. Create a new deployment called nginx-deploy, with image nginx:1.16 and 1 replica. Record the version. Next upgrade the deployment to version 1.17 using rolling update. Make sure that the version upgrade is recorded in the resource annotation.
29. Create snapshot of the etcd running at https://127.0.0.1:2379. Save snapshot into /opt/etcd-snapshot.db.
30. Create a Persistent Volume with the given specification.
31. Taint the worker node to be Unschedulable. Once done, create a pod called dev-redis, image redis:alpine to ensure workloads are not scheduled to this worker node. Finally, create a new pod called prod-redis and image redis:alpine with toleration to be scheduled on node01.
32. Set the node named worker node as unavailable and reschedule all the pods running on it. (Drain node)
33. Create a Pod called non-root-pod , image: redis:alpine
34. Create a NetworkPolicy which denies all ingress traffic
35. Understand ClusterIP, NodePort, LoadBalancer service types and endpoints
        - Create a deployment with the latest nginx image and two replicas.
        - Expose it's port 80 through a service of type NodePort.
        - Show all elements, including the endpoints.
        - Get the nginx index page through the NodePort.
36. Deploy and configure network load balancer and Do the same exercice as in the previous section but use a Load Balancer service type rather than a NodePort.
37. Questions:
        - Keep the previous deployment of nginx and add a new deployment using the image bitnami/apache with two replicas.
        - Expose its port 8080 through a service and query it.
        - Deploy nginx ingress controller
        - Create an ingress service that redirects /nginx to the nginx service and /apache to the apache service.
38. Create a busybox pod and resolve the nginx and apache services created earlier from within the pod.
39. Questions:
        - Create a pod and mount a volume with hostPath directory.
        - Check that the contents of the directory are accessible through the pod.
40. Questions:
        - Create a persistent volume from hostPath and a persistent volume claim corresponding tothat PV. Create a pod that uses the PVC and check that the volume is mounted in the pod.
        - Create a file from the pod in the volume then delete it and create a new pod with the same volume and show the created file by the first pod.
41. Create an nginx pod with a liveness and a readiness probe for the port 80.
42. Install the metrics server and show metrics for nodes and for pods in kube-system namespace.
43. Get logs from the nginx pod deployed earlier and redirect them to a file.
44. Questions:
        - Launch a pod with a busybox container that launches with the sheep 3600 command (this command doesn't exist.
        - Get the logs from the pod, then correct the error to make it launch sleep 3600.
45. Get logs from the control plane in the kube-system namespace.
46. Check the node status and the system logs for kubelet on the failing node.
47. Check the kube-dns service running in the kube-system namespace and check the endpoints behind the service. Check the pods that serve the endpoints.
48. Questions:
        - Create a deployment named nginx-deploy in the ns-nginx namespace using nginx image version 1.22 with three replicas. Check that the deployment rolled out and show running pods.
49. Questions:
        - Scale the deployment to 5 replicas and check the status again.
        - Then change the image tag of nginx container from 1.22 to 1.23.
        - Check the history of the deployment and rollback to previous revision.
        - Then check that the nginx image was reverted to 1.22.
50. Questions:
        - Create a pod with the latest busybox image running a sleep for 1 hour, and give it an environment variable named PLANET with the value blue.
        - Then exec a command in the container to show that it has the configured environment variable.
51. Questions:
        - Create a configmap named space with two values planet=blue and moon=white.
        - Create a pod similar to the previous where you have two environment variables taken from the above configmap and show them in the container.
52. Questions:
        - Create a configmap named space-system that contains a file named system.conf with the values planet=blue and moon=white.
        - Mount the configmap to a pod and display it from the container through the path /etc/system.conf
53. Questions:
        - Create a secret from files containing a username and a password.
        - Use the secrets to define environment variables and display them.
        - Mount the secret to a pod to admin-cred folder and display it.
54. Create a deployment with the latest nginx image and scale the deployment to 4 replicas.
55. Autoscale a deployment to have a minimum of two pods and a maximum of 6 pods and that transitions when cpu usage goes above 70%.
56. Create a DaemonSet with the latest busybox image and see that it runs on all nodes.
57. Create a pod with a busybox container that requests 1G of memory and half a CPU, and has limits at 2G of memory and a whole CPU.
58. Label a node with kind=special and schedule a pod to that node.
59. Use antiaffinity to launch a pod to a different node than the pod where the first one was scheduled.
60. Taint a node with type=special:NoSchedule, make the other node unschedulable, and create a pod to tolerate this taint.
61. Force a pod to be on a specific node with using the scheduler, and show that it was assigned to it.
62. Check the scheduler events.
63. Use KubeADM to install a basic cluster (https://github.com/alijahnas/CKA-practice-exercises/blob/CKA-v1.27/cluster-architecture-installation-configuration.md#use-kubeadm-to-install-a-basic-cluster)
64. Perform a version upgrade on a Kubernetes cluster using KubeADM
65. Facilitate operating system upgrades
66. https://github.com/alijahnas/CKA-practice-exercises/blob/CKA-v1.27/cluster-architecture-installation-configuration.md#provision-underlying-infrastructure-to-deploy-a-kubernetes-cluster
67. Implement etcd backup and restore
68. Create a PVC my-pvc with the capacity 10Gi and storage class k8s-csi-plugin. 
69. Assign the PVC to the pod named nginx-pod with image nginx and mount to path /usr/share/html 
        - Ensure the pod claims the volume as ReadWriteMany access mode 
        - Use kubectl patch or kubectl edit to update the capacity of the PVC as 70Gi to record the change.
70. Create a persistent Volume with name my-vol, of capactiy 2Gi and access mode ReadWriteOnce. The type of volume is hostpath and its location is /path/to/file
71. Upgrade master control plane components from version 1.20.0 to only version 1.20.1. • Drain the master before start the upgrade and uncordn once the upgrade is completed • Update the kubelet and kubeadm as well
72. Create a snapshot of the etcd instance running at https://127.0.0.1:2379 saving the snapshot to the file path /path/to/backup/etcdbkp.db The etcd instance is running etcd version 3.1.10 Use the below TLS certificates/keys for connecting to the server with etcdctl. CA certificate: /opt/ca.crt Client certificate: /opt/etcd-client.crt Clientkey:/opt/etcd-client.key 
73. The node k8s-node is not in ready state. Ssh to the node and troubleshoot the issue, make the changes permanent to avoid the problem in future.
74. Check to see how many nodes are ready (not including nodes tainted NoSchedule) and write the number to /path/to/node
75. Scale the deployment webserver to 6 pods
        - Name: non-persistent-redis Container image: redis Named-volume with name: cache-control Mount path: /data/redis It should launch in the pre-prod namespace and the volume  NOT be persistent.
        - From the Pod label name:cpu-utilizer, find pods running high CPU workloads and write the name of the Pod consuming most CPU to the file /opt/cpu.txt
76. Set the node labelled with name:node-01 as unavailable and reschedule all the pods running on it.
77. Reconfigure the existing deployment front-end: Add a port specification named http exposing port 80/tcp of the existing container nginx add a selector entry with key foo and value bar • Create a new service named front-end-svc exposing the container port http. Also use the new selector entry foo to select the service's target. • Configure the new service to also expose the individual Pods via a port on the host on which they are scheduled
78. Create a Pod as follows: Name: jenkins Using image: jenkins In a new Kubenetes namespace named tools
79. Question
        - Create a service account my-sa in new namespace my-ns. 
        - Create a cluster role with the name new-cluster-role and ensure the role only can create and list below resources. 
        - DaemonSets • Deployments • Replicaset • Pods
        - Ensure only the newly created service account can use the role and it is effective with the name space my-ns.
80. Create a Static pod, Name: consul Using image: consul In a new Kubenetes namespace named tools 
81. A Kubernetes worker node, labelled with name "node-01" is in state NotReady . Investigate why this is the case, and perform any appropriate steps to bring the node to a Ready state, ensuring that any changes are made permanent. (find cause what can be except kubelet restart)
82. Create a custom scheduler. Added create a new pod and schedule it using custom scheduler Name: custom-scheduler Namespace: kube-system
83. Creae a persistent volume with name my-vol of capacity 10Gi and access mode ReadWriteOnce. The type of volume is hostPath and its location is /test/path
84. From the pod label name=cpu-burner, find pods running high CPU workloads and Write the name of the pod consuming most CPU to the file /tmp/cpu.txt.
85. Schedule a pod as follows Name :- nginx01 image :- nginx Node Selector :- name=node.
86. Create a new nginx Ingress resource as follows: o Name: nginx-ingress o Namespace: ingress-ns o Exposing service me.html on path /me.html using service port 8080 o Exposing service test on path /test using service port 8080
87. Create a NetworkPolicy named k8s-netpol in the namespace namespace-netpol in a way that pods running on namespace internal on port 9200 can only access pods running in namespace-netpol. a. Allow the pods to communicate if they are running on port 9200 within the namespace b. Ensure the NetworkPolicy doesn’t allow other pods that are running other than port 9200 c. The communication from and to the pods running on port 9200 d. No pods running on port 9200 from other name spaces to allowed. NB: There will be a default deny all from any namespace netpol will be already present.
88. Add a side car container to the running pod logging-pod with the blow specification. The image of the sidecar container is busybox and the container writes the logs as below tail -n+1 /var/log/k8slog/application.log The container shares the volume logs with the application container the mounts to the directory /var/log/k8slog Do not alter the application container and verify the logs are written properly to the file looging-pod primary container logger does not write to any volumes, you need to create a volume from empty dir and mount it appropriately.
89. Monitor the logs of pod loggy and extract log lines issue-not-found. Write the output to /tmp/pod.txt.
90. Create a deployment and perform rollback. Name: nginx Using container nginx with version 1.11-alpine The deployment should contain 3 replicas Next, deploy the app with new version 1.13-alpine by performing a rolling update and record that update. Finally, rollback that update to the previous version 1.11-alpine 
91. Create a new pod with the nginx image.
92. Create a new pod with the name redis and with the image redis:1.99.
93. Identify the problem with the pod.
94. Rectify the problem with the pod and wait until the pod is ready and healthy.
95. Create a new replicaset rs-1 using image nginx with labels tier:frontend and selectors as tier:frontend. Create 3 replicas for the same.
95. Update the image of the above replicaset to use nginx:alpine image.
96. Scale down the replicaset to 2 replicas.
97. Create a new deployment deploy-1 using image busybox with 3 replicas and command sleep 3600.
98. Update the image of the above deployment with image ubuntu.
99. Create a service redis-service to expose the redis02 application within the cluster on port 6379.
100. Create a new pod called custom-nginx using the nginx image and expose it on container port 8080.
101. Create a pod called httpd using the image httpd:alpine in the default namespace. Next, create a service of type ClusterIP by the same name (httpd). The target port for the service should be 80.
102. Create a pod with the ubuntu image to run a container to sleep for 5000 seconds.
103. Create a new ConfigMap for the webapp-color pod. Set key-value pairs as COLOR=blue.
104. Create a deployment nginx01 using nginx image, which has environment variable CREATED_BY with value octocat. Verify the environment variable in the containers of the above deployment.
105. Create a new config map db-config with key-value pairs as:
        - db-host = "localhost.example.com"
        - db-port = 3306
        - db-name = "kubernetes-objects"
106. Mount the config map db-config in the deployment ubuntu01 with image ubuntu which has 2 replicas.
107. Create a deployment named multi-con-01, which has two containers, one container uses nginx image and has port 80 exposed. Mount the config map db-config as environment variable. Create the second container in the same deployment with image ubuntu, keep the container alive using the command sleep 5000 and mount the config map in db-config with different keys where the new keys are mapped as:
        - db-host --> DB_URL
        - db-port --> DB_PORT
        - db-name --> DB_NAME
108. Create an opaque secret named db-creds with following key value pairs:
        - db_user=root
        - db_password=pass404
        - db_role=admin
109. Mount the secret db-creds in the deployment multi-con-01 [created in (23)] as environment variables in the ubuntu container with the same keys as mentioned in the secret.
110. Create a pod ubuntu02 with image ubuntu and run the command sleep 3400 as user 1001.
111. Create a pod ubuntu03 with image ubuntu and add capabilities for SYS_TIME to each container. Run the command date -s '01JAN 2020 10:00:00 to verify if it is successful.
112. Taint one of the worker nodes in your cluster with the following property, mode=maintainance:NoSchedule. Create a pod nginx02 with image nginx:alpine and ensure the pod runs on the tainted node as above. Hint: You might want to use tolerations and nodeselectors both in case you have multiple worker nodes..
113. Create a pod box0 with image busybox and command sleep 30; touch /tmp/debug; sleep 30; rm /tmp/debug. The pod should not be ready until the file /tmp/debug is available in the pod. If the file doesn't exist, the pod must restart.
114. Create a pod nginx03 with image nginx, make sure the server is up and running every 10 seconds. The nginx server ideally takes 30 seconds to warm up so ensure that there are no false negatives when reporting the health of the pod.
        - Note: Nginx runs on port 80..
        - This is a multistage problem:
        - Create a deployment deploy01 with image nginx with port 80 exposed.
        - Update the deployment with image nginx:dev and make sure you record the execution of this action.
        - If the deployment in step b is unsuccessful, rollback the deployment to the previous state by setting any fields explicitly.
        - If the nginx deployment is in a healthy state, scale the deployment to run 3 replicas, also record this execution for audit-keeping.
        - Display the history of deployment deploy-01 and store it in file /opt/answers/31.txt.
115. Create a job that will roll a dice using image kodekloud/throw-dice. The image generates a random number between 1 and 6 and exits. It is a success only if it is a 6 else it is a failure. Check how many times it takes the job to trigger to get a successful outcome.
116. Create a job with the above image to generate 8 successful outcomes. Also, ensure that the job will attempt no more than 15 attempts and see if the job is successful. You can add an element of 3 parallel executions if required.
117. Create a Persistent Volume deploy-history which makes the storage available on each worker nodes at /tmp/deployment. Make sure it has the default provisioner of your cluster assigned. Label the Persistent Volume with audit: true, tier: middleware. The persistent volume must have a capacity of 2 GB.
118. Create a Persistent Volume persistent-data which uses a storage class name persistent and is of type hostPath which stores the data on /tmp/persistent on worker nodes. The persistent volume must have a capacity of 2 GB.
119. Create a Persistent Volume my-personal-data which uses a storage class name persistent and is of type hostPath which stores the data on /tmp/pii on worker nodes. The persistent volume must have a capacity of 2 GB. Since this will store personal data, make sure you can identify the persistent volume using the labels security: high, type: pii, audit: true.
120. Create a Persistent Volume Claim to bind to persistent volume which uses storage class persistent and requests 2 GB capacity.
121. Create a Persistent Volume Claim to bind to a PV which ensures that the personal and private data is secure. Ensure that this PVC will bind to a PV of type pii.
122. Create a PVC such that it will bind to a PV that is qualified for middleware applications.
123. Create a deployment deploy02 with image busybox, mount one of the PVC from above such that it will store logs in the /tmp/deployment directory. The containers of the deployment must:
        - Create a file in /tmp/deployment with the same name as the pod name with .txt extension.
        - Run the command i=0; while true; do; echo "$i $(date)" >> /tmp/deployment/<podname>.txt && sleep 60 ; done to the log file.
        Hint: You can use init-containers, environment variables to achieve this.
        - Ensure there are 5 replicas of the deployment.
        - Ensure you can see the log files created and populated with data in /tmp/deployment directory on the scheduled worker nodes.

124. Create a scheduled job such that it runs every minute. Use the image kodekloud/throw-dice to check the outcome.
125. Create a Persistent Volume deploy-history which makes the storage available on each worker nodes at /tmp/deployment. Make sure it has the default provisioner of your cluster assigned. Label the Persistent Volume with audit: true, tier: middleware. The persistent volume must have a capacity of 2 GB.
126. Create a Persistent Volume persistent-data which uses a storage class name persistent and is of type hostPath which stores the data on /tmp/persistent on worker nodes. The persistent volume must have a capacity of 2 GB.
127. Create a Persistent Volume my-personal-data which uses a storage class name persistent and is of type hostPath which stores the data on /tmp/pii on worker nodes. The persistent volume must have a capacity of 2 GB. Since this will store personal data, make sure you can identify the persistent volume using the labels security: high, type: pii, audit: true.
128. Create a Persistent Volume Claim to bind to persistent volume which uses storage class persistent and requests 2 GB capacity.
129. Create a Persistent Volume Claim to bind to a PV which ensures that the personal and private data is secure. Ensure that this PVC will bind to a PV of type pii.
130. Create a PVC such that it will bind to a PV that is qualified for middleware applications.
131. Create a deployment deploy02 with image busybox, mount one of the PVC from above such that it will store logs in the /tmp/deployment directory. The containers of the deployment must:
132. Create two deployments i.e. nginx04 and redis04 using images nginx and redis respectively with 3 replicas. Your goal is to ensure that:
        - each worker node must not have 2 or more nginx04 pods.
        - each worker node that has a nginx04 pod must have a redis04 pod scheduled on the same node.
        Hint: Use pod affinity and anti-affinity to ensure the above scneario.
133. Create 3 pods nginx05, redis05, and httpd05 with images nginx, redis, and httpd respectively. Attach a sidecar debug container of image busybox to each of them. The security team has enforced the application team to limit the communication between unnecessary pods. Ensure that only the following communication is allowed between pods:
        - Allow:
            - nginx05 <--> redis05
            - nginx05 <--> httpd05
        - Deny:
            - httpd05 <-/-> redis05
            - redis05 <-/-> rest of the world
            - nginx05 <-/-> the rest of the world
133. Identify a possible information flow in this system. Write the information flow in the format End-User::Pod1::Pod2::Pod3.
134. Create an application stack from this source link. Apply the network policy from this source link. Identify whether the network policy applied is correct or not. If not, update the desired network policy. If any network policy was updated, write the updated policy in /opt/44_netpol.yaml.
135. A developer started a pod calculus with image busybox which performs the calculation i=0; while true; do a=$(( i*i+i )); echo $a; i=$(( i+1 )); done. But later realized that this is not a reliable way to start a calculation-intensive pod. The developer decided to use a replicaset instead. But with the current pod running it would ruin all the calculations done so far. Can you help the developer to ensure that a replicaset can be created and the existing pod can become a part of this replicaset without any downtime. Store the manifest file of the replica set in /opt/45_rs.yaml and at the beginning add a comment describing in one line what strategy was implemented to achieve this.
136. Create a deployment deploy03 that uses image nginx:v2. The container name must be nginx. Check if the deployment is successful. Now delete the deployment. Get the events associated with the deployment deploy03 and pods created by the deployment and store them in a file located at /opt/answers/46_events.txt
137. Create a configmap devconfig that has configuration data as follows:
        - sdk.cfg:
        - path: /etc/sdk/
        - version: v2
        - auth: token
        - language: golang:1.15
138. Create a pod devbox with image busybox such that it projects the contents in devconfig. Project sdk.cfg on path /var/dev-sdk/config/sdk.cfg and language on path /var/dev-sdk/lang/golang/version/value.txt.
139. Create a pod pod01 with image busybox such that it requests for 100m of cpu and 50Mi of memory and the resources allocated are expandable to a limit of 200m of cpu and 250 Mi of memory. Try to create a pod using imperative command only.
        - stateful-set problem:
        - Create a stateful set for a middleware application named middleware that uses image nginx. Ensure that the stateful set has 3 replicas and has a persistent storage such that it uses PVC with a storage of 1 Gi mounted on worker nodes host path at /tmp/middleware/storage. Mount the storage on /var/www/html. Create a init-container in the stateful set with image busybox to create an index.html at /var/www/html. The contents of the index.html can be generated using the command echo "From middleware application" > /var/www/html/index.html. Expose the stateful set through a headless service middleware-svc.
        - Create a temporary pod with image busybox to check if you can access nginx service. Try accessing the service with the headless service and pod names (not ips).
        Create a deployment stressor with image polinux/stress. Execute the deployment with command stress and arguments --cpu 4 --timeout 180. Enable autoscaling for this deployment with a cpu limit of 75%. Get the autoscale management object and store it in /opt/answers/50_autoscale.yaml file
140. Create a busybox pod that runs the command "env" and save the output to "envpod" file
141. List pod logs named "frontend" and search for the pattern "started" and write it to a file "/opt/error- logs"
142. Create a pod that echo "hello world" and then exists. Have the pod deleted automatically when it's completed
143. Create a pod with environment variables as var1=value1.Check the environment variable in pod
144. Create a namespace called 'development' and a pod with image nginx called nginx on this namespace.
145. Create a nginx pod with label env=test in engineering namespace See the solution below.
146. Get list of all pods in all namespaces and write it to file "/opt/pods-list.yaml"
147. Create a pod with image nginx called nginx and allow traffic on port 80
148. Get list of all the pods showing name and namespace with a jsonpath expression.
149. Check the image version in pod without the describe command
150. List the nginx pod with custom columns POD_NAME and POD_STATUS
151. List all the pods sorted by name
152. Check the Image version of nginx-dev pod using jsonpath
153. Create a busybox pod and add "sleep 3600" command
154. Create an nginx pod and list the pod with different levels of verbosity
155. List the nginx pod with custom columns POD_NAME and POD_STATUS
156. Delete the pod without any delay (force delete)
157. Create a redis pod and expose it on port 6379
158. Create the nginx pod with version 1.17.4 and expose it on port 80
159. Change the Image version to 1.15-alpine for the pod you just created and verify the image version is updated.
160. Change the Image version back to 1.17.1 for the pod you just updated and observe the changes
161. Create a redis pod, and have it use a non-persistent storage Note: In exam, you will have access to kubernetes.io site, Refer : https://kubernetes.io/docs/tasks/configure-pod-container/configurevolume-storage/
162. Create a Pod with three busy box containers with commands "ls; sleep 3600;", "echo Hello World; sleep 3600;" and "echo this is the third container; sleep 3600" respectively and check the status
163. Check logs of each container that "busyboxpod-{1,2,3}"
164. List all the pods sorted by name
165. List all the pods sorted by created timestamp
166. List all the pods showing name and namespace with a json path expression
167. List "nginx-dev" and "nginx-prod" pod and delete those pods
168. Create a Pod with main container busybox and which executes this "while true; do echo `Hi I am from Main container' >> /var/log/index.html; sleep 5; done" and with sidecar container with nginx image which exposes on port 80. Use emptyDir Volume and mount this volume on path /var/log for busybox and on path /usr/share/nginx/html for nginx container. Verify both containers are running.
169. Exec into both containers and verify that main.txt exist and
170. Create an nginx pod and set an env value as 'var1=val1'. Check the env value existence within the pod
171. Create a pod with init container which create a file "test.txt" in "workdir" directory. Main container should check a file "test.txt" exists and execute sleep 9999 if the file exists.
172. Create a pod with init container which waits for a service called "myservice" to be created. Once init container completes, the myapp-container should start and print a message "The app is running" and sleep for 3600 seconds.
173. Create 5 nginx pods in which two of them is labeled env=prod and three of them is labeled env=dev
174. Get the pods with label env=dev and output the labels
175. Get the pods with labels env=dev and env=prod and output the labels as well
176. Get all the pods with label "env"
177. the label for one of the pod to env=uat and list all the pods to verify
178. list of all the nodes with labels
179. a nginx pod that will be deployed to node with the label "gpu=true"
180. the pod with name=webapp
181. a deployment called webapp with image nginx having 5 replicas in it, put the file in /tmp directory with named webapp.yaml
182. the list of pods of webapp deployment
183. the deployment from 5 replicas to 20 replicas and verify
184. the deployment rollout status
185. a deployment of webapp with image nginx:1.17.1 with container port 80 and verify the image version
186. the deployment with the image version 1.17.4 and verify
187. the rollout history and make sure everything is ok after the update
188. the deployment to the previous version 1.17.1 and verify Image has the previous version
189. the deployment with the image version 1.16.1 and verify the image and check the rollout history
190. the history of deployment
191. the deployment with the previous version and verify everything is Ok
192./Rollback deployment to specific revision "1"
193. the history of the specific revision of that deployment
194. the rollout of the deployment
195. the rollout of the deployment
196. the deployment to 5 replicas
197. down the deployment to 1 replica
198. the autoscaling to this deployment with minimum 10 and maximum 20 replicas and target CPU of 85% and verify hpa is created and replicas are increased to 10 from 1
199. the cluster by deleting deployment and hpa you just Created
200. Use curl to explore which Pods are present in the kube-system namespace
201. Managing Pod Networking
        - Create two services: myservice should be exposing port 9376 and forward to targetport 80, and mydb should be exposing port 9377 and forward to port 80.
        - Create a Pod that will start a busybox container that will sleep for 3600 seconds, but only if the aforesaid services are available.
        - To test that it is working, start the init container Pod before starting the services.
202. ManagingScheduling
203. Configure worker1.example.com in such a way that no new Pods will be scheduled on it, but existing Pods will not be moved away from it.
204. Mark worker1.example.com with the node label disk=ssd. Start a new nginx Pod that uses nodeAffinity to be scheduled on nodes that have the label disk=ssd set. Start the Pod and see what happens
205. Remove all restrictions from worker1.example.com
