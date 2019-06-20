---
redirect_from:
  - "login-to-sql-server-big-data-cluster"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Login_to_SQL_Server_Big_Data_Cluster.ipynb
kernel_name: python3
has_widgets: false
title: 'Login To Sql Server Big Data Cluster'
prev_page:
  url: /Login_to_Azure
  title: 'Login To Azure'
next_page:
  url: /Show_Big_Data_Cluster_Endpoints
  title: 'Show Big Data Cluster Endpoints'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Login to SQL Server big data cluster**

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print (f'Creating MSSQL_CLUSTER: bdc {mssql_cluster_name} using configuration file {mssqlctl_configuration_file}')



os.environ["CONTROLLER_USERNAME"] = bdc_controller_username

os.environ["CONTROLLER_PASSWORD"] = bdc_controller_password



cmd = f'mssqlctl login --cluster-name {mssql_cluster_name}'

error_check()
```
</div>

</div>

### Show big data cluster status

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'mssqlctl bdc status show'

error_check()
```
</div>

</div>

### Show big data cluster status –debug

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
cmd = f'mssqlctl bdc status show --debug'

error_check()
```
</div>

</div>
