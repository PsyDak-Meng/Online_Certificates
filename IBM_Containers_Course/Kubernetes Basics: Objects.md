# Kubernetes Basics: Objects

## Kubernete Objects
Kubernetes objects include Namespaces, Pods, ReplicaSets, Deployments, and Services. <br><br>
1. = Object spec (user desired state) + Status (Kubernetes current state);
2. **Labels**: Key/value pairs for identificaiton, not unique to be used in grouping with label selectors;
3. **Namespaces**: Isolating mechanism for groups within a single cluster, unique object names within the namespace;
4. **Pod**: Process / running instance with 1 or more containers, scale horizontally as ReplicaSets by replicating pod services using YAML files;

   ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/6942537a-bd45-4fd1-9932-3d70471f5024)
     ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/5a0a9543-c407-4d52-a5d3-5fb440b0941a)
5. **Deployment**: Provides updates for pods and replicasets and runs multiple replicas of an application.<br>
For stateless applications and the update will trigger a rollout (change only on the new version).
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f55d559c-a1a4-4b3e-b9a0-e13135791bd8)

6. **Services**
REST object, abstractiuon for a set of pods in a cluster. Needed for changing IP addresses in volatile pods, they track changes and expose single IP address or DNS name. Targets a set of pods with selectors.<br>
**4 types**:
   - ClusterIP (interservice comminicatino within cluster),
   - NodePort (route incoming requests automatically to the ClusterIP)
   - Load Balancer (creates NodePort and ClusterIP automatically)
   - External Name (external storage, allow different namespace talk to each other)
- Load balancing;
- Provide policies: protocols (TCP, UDP,etc), incoming and target ports
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/05f4142b-9653-47d8-8fc5-5f2be8ca12ca)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/65ce72a2-37e9-41c3-acaa-6c34a36645fa)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/7e3298c0-6755-4c53-9efe-da1d0e6574d2)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d78c0077-0b0a-4bd2-9fa7-019621408503)

6. **Ingress** <br>
Manages external access to cluster services (objects & controller). HTTP and HTTPS traffic routing.
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/3d45b53d-5c6d-4967-8385-b1c26ab61c68)

8. **Daemon Set**<br>
Ensures at least one instance of the pod on all your nodes.
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d7c349de-3c9c-43a1-a7ac-07ae36e4834c)

9. **StatefuilSet**<br>
Manages stateful applicatipns' pod deployment and scaling.
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/c5d048c8-7588-4902-bfc1-f5452121ca31)

10. **Job**
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/5c51c946-73a8-4447-bfbb-edbd0193ea87)
