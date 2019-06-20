---
redirect_from:
  - "create-aks-cluster-for-linux"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Create_AKS_Cluster_for_Linux.ipynb
kernel_name: python3
has_widgets: false
title: 'Create Aks Cluster For Linux'
prev_page:
  url: /Big_Data_Cluster_Settings
  title: 'Big Data Cluster Settings'
next_page:
  url: /Create_an_Azure_Resource_Group
  title: 'Create An Azure Resource Group'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Create AKS cluster for Linux**


We will create an AKS Cluster with the settings provided.

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import json



if not skip_aks_create:



    # If specific version of kubernetes has been asked for, pass in the --kubernetes-version option

    #

    if aks_kubernetes_version != "":

        kubernetes_version_option="--kubernetes-version {aks_kubernetes_version}"

    else:

        kubernetes_version_option = ""

    input = !az ad sp create-for-rbac --skip-assignment

    input = ''.join(input)

    results = json.loads(input)

    appID = results['appId']

    password = results['password']

    cmd = f'az aks create --name {aks_cluster_name} --resource-group {azure_resource_group} --generate-ssh-keys --node-vm-size {azure_vm_size} --node-count {azure_vm_count} {kubernetes_version_option}' 

    #cmd = f'az aks create --name {aks_cluster_name} --resource-group {azure_resource_group} --service-principal {appID} --client-secret {password} --generate-ssh-keys --node-vm-size {azure_vm_size} --node-count {azure_vm_count} {kubernetes_version_option}' 

    error_check()

else:

    print('SKIPPED: az aks create')
```
</div>

</div>

### Show AKS cluster details

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'az aks show -g {azure_resource_group} -n {aks_cluster_name}'

error_check()
```
</div>

</div>

### Get AKS credentials

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'az aks get-credentials --resource-group {azure_resource_group} --name {aks_cluster_name} --admin --overwrite-existing'

error_check()
```
</div>

</div>

### Enable AKS monitoring

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
if not skip_aks_create:

    if aks_enable_monitoring:

        cmd = f'az aks enable-addons -a monitoring -n {aks_cluster_name} -g {azure_resource_group}'

        error_check()

    else:

        print('SKIPPED: az aks enable-addons -a monitoring')
```
</div>

</div>

### Show the Kubernetes Nodes

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'{kubectl_binary_location} get nodes'

error_check()
```
</div>

</div>

### Show the Kubernetes Systems Pods


Show the BDC pods. You can run to monitoring progress while waiting for

the ‘mssqlctl bdc create’ above to complete

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'{kubectl_binary_location} get pods --all-namespaces'

error_check()
```
</div>

</div>

### List the MSSQLCTL configuration profiles

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import os



os.environ["ACCEPT_EULA"] = 'yes'



# List the configuration profiles available

# mssqlctl_binary_location = mssqlctl

cmd = f'mssqlctl bdc config list'

!{cmd}



#!mssqlctl bdc config list
```
</div>

</div>

### Create a MSSQLCTL configuration file

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import os

# Create (init) a configuration file

#

cmd = f'mssqlctl bdc config init --source {mssqlctl_configuration_profile} --target {mssqlctl_configuration_file} --force'

error_check()



# Set the 'big data cluster' name

#

jsonPath = '"metadata.name=''{0}''"'.format(mssql_cluster_name)

cmd = f'mssqlctl bdc config section set -c {mssqlctl_configuration_file} -j {jsonPath}'

error_check()

# Set the docker registry

#

jsonPath = '"spec.controlPlane.spec.docker.registry=''{0}''"'.format(docker_registry)

cmd = f'mssqlctl bdc config section set -c {mssqlctl_configuration_file} -j {jsonPath}'

error_check()



# Set the docker repository

#

jsonPath = '"spec.controlPlane.spec.docker.repository=''{0}''"'.format(docker_repository)

cmd = f'mssqlctl bdc config section set -c {mssqlctl_configuration_file} -j {jsonPath}'

error_check()
```
</div>

</div>

### Delete a previously created SQL Server big data cluster

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
if include_bdc_delete:



    os.environ["CONTROLLER_USERNAME"] = bdc_controller_username

    os.environ["CONTROLLER_PASSWORD"] = bdc_controller_password



    cmd = f'mssqlctl bdc delete -n {mssql_cluster_name} --force'

    error_check()

else:

    print('SKIPPING: mssqlctl bdc delete')
```
</div>

</div>
