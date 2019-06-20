---
redirect_from:
  - "delete-aks-cluster"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Delete_AKS_Cluster.ipynb
kernel_name: python3
has_widgets: false
title: 'Delete Aks Cluster'
prev_page:
  url: /Default_Settings_for_Linux
  title: 'Default Settings For Linux'
next_page:
  url: /Delete_Azure_Resource_Group
  title: 'Delete Azure Resource Group'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Delete AKS Cluster** (from previous run of this Notebook)
If running this notebook more than once with the same parameters, you’ll

need to delete the previously created AKS Cluster.

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'az aks delete --name {aks_cluster_name} --resource-group {azure_resource_group} -y'

error_check()
```
</div>

</div>
