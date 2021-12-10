# Demo Script

## 1. Update config.sh

#### 1. OCP Server

Update `OCP_SERVER`

#### 2. OCP Token

1. Create OCP Token using the link [here](https://github.com/ibm-gsi-ecosystem/watson-ai-ops-guide/tree/master/601-getting-cluster-access-token2) 

2. Update the below property.

```
OCP_TOKEN=""
```

#### 3. IBM Cloud API Key

1. Create IBM Cloud API Key for accessing IKS Cluster using the link [here](https://github.com/ibm-gsi-ecosystem/watson-ai-ops-guide/tree/master/602-accessing-iks-cluster-using-api-key) 

2. Update the below property.

```
IBMCLOUD_API_KEY=
```

#### 4. IKS Cluster Id

Update the iks cluster id in the below property.

```
IKS_CLUSTER_ID=csadfdasd0ohsnstmnnqg
```

#### 5. Application Url

Update the bookinfo app url

```
APP_URL=http://1.1.1.1:31010/productpage?u=normal
```

#### 6. Namespace

Update the NAMESAPCE property, with namespace where the aiops is installed.

```
NAMESAPCE=aiops31
```

