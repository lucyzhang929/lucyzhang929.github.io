---
redirect_from:
  - "install-kubernetes-cli-for-linux"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Install_Kubernetes_CLI_for_Linux.ipynb
kernel_name: python3
has_widgets: false
title: 'Install Kubernetes Cli For Linux'
prev_page:
  url: /Install_Azure_CLI
  title: 'Install Azure Cli'
next_page:
  url: /Install_MSSQLCTL_CLI_for_Linux
  title: 'Install Mssqlctl Cli For Linux'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### Install Kubernetes CLI for Linux

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import platform

import requests

import sys



if not skip_kubectl_install:

    cmd = f'sudo apt-get update'

    print("START " + cmd)

    !{cmd}

    if _exit_code != 0:

        raise SystemExit(f'Shell command:\n\n\t{cmd}\n\nreturned non-zero exit code: ' + str(_exit_code) + '.\n')

    print(f'\nSUCCESS: {cmd}')

    cmd = f'sudo apt-get install -y kubectl'

    print("START " + cmd)

    !{cmd}

    if _exit_code != 0:

        raise SystemExit(f'Shell command:\n\n\t{cmd}\n\nreturned non-zero exit code: ' + str(_exit_code) + '.\n')

    print(f'\nSUCCESS: {cmd}')



else:

    print('SKIPPED: Uninstall KUBECTL')
```
</div>

</div>
