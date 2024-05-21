# Kubernetes Application Management

## kubectl Cheatsheet
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/6a0d5ae6-37ec-4180-83cb-66d2f7dd569e)



## Replica Set
- **Deployments --> ReplicaSet --> pod labels --> pods**
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/df422b9a-94cb-42d0-b8b4-43c576be94a8)
- Create by YAML: **create --> get --> scale deploy --> get --> delete**
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/24c935af-364c-4fb8-b589-ad40ee7dd7d5)

![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/5948ae81-e9d2-4aa8-9761-0b2e969299c1)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/07359595-fc55-41d8-a5e6-be9b3b8918c7)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/5cc781cf-be62-4e6c-9a10-cf31c66368cb)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/cc10233e-364f-442a-8772-e5844ef4ea21)


## Autoscaling (Backend in ReplcaSet)
1. Usually HPA, combos good for cost and syability;
2. Dont't use VPA+HPA on memory and cpu;
3. CA for beyond HPA & VPA.

- Horizontal Pod Autoscaler (adjust number of pods through ex. deployment)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/c8184cc8-2650-43e3-94ce-adc70f9e8eea)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/3dd5a51e-1a60-4126-bc4e-3ac286baf666)

- Vertical Pod Autoscaler (**scale up--adding recourse to a machine**; adjust resource requests and limits of container by adjusting resouce size or speed of pods)

- Cluster Autoscaler (adjust the number of nodes)

 ## Rolling Updates
 Automated updates occuring on a scheduled basis.
 ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d5b83483-b21b-4218-a9c0-8b437e6376a8)
**Update and push new Docker image --> rollout status --> rollout undo --> get pods**
- All-at-once (downtime)
- One-at-a time (staggered so not interrupted)

## ConfigMaps and Secrets
### ConfigMaps
Avoid hard-coding configuration variables. ConfigMaps is an API object that stores non-confidential data in key-value pair without encryption.
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/fc8d443e-3ac8-453a-ae88-881d83dc3d4b)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/3a264bfc-5885-4625-b81f-ed8e2e2a6339)

- String literal
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d022ddc7-600f-4357-a6c6-c7ac6f471eea)
 
- ConfigMap properties file
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f8b61329-bd40-4ab3-89b7-71b36637c8b7)

- YAML
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/523b8413-0561-4350-98fc-7a2ed7308836)

### Secrets
- String literal
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f5e0b53c-590c-4bf5-9023-e847efdb66d1)
print out secret: ```kubectl get secret api-cards -o YAML```

- environmental variable
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/f5b59f88-8647-4141-9051-271c979b7237)

- volume mounts
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/c5fc45c7-58ad-4d61-9e52-5c60a6904c3a)


## Service Binding
Consumes external service using volumeMounts and volumes by binding the application to a deployment.<br>
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/9e32ce16-a31e-44d2-a30d-a6990c6b000c)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/02a7879d-eb6a-404d-9d56-7f8f9d0b91a5)
Verify Secret stored in Kubernetes Cluster: ```kubectl get secrets --namespace=default```
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/6a0fd12c-b056-4beb-b6a0-7f76c5872179)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/61dbb8d2-74bf-4bae-8cd7-8cbbe34e143e)


## Hands-on Lab
See the lab [here.](https://labs.cognitiveclass.ai/v2/tools/cloud-ide-kubernetes?ulid=ulid-cb959be16e9c5b58cc02a6c15e180c60c70529f2)


