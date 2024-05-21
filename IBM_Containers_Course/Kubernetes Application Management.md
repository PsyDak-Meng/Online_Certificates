# Kubernetes Application Management

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
Avoid hard-coding configuration variables. ConfigMaps is an API object that stores non-confidential data in key-value pair without encryption.

