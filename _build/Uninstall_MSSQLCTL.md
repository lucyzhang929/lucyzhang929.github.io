---
redirect_from:
  - "uninstall-mssqlctl"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Uninstall_MSSQLCTL.ipynb
kernel_name: python3
has_widgets: false
title: 'Uninstall Mssqlctl'
prev_page:
  url: /Uninstall_AZ_CLI
  title: 'Uninstall Az Cli'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### Uninstall MSSQLCTL

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import sys



if not skip_mssqlctl_uninstall:

    cmd = f'{sys.executable} -m pip uninstall -r {mssqlctl_url} --yes'

    error_check()

    cmd = f'{sys.executable} -m pip uninstall --yes mssqlctl-cli-storage'

    error_check()

else:

    print('SKIPPED: Uninstall MSSQLCTL')
```
</div>

</div>
