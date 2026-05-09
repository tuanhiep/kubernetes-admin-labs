# Network Policies
  - Take me to [Video Tutorials](https://kodekloud.com/topic/network-policies-3/)
  
#### Trafic flowing through a webserver serving frontend to users an app server serving backend API and a database server

  ![traffic](../../images/traffic.png)
  
- There are two types of traffic
  - Ingress
  - Egress
  
   ![ing1](../../images/ing1.png)
  
   ![ing2](../../images/ing2.png)
  
## Network Security

  ![nsec](../../images/nsec.png)
  
## Network Policy

  ![npol](../../images/npol.png)
  
  ![npol1](../../images/npol1.png)
  
## Network Policy Selectors
  
  ![npolsec](../../images/npolsec.png)
  
## Network Policy Rules

  ![npol2](../../images/npol2.png)
  
## Create network policy
 
- To create a network policy
  ```
  apiVersion: networking.k8s.io/v1
  kind: NetworkPolicy
  metadata:
   name: db-policy
  spec:
    podSelector:
      matchLabels:
        role: db
    policyTypes:
    - Ingress
    ingress:
    - from:
      - podSelector:
          matchLabels:
            role: api-pod
      ports:
      - protocol: TCP
        port: 3306
  ```
  
  ```
  $ kubectl create -f policy-definition.yaml
  ```
  
 ![npol3](../../images/npol3.png)
 
 ![npol4](../../images/npol4.png)
  
## Note
 
 ![note1](../../images/note1.png)
 
#### Additional lecture on [Developing Networking Policies](https://kodekloud.com/topic/developing-network-policies/)

#### K8s Reference Docs
- https://kubernetes.io/docs/concepts/services-networking/network-policies/
- https://kubernetes.io/docs/tasks/administer-cluster/declare-network-policy/
 
  
  
  
  
