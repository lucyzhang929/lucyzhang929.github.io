---
redirect_from:
  - "delete-azure-resource-group"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Delete_Azure_Resource_Group.ipynb
kernel_name: python3
has_widgets: false
title: 'Delete Azure Resource Group'
prev_page:
  url: /Delete_AKS_Cluster
  title: 'Delete Aks Cluster'
next_page:
  url: /Install_Azure_CLI
  title: 'Install Azure Cli'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Delete Azure Resource Group** (from previous run of this Notebook)


If running this notebook more than once with the same parameters, you’ll

need to delete the previously created resource group.

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
if not skip_group_delete:

    cmd = f'az group delete --name {azure_resource_group} -y'

    error_check()

else:

    print('SKIPPED: az group delete')
```
</div>

</div>
