# Kubernetes Basics-1: Concepts & Architecture
Container orchestrationfor automated, portable and scalable container management with some managent capabilities.<br>
Uses YAML or JSON files for configuration to
- Automate rollout and rollbacks
- Storage orchestration
- Scaling
- Automated bin packing
- Secret and configuration management
- Batch execution
- Self-healing (expose only healthy, kill/reschedule/restart failing ones)
- Load balancing
and many usages in its ecosystem.<br>

**Dos & Don'ts**: [here](https://github.com/PsyDak-Meng/Online_Certificates/blob/main/IBM_Containers_Course/Kubernetes%20Antipatterns.pdf)


 ## Concepts
 ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/8003157b-e3f7-4cae-a40c-ef80bdf22c41)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/bcff700b-261d-4171-af81-5e3fc33e9681)

 ## Architecture
 Developers use Kubernetes API server to control the Kubernetes control plane that manages the Kubernetes worker nodes provided by the cloud provider.

 ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/527d2f44-f3f1-471b-a650-ecfabcbec6eb)

![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/2fd3f439-fba8-422b-9480-7b8622c5de8b)

### Kubernetes API Server
Cube API servers scale horizontally by deploying more instance to balance traffic.

 ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/aabe32e1-5ee5-4080-8b6f-aeb22cddc04a)

- **etcd**: Highly available, distributed key-value store containing all cluster data, deployment configuration data (state & meta data). Accessible in a common location;
- **kubernetes scheduler**: Determine where workload should optimally run in the cluster, assigning pods (set of containers) to nodes (machines);
- **kubernete-controller manager**: Monitor and ensure cluster state mayches desired state;
- **cloud-controller manager**: Link clusters into cloud provider's API for interactions.

### Kublet & Proxy
**Kublet**: Assert pods and containers running healthily for the control plane.<br>
**Proxy**: Network proxy that maintaines network rules for communicatinos with pods.<br>
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/5055e3e8-0430-4691-98f1-ea4194e27b76)

### Container runtime
Downloads images and runs containers. Kubernetes implemented interface so cmponents are pluggable.
