# Deploying iLender Application

## 1. Update Humio properties

Update `humioUrl` and `humioToken` properties in the file `./yaml/20-deployable-common.yaml`

```
  humioUrl: http://1.1.1.1:8080/api/v1/ingest/humio-unstructured
  humioToken: 
```

[Refer ...](../81-installing-humio-on-openshift)



## 2. Apply the yaml

Apply the yaml in the Openshift or Kubernetes (OCP/IKS) clusters

```
kubectl apply -f ./yaml
```

## 3. Access the app

App is installed in the `ilender-ns` namespace.

![ilender](./images/iLender-Login.png)


### 3.1 User Id and Password

```
sam/sam
sandy/sandy
```

### 3.2 URLs

You can access the application using the `EXTERNAL-IP` from node and `NodePort` from svc.

#### Get EXTERNAL-IP

Run the below command to get `EXTERNAL-IP`

```
kubectl get nodes -o wide
```

Output could be like this.

```
Jeyas-MacBook-Pro:frontuiservice jeyagandhi$ kubectl get nodes -o wide
NAME             STATUS   ROLES    AGE   VERSION       INTERNAL-IP      EXTERNAL-IP       OS-IMAGE             KERNEL-VERSION       CONTAINER-RUNTIME
10.241.253.157   Ready    <none>   26d   v1.20.7+IKS   10.241.253.157   1.1.1.1   Ubuntu 18.04.5 LTS   4.15.0-144-generic   containerd://1.4.6
10.241.253.189   Ready    <none>   26d   v1.20.7+IKS   10.241.253.189   1.2.3.5   Ubuntu 18.04.5 LTS   4.15.0-144-generic   containerd://1.4.6
```

#### Get NodePort

Run the below command to get `NodePort`of the svc

```
kubectl get svc
```

Output could be like this.

```
Jeyas-MacBook-Pro:frontuiservice jeyagandhi$ kubectl get svc
NAME                      TYPE           CLUSTER-IP       EXTERNAL-IP     PORT(S)          AGE
ilender-bigbank           ClusterIP   172.21.165.179   1.1.1.1       9090:30598/TCP   10d
ilender-creditscore       NodePort       172.21.55.156    <none>          9090:30601/TCP   10d
ilender-customerprofile   ClusterIP   172.21.145.229   1.1.1.1   9090:32751/TCP   10d
ilender-frontweb          NodePort       172.21.44.159    <none>          9090:30600/TCP   10d
ilender-greatbank         ClusterIP   172.21.84.144    <pending>       9090:31622/TCP   10d
ilender-loan              ClusterIP   172.21.161.226   1.1.1.1   9090:30301/TCP   10d
ilender-loanprocessor     ClusterIP   172.21.82.15     1.1.1.1   9090:30880/TCP   10d
ilender-openbanking       ClusterIP   172.21.235.41    1.1.1.1   9090:31331/TCP   10d
ilender-user              ClusterIP   172.21.43.214    1.1.1.1       9090:32427/TCP   10d
```

#### Get URLs

The URL would be of this format.

```
http://< EXTERNAL-IP >: < NodePort >
```

Here are the 2 urls that we need.

```
App URL  (ilender-frontweb) : http://1.1.1.1:30600
CreditScore Service URL  (ilender-creditscore) : http://1.1.1.1:30601
```