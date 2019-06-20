---
redirect_from:
  - "create-an-azure-resource-group"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Create_an_Azure_Resource_Group.ipynb
kernel_name: python3
has_widgets: false
title: 'Create An Azure Resource Group'
prev_page:
  url: /Create_AKS_Cluster_for_Linux
  title: 'Create Aks Cluster For Linux'
next_page:
  url: /Create_SQL_Server_Big_Data_Cluster
  title: 'Create Sql Server Big Data Cluster'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Create an Azure Resource Group**


We will create an Azure resource group to hold all of the subsequent

things we are going to create (such as a Kubernetes cluster and several

Persistent Volumes)

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
if not skip_group_create:

    cmd = f'az group create --name {azure_resource_group} --location {azure_region}'

    error_check()

else:

    print('SKIPPED: az group create')
```
</div>

</div>
