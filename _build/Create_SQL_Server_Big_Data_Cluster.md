---
redirect_from:
  - "create-sql-server-big-data-cluster"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Create_SQL_Server_Big_Data_Cluster.ipynb
kernel_name: python3
has_widgets: false
title: 'Create Sql Server Big Data Cluster'
prev_page:
  url: /Create_an_Azure_Resource_Group
  title: 'Create An Azure Resource Group'
next_page:
  url: /Default_Settings_for_Linux
  title: 'Default Settings For Linux'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Create SQL Server big data cluster**

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print (f'Creating MSSQL_CLUSTER: cluster {mssql_cluster_name} using configuration file {mssqlctl_configuration_file}')



os.environ["CONTROLLER_USERNAME"] = bdc_controller_username

os.environ["CONTROLLER_PASSWORD"] = bdc_controller_password

os.environ["MSSQL_SA_PASSWORD"] = bdc_mssql_sa_password

os.environ["KNOX_PASSWORD"] = bdc_knox_password

os.environ["DOCKER_REGISTRY"] = docker_registry

os.environ["DOCKER_REPOSITORY"] = docker_repository

os.environ["DOCKER_USERNAME"] = docker_username

os.environ["DOCKER_PASSWORD"] = docker_password

os.environ["DOCKER_EMAIL"] = docker_email

os.environ["DOCKER_IMAGE_TAG"] = docker_image_tag



cmd = f'mssqlctl bdc create -c {mssqlctl_configuration_file} --accept-eula yes'

error_check()
```
</div>

</div>
