# OpenShift
Container orchestration enterprise platform running on Kubernetes clusters, with object data stored in the etcd key-value store.

**Cheat Sheet: OpenShift CLI**
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/353f759c-4f62-4972-a0e2-f63d267cdd04)


## Structure
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/48873890-22db-4efc-9071-daff9e63f383)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/e58d830f-3818-4710-a245-bde9da837fd9)


## OpenShift CLI (oc)
Works directly with the source code.

## Build (BuildConfig)
### Input sources
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/54072ee5-89f0-4fac-9284-e09e7e9ff955)
### ImgaeStream
1. Abstraction for creating and updating container images reliazed by pointer. <br>
2. Can store source image in internal/external registies or other ImageStreams. <br>
3. **Use ImageStream tag insead of hard coding the image url,**so that if image url changes you only have to change the pointer in ImageStream. 
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/06ddc34a-f090-4efb-bb03-e0fcb8e43603)
### Build Trigeers (automated build)
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/621747d1-e80f-4a43-8667-d9e843b794d5)

### Strategies
- Source to Image (S2I): no Dockerfile, have predifined builder images
  ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/2be554e9-e6b3-407e-9956-258591de76a6)

- Docker
  ![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/908acb22-f10c-478d-8afe-0313d7920848)

- Custom: need administrative availability <br>
  Use Docker images containing logic to transform inputs into expected outputs. Creates additional objects like JAR files and CI/CD deployment for uni/integration tests.
  
### Example
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/363638b1-35a2-466f-a1de-335a661e4eb1)



## Operators
An extension of Kubernetes API running in a pod to **automate long-running cluster tasks (package, deploy, manage, testing, delivery)** as a custom controller.
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/6affb612-a686-4b9f-8d97-a06ca0f60feb)

- Custom resource definition (CRD): <br>
Store and retreive objects in the Kuebrnetes API within clusters, accessible using kubectl.
- Custom controllers (change cluster actual state): <br>
CRD + contollers = new decalrative Kubernetes API
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/b3bba671-6c72-4571-8018-9d8bfdf54d50)
- Operator Framework
  - Operator SDK
  - Operator LifeCycle Manager
  - Operator Registry
  - Operator Hub
 
### Example
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/e8985d81-aca4-415e-9cb5-e0cd1d222b45)



## Istio (service mesh)
Security, Traffic econtrol, Policies, Observability without adding to code.
### With Kubernetes
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/23b2b7c2-aaeb-47f6-898b-495253441322)

### With Microservices
![image](https://github.com/PsyDak-Meng/Online_Certificates/assets/105434864/d22163fe-ba25-41ca-b46e-bac21eaffa48)


