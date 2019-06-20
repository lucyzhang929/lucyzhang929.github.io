---
redirect_from:
  - "login-to-azure"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Login_to_Azure.ipynb
kernel_name: python3
has_widgets: false
title: 'Login To Azure'
prev_page:
  url: /Install_MSSQLCTL_CLI_for_Linux
  title: 'Install Mssqlctl Cli For Linux'
next_page:
  url: /Login_to_SQL_Server_Big_Data_Cluster
  title: 'Login To Sql Server Big Data Cluster'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Login to Azure**


This will load a browser window to enable credentials to be entered. If this cells is hanging forever, it might be because your Web browser windows is waiting for you to enter your Azure credentials!



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
if not skip_azure_login:

    cmd = f'az login'

    error_check()

else:

    print('SKIPPED: az login')
```
</div>

</div>



### Set Azure Subscription to deploy AKS into.


If you want to deploy to a subscription that is not your default

subscription, then we set it here.

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
if azure_subscription_id != "":

    cmd = f'az account set --subscription {azure_subscription_id}'

    error_check()

else:

    print('Using default Azure subscription', {azure_subscription_id})
```
</div>

</div>

### Showing Azure account info (verifying Azure connectivity)

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'az account show'

error_check()
```
</div>

</div>
