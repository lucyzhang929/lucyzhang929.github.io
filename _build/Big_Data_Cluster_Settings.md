---
redirect_from:
  - "big-data-cluster-settings"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Big_Data_Cluster_Settings.ipynb
kernel_name: python3
has_widgets: false
title: 'Big Data Cluster Settings'
prev_page:
  url: /Azure_Settings
  title: 'Azure Settings'
next_page:
  url: /Create_AKS_Cluster_for_Linux
  title: 'Create Aks Cluster For Linux'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
mssql_cluster_name == ""

bdc_controller_username == ""

bdc_controller_password == ""

bdc_mssql_sa_password == ""
```
</div>

</div>

![11811317_10153406249401648_2787740058697948111_n](https://raw.githubusercontent.com/Microsoft/sqlworkshops/master/graphics/solutions-microsoft-logo-small.png)



## Create Azure Kubernetes Service cluster and a deploy SQL Server 2019 big data cluster


This notebook walks an user through the process of deploying a SQL Server 2019 Big Data Cluster on Azure Kubernetes Service.



### <span style="color:red">Important Instructions</span>
* If you plan to **Run Cells** for this Notebook then please note that the first cell *Big Data Cluster Settings* prompts you to enter some details.

* We have included some default *Azure Settings* in the second cell of this Notebook. If you plan to override please define the appropriate values. You might want to reference Azure Kubernetes Service region and VM size requirements.

* In this Notebook in the *Default Settings*, we will uninstall and reinstall all the dependencies. If you want to skip the dependencies to be reinstalled please set the **skip** variable to be "True".

* If you are experiencing an issue in the *Create AKS Cluster* step you might need to specify servical principal for the AKS Cluster: https://docs.microsoft.com/en-us/azure/aks/kubernetes-service-principal#specify-a-service-principal-for-an-aks-cluster. 

### **Dependencies**


> The Notebook tries to install these dependencies for you. If you

still experience any issues in installing any of the dependencies then please install

from the following Installation links below.



----------------------------------------------------------------

<table>

<colgroup>

<col style="width: 27%" />

<col style="width: 24%" />

<col style="width: 24%" />

<col style="width: 24%" />

</colgroup>

<thead>

<tr class="header">

<th>Tool</th>

<th>Required</th>

<th>Description</th>

<th>Installation</th>

</tr>

</thead>

<tbody>

<tr class="odd">

<td><strong>mssqlctl</strong></td>

<td>Yes</td>

<td>Command-line tool for installing and managing a big data cluster.</td>

<td><a href="deploy-install-mssqlctl.md">Install</a></td>

</tr>

<tr class="even">

<td><strong>kubectl</strong></td>

<td>Yes</td>

<td>Command-line tool for monitoring the underlying Kuberentes cluster (<a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/">More info</a>).</td>

<td><a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-with-powershell-from-psgallery">Windows</a> | <a href="https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-binary-using-native-package-management">Linux</a></td>

</tr>

<tr class="odd">

<td><strong>Azure CLI</strong></td>

<td>For AKS</td>

<td>Modern command-line interface for managing Azure services. Used with AKS big data cluster deployments (<a href="https://docs.microsoft.com/cli/azure/?view=azure-cli-latest">More info</a>).</td>

<td><a href="https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest">Install</a></td>

</tr>

</tbody>

</table>

<p>

### **Big Data Cluster Settings**

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import os, getpass, sys, json

import pandas as pd

import numpy as np

from IPython.display import *



pd.set_option('display.max_colwidth', -1)



print('SQL Server Big Data Cluster Name is: ', mssql_cluster_name)

if mssql_cluster_name == "":

    raise SystemExit(f'Please provide a name of your Big Data Cluster!' + '\n')

print('The Controller Username is: ',bdc_controller_username)

if bdc_controller_username == "":

    raise SystemExit(f'Controller Username is required!' + '\n')

bdc_controller_password = getpass.getpass(prompt='Controller Password: ')

if bdc_controller_password == "":

    raise SystemExit(f'Controller Password is required!' + '\n')

else:

    print('Controller Password is','***********')

bdc_mssql_sa_password = getpass.getpass(prompt='MSSQL Password: ')

if bdc_mssql_sa_password == "":

    raise SystemExit(f'MSSQL Password is required!' + '\n')

else:

    print('MSSQL Password is','***********')
```
</div>

</div>
