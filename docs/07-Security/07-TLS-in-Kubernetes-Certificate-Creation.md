# TLS in kubernetes - Certificate Creation
  - Take me to [Video Tutorial](https://kodekloud.com/topic/tls-in-kubernetes-certificate-creation/)
  
In this section, we will take a look at TLS certificate creation in kubernetes

## Generate Certificates
- There are different tools available such as easyrsa, openssl or cfssl etc. or many others for generating certificates.

## Certificate Authority (CA)

- Generate Keys
  ```
  $ openssl genrsa -out ca.key 2048
  ```
- Generate CSR
  ```
  $ openssl req -new -key ca.key -subj "/CN=KUBERNETES-CA" -out ca.csr
  ```
- Sign certificates
  ```
  $ openssl x509 -req -in ca.csr -signkey ca.key -out ca.crt
  ```
 
 ![ca1](../../images/ca1.png)
 
## Generating Client Certificates

#### Admin User Certificates

- Generate Keys
  ```
  $ openssl genrsa -out admin.key 2048
  ```
- Generate CSR
  ```
  $ openssl req -new -key admin.key -subj "/CN=kube-admin" -out admin.csr
  ```
- Sign certificates
  ```
  $ openssl x509 -req -in admin.csr -CA ca.crt -CAkey ca.key -out admin.crt
  ```
  
  ![ca2](../../images/ca2.png)
  
- Certificate with admin privilages
  ```
  $ openssl req -new -key admin.key -subj "/CN=kube-admin/O=system:masters" -out admin.csr
  ```
  
#### We follow the same procedure to generate client certificate for all other components that access the kube-apiserver.

  ![crt1](../../images/crt1.png)
  
  ![crt2](../../images/crt2.png)
  
  ![crt3](../../images/crt3.png)
   
  ![crt4](../../images/crt4.png)
  
## Generating Server Certificates

## ETCD Server certificate

  ![etc1](../../images/etc1.png)
  
  ![etc2](../../images/etc2.png)
  
## Kube-apiserver certificate

  ![api1](../../images/api1.png)
  
  ![api2](../../images/api2.png)
  
## Kubectl Nodes (Server Cert)

   ![kctl1](../../images/kctl1.png)
   
## Kubectl Nodes (Client Cert)

   ![kctl2](../../images/kctl2.png)
   
   
   
  
  

  

  


  
  
  
  
 
