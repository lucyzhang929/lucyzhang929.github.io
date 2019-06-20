---
redirect_from:
  - "install-mssqlctl-cli-for-linux"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Install_MSSQLCTL_CLI_for_Linux.ipynb
kernel_name: python3
has_widgets: false
title: 'Install Mssqlctl Cli For Linux'
prev_page:
  url: /Install_Kubernetes_CLI_for_Linux
  title: 'Install Kubernetes Cli For Linux'
next_page:
  url: /Login_to_Azure
  title: 'Login To Azure'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### Install MSSQLCTL CLI for Linux


Install mssqlctl to manage SQL Server big data clusters.



    For details see:



        https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-install-mssqlctl

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print(f'START: !{sys.executable} -m pip install -r {mssqlctl_url} --force-reinstall\n') 



!{sys.executable} -m pip install -r {mssqlctl_url} --force-reinstall --trusted-host helsinki

    if _exit_code != 0:

        raise SystemExit('Shell command:\n\n\t!{sys.executable} -m pip install -r {mssqlctl_url} --force-reinstall\n\nreturned non-zero exit code: ' + str(_exit_code) + '.\n')



print(f'\nSUCCESS: !{sys.executable} -m pip install -r {mssqlctl_url} --force-reinstall')



print ('======== Begin MSSQLCTL version  ========')

print(f'START: !mssqlctl --version\n')



!mssqlctl --version

if _exit_code != 0:

   raise SystemExit('Shell command:\n\n\t!mssqlctl --version\n\nreturned non-zero exit code: ' + str(_exit_code) + '.\n')



print(f'\nSUCCESS: !mssqlctl --version')

print ('======== End MSSQLCTL version  ========')
```
</div>

</div>
