# Kubernetes Basics: Kubectl (CLI)

## Command structure
```
kubectl [command][type][name][flags]
```
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/0df790fd-ea91-4643-8f3f-70a34a563841)

- Imperatiev cmd
- Imperative object configuration
- Declarative object configuration
  
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/7feef941-18a5-4965-8fd5-df92fed3a0a2)
If A ran imperative cmd, B has to ask A for his cmd or else cannot run the same application. 
<br><br><br>
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/4a8a73cd-9f72-4f35-8bab-abd14d2add97)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/b72e8ddb-f6e0-4ce0-9eaa-f6868467ef6b)
If A ran cmd outside imperative configuration object, B cannot run the same application without updated configuration because it is not shared, so imperative configuration has to specify all necessary cmd.
<br><br><br>
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/eb0bad71-47df-433a-8b2d-eb13278c61ed)
Stores updates of configuration state automatically, and is shared across developers.



## Common Commands
find all commands [here](Kubernetes.io)<br>
### Workflow
1. **config**: config to get appropriate cluster<br>
  1.1 get cluster information:<br>
   ex: kubectl config get-clusters<br><br>
  1.2 get contexts(access params):<br>
   ex: kubectl config get-contexts<br><br>
  1.3 list pods: <br>
  ex: kubectl get pods<br><br>
3. **create pod**<br>
   2.1 set namespace as environmental variable: <br>
   export MY_NAMESPACE=sn-labs-$USERNAME<br><br><br>
   
   2.2.1.1 **(Imperative cmd)** build & push image: <br>
   ex: docker build -t us.icr.io/$MY_NAMESPACE/hello-world:1 . && docker push us.icr.io/$MY_NAMESPACE/hello-world:1<br>
   2.2.1.2 run image as container: <br>
   ex: kubectl run hello-world --image us.icr.io/$MY_NAMESPACE/hello-world:1 --overrides='{"spec":{"template":{"spec":{"imagePullSecrets":[{"name":"icr"}]}}}}'<br><br>
   
   2.2.2 **(Imperative object config)** create from .yaml<br>
   ex: kubectl create -f hello-world-create.yaml<br><br>

   2.2.3 **(Declarative cmd)** creating deployment: <br>
   ex: kubectl apply -f hello-world-apply.yaml<br><br>
   
   
   2.3.1 check pods/deployments for running container (-more detail): <br>
   kuberctl get pods/deployments -o wide<br><br>
   2.3.2 describe pod (memory/CPU limits): <br>
   ex: kubectl describe pod hello-world<br><br>

   2.4.1 expose to internet for load balancing:<br>
   ex: kubectl expose deployment/hello-world<br><br>
   2.4.2 check services:
   ex: kubectl get services<br><br>
   2.4.3 access ClusterIP from proxy to be within cluster:<br>
   kubectl proxy<br>
   ping for response: curl -L localhost:8001/api/v1/namespaces/sn-labs-$USERNAME/services/hello-world/proxy<br><br>
   
   2.5 delete pod/deployment: <br>
   ex: kubectl delete pod hello-world<br>
   kubectl delete deployment/hello-world service/hello-world<br>
   
   
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/8c39533c-7e51-455a-9815-f96f3ae63a2d)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/37c9b474-3efb-4c3f-a2e8-873ec8ecc342)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f513bac1-e33f-4704-ae80-ef4da8fe17d5)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f0582f06-3684-4dea-8636-301176fbbe3d)

## Lab
Find the hand-on lab [here.](https://labs.cognitiveclass.ai/v2/tools/cloud-ide-kubernetes?ulid=ulid-ef5443811ce77e02c7bb8c432d1738b1173c7d76)
