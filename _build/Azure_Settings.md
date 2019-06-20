---
redirect_from:
  - "azure-settings"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Azure_Settings.ipynb
kernel_name: python3
has_widgets: false
title: 'Azure Settings'
prev_page:
  url: 
  title: ''
next_page:
  url: /Big_Data_Cluster_Settings
  title: 'Big Data Cluster Settings'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# Azure Settings

azure_subscription_id = "" #If this value is blank, this notebook uses the 'default' subscription ID for your Azure account.

azure_vm_size = "Standard_E4s_v3" #Example: Standard_E4s_v3

azure_vm_count = int(4) #Example: int(4)

azure_region = "eastus" #Example: eastus

mssql_cluster_name = ""

azure_resource_group = 'aks-'+mssql_cluster_name
```
</div>

</div>

### **Azure Settings**
#### Subscription ID
- If you don't want your default subscription, then please visit here to use the subscription you would like to use: https://ms.portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade



#### VM Sizes
- If you don't want to use the default VM Size, then please visit here to use the VM Size you would like to use: https://docs.microsoft.com/en-us/azure/virtual-machines/windows/sizes

 

#### Regions
- If you don't want default VM Size, then please visit here to use the VM Size you would like to use: https://azure.microsoft.com/en-us/global-infrastructure/services/?products=kubernetes-service

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print("Azure VM Size:",azure_vm_size)

print("Azure VM Count:",azure_vm_count)

print("Azure Region:",azure_region)

print("Azure Resource Group:",azure_resource_group)
```
</div>

</div>
