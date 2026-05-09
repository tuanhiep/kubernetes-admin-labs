# API Groups
  - Take me to [Video Tutorial](https://kodekloud.com/topic/api-groups/)
  
In this section, we will take a look at API Groups in kubernetes

## To return version and list pods via API's 

 ![api3](../../images/api3.png)
 
- The kubernetes API is grouped into multiple such groups based on their purpose. Such as one for **`APIs`**, one for **`healthz`**, **`metrics`** and **`logs`** etc.

  ![api4](../../images/api4.png)
 
## API and APIs
- These APIs are catagorized into two.
  - The core group - Where all the functionality exists
    
    ![api5](../../images/api5.png)
 
  - The Named group - More organized and going forward all the newer features are going to be made available to these named groups.
  
    ![api6](../../images/api6.png)
    
- To list all the api groups

  ![api7](../../images/api7.png)
  
## Note on accessing the kube-apiserver
- You have to authenticate by passing the certificate files.

  ![api8](../../images/api8.png)
  
- An alternate is to start a **`kubeproxy`** client
  
  ![api9](../../images/api9.png)
  
## kube proxy vs kubectl proxy
 
  ![kp](../../images/kp.png)
  
## Key Takeaways

  ![api10](../../images/api10.png)

#### K8s Reference Docs
- https://kubernetes.io/docs/concepts/overview/kubernetes-api/
- https://kubernetes.io/docs/reference/using-api/api-concepts/
- https://kubernetes.io/docs/tasks/extend-kubernetes/http-proxy-access-api/
