---
redirect_from:
  - "install-azure-cli"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Install_Azure_CLI.ipynb
kernel_name: python3
has_widgets: false
title: 'Install Azure Cli'
prev_page:
  url: /Delete_Azure_Resource_Group
  title: 'Delete Azure Resource Group'
next_page:
  url: /Install_Kubernetes_CLI_for_Linux
  title: 'Install Kubernetes Cli For Linux'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### Install Azure CLI

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import sys



if not skip_azcli_install:

    force_install_option='--force-install' if azcli_use_force_install_option else ''

    user_install_option='--user' if azcli_use_user_install_option else ''



    cmd = f'{sys.executable} -m pip install azure-cli {force_install_option} {user_install_option}'

    error_check()

else:

  print('SKIPPED: Install AZ CLI')
```
</div>

</div>
