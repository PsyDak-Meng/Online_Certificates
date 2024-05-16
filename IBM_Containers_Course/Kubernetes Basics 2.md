# Kubernetes Basics-2: Objects

## Kubernete Objects
1. = Object spec (user desired state) + Status (Kubernetes current state);
2. **Labels**: Key/value pairs for identificaiton, not unique to be used in grouping with label selectors;
3. **Namespaces**: Isolating mechanism for groups within a single cluster, unique object names within the namespace;
4. **Pod**: Process / running instance with 1 or more containers, scale horizontally as ReplicaSets by replicating pod services using YAML files;

   ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/6942537a-bd45-4fd1-9932-3d70471f5024)
   ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/6942537a-bd45-4fd1-9932-3d70471f5024)
     ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/5a0a9543-c407-4d52-a5d3-5fb440b0941a)
5. **Deployment**: Provides updates for pods and replicasets and runs multiple replicas of an application.<br>
For stateless applications and the update will trigger a rollout (change only on the new version).
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f55d559c-a1a4-4b3e-b9a0-e13135791bd8)
