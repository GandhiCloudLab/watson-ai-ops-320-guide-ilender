# Installing Watson AIOps AI-Manager on ROKS

This document explains about Installing Watson AIOps AI-Manager on ROKS.

This document is based on the IBM Documentation https://www.ibm.com/docs/en/cloud-paks/cloud-pak-watson-aiops/3.2.0?topic=manager-starter-installation


### 1. Installation Script 

Installation script is available in [files/10-install-ai-manager](./files/10-install-ai-manager.sh).


### 2, Update ENTITLEMENT_KEY  

1. Get `IBM entitlement key` from https://myibm.ibm.com/products-services/containerlibrary

<img src="images/image0.png">

2. Replace the value of the `ENTITLEMENT_KEY` variable in `files/00-config.sh`

```
#!/bin/bash

## Entitlement key
export ENTITLEMENT_KEY=ABCD

## Namespace where WAIOps to be isnstalled.
export NAMESPACE=cp4waiops
```

### 3. Install WAIOPS AI-Manager

Here are the steps to install AI-Manager

#### 3.1. Login into OpenShift

Login into OpenShift cluster where you want to install AI-Manager.

```
oc login ......
```

#### 3.2. Goto the files folder

Run the below command

```
cd 03-install-ai-manager/files
```

#### 3.3. Run the install script

Run the below command to start the install

```
sh 10-install-ai-manager.sh
```

- It would take around 1hr to complete the istallation. 
- By default the installation is done on the namespace `cp4waiops`
- Keep checking the logs for the status. 
- The same script can be run again and again if the install stopped for any reason.

#### 3.4. Output
 
The installation would be completed and the output could be like this.

```
=====================================================================================================
URL : https://cpd-cp4waiops.aaaaaaaa.ams03.containers.appdomain.cloud
USER: admin
PASSWORD: 
=====================================================================================================

```

You can use this to login into the WAIOps Console.

