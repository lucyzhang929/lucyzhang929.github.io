---
redirect_from:
  - "uninstall-az-cli"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Uninstall_AZ_CLI.ipynb
kernel_name: python3
has_widgets: false
title: 'Uninstall Az Cli'
prev_page:
  url: /Show_Big_Data_Cluster_Endpoints
  title: 'Show Big Data Cluster Endpoints'
next_page:
  url: /Uninstall_MSSQLCTL
  title: 'Uninstall Mssqlctl'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### Uninstall AZ CLI

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import sys



if not skip_azcli_uninstall:

    cmd = f'{sys.executable} -m pip uninstall azure-cli --yes'

    error_check()

else:

    print('SKIPPED: Uninstall AZ CLI')
```
</div>

</div>
