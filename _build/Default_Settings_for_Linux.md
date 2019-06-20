---
redirect_from:
  - "default-settings-for-linux"
interact_link: content/C:\Users\t-luz\Desktop\fromSwar\LinuxBook\content\Default_Settings_for_Linux.ipynb
kernel_name: python3
has_widgets: false
title: 'Default Settings For Linux'
prev_page:
  url: /Create_SQL_Server_Big_Data_Cluster
  title: 'Create Sql Server Big Data Cluster'
next_page:
  url: /Delete_AKS_Cluster
  title: 'Delete Aks Cluster'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

### **Default Settings for Linux**


Unless you are absolutely sure, please <span style="color:red">do not </span>modify these settings.

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
skip='False'



import getpass, os, secrets, string, random, platform



raise SystemExit("ERROR: You're on a platform we haven't worked out binary locations for. Please log an issue and we will address.")



def error_check():

    print("START " + cmd)

    !{cmd}

    if _exit_code != 0:

        raise SystemExit(f'Shell command:\n\n\t{cmd}\n\nreturned non-zero exit code: ' + str(_exit_code) + '.\n')

    print(f'\nSUCCESS: {cmd}')
```
</div>

</div>

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import os, getpass

import sys





#MSSQL Settings

mssql_cluster_version = os.getenv('AZDATA_MSSQL_CLUSTER_VERSION', 'latest')

bdc_knox_password = bdc_mssql_sa_password



# aks settings

aks_kubernetes_version = os.getenv('AZDATA_AKS_KUBERNETES_VERSION', '')

aks_enable_monitoring = os.getenv('AZDATA_AKS_ENABLE_MONITORING', 'False') == 'True'

aks_cluster_name = os.getenv('AZDATA_AKS_CLUSTER_NAME', mssql_cluster_name)



# docker settings

docker_registry = os.getenv('AZDATA_DOCKER_REGISTRY', 'hlsaris.azurecr.io')

docker_repository = os.getenv('AZDATA_DOCKER_REPOSITORY', 'aris-p-stable-sqlmain-gb')

docker_image_tag = os.getenv('AZDATA_DOCKER_IMAGE_TAG', mssql_cluster_version)

docker_username = os.getenv('AZDATA_DOCKER_USERNAME', '5adc375f-8bcd-486c-ba9b-e821a506977b')

docker_password = os.getenv('AZDATA_DOCKER_PASSWORD', '1cc2d580-7178-4c58-94a1-242a0a13a9b0')

docker_email = os.getenv('AZDATA_DOCKER_EMAIL', 'aristesting@microsoft.com')



# azcli settings

azcli_use_force_install_option = os.getenv('AZDATA_AZCLI_USE_FORCE_INSTALL_OPTION', 'False') == 'True'

azcli_use_user_install_option = os.getenv('AZDATA_AZCLI_USE_USER_INSTALL_OPTION', 'True') == 'True'



# mssqlctl settings

mssqlctl_url = os.getenv('AZDATA_MSSQLCTL_URL', 'http://helsinki/browse/packages/python/aris-p-release-candidate-gb/mssqlctl/requirements.txt'.format(mssql_cluster_version))

mssqlctl_configuration_profile = os.getenv('AZDATA_MSSQLCTL_CONFIGURATION_PROFILE', 'aks-dev-test')

mssqlctl_configuration_file = os.getenv('AZDATA_MSSQLCTL_CONFIGURATION_FILE', 'mssql-bdc-configuration')

mssqlctl_use_force_install_option = os.getenv('AZDATA_MSSQLCTL_USE_FORCE_INSTALL_OPTION', 'False') == 'True'

mssqlctl_use_user_install_option = os.getenv('AZDATA_MSSQLCTL_USE_USER_INSTALL_OPTION', 'True') == 'True'

mssqlctl_binary_location = os.getenv('AZDATA_MSSQLCTL_BINARY_LOCATION', os.path.join(get_binary_location(), 'mssqlctl'))



# kubectl settings

kubectl_windows_url = os.getenv('AZDATA_KUBECTL_WINDOWS_URL', 'https://storage.googleapis.com/kubernetes-release/release/v1.13.0/bin/windows/amd64/kubectl.exe')

kubectl_binary_location = os.getenv('AZDATA_KUBECTL_BINARY_LOCATION', os.path.join(get_binary_location(), 'kubectl'))

kubectl_use_user_install_option = os.getenv('AZDATA_KUBECTL_USE_USER_INSTALL_OPTION', 'True') == 'True'



if skip=='True':

    skip_azure_login = os.getenv('AZDATA_SKIP_AZURE_LOGIN', 'True') == 'True'

    skip_group_delete = os.getenv('AZDATA_SKIP_GROUP_DELETE', 'True') == 'True'

    skip_group_create = os.getenv('AZDATA_SKIP_GROUP_CREATE', 'True') == 'True'

    skip_aks_create = os.getenv('AZDATA_SKIP_AKS_CREATE', 'True') == 'True'

    skip_mssqlctl_uninstall = os.getenv('AZDATA_SKIP_MSSQLCTL_UNINSTALL', 'True') == 'True'

    skip_mssqlctl_install = os.getenv('AZDATA_SKIP_MSSQLCTL_INSTALL', 'True') == 'True'

    skip_azcli_uninstall = os.getenv('AZDATA_SKIP_AZCLI_UNINSTALL', 'True') == 'True'

    skip_azcli_install = os.getenv('AZDATA_SKIP_AZCLI_INSTALL', 'True') == 'True'

    skip_kubectl_install = os.getenv('AZDATA_SKIP_KUBECTL_INSTALL', 'True') == 'True'

else:

    skip_azure_login = os.getenv('AZDATA_SKIP_AZURE_LOGIN', 'False') == 'True'

    skip_group_delete = os.getenv('AZDATA_SKIP_GROUP_DELETE', 'False') == 'True'

    skip_group_create = os.getenv('AZDATA_SKIP_GROUP_CREATE', 'False') == 'True'

    skip_aks_create = os.getenv('AZDATA_SKIP_AKS_CREATE', 'False') == 'True'

    skip_mssqlctl_uninstall = os.getenv('AZDATA_SKIP_MSSQLCTL_UNINSTALL', 'False') == 'True'

    skip_mssqlctl_install = os.getenv('AZDATA_SKIP_MSSQLCTL_INSTALL', 'False') == 'True'

    skip_azcli_uninstall = os.getenv('AZDATA_SKIP_AZCLI_UNINSTALL', 'False') == 'True'

    skip_azcli_install = os.getenv('AZDATA_SKIP_AZCLI_INSTALL', 'False') == 'True'

    skip_kubectl_install = os.getenv('AZDATA_SKIP_KUBECTL_INSTALL', 'False') == 'True'



# include settings

include_bdc_delete = os.getenv('AZDATA_INCLUDE_BDC_DELETE', 'True') == 'True'



print('')

print('PARAMETERS:')

print('')

print(f'mssql_cluster_version = {mssql_cluster_version}')

print(f'mssql_cluster_name = {mssql_cluster_name}')

print(f'azure_subscription_id = {azure_subscription_id}')

print(f'azure_vm_size = {azure_vm_size}')

print(f'azure_vm_count = {str(azure_vm_count)}')

print(f'azure_region = {azure_region}')

print(f'azure_resource_group = {azure_resource_group}')

print(f'aks_kubernetes_version = {aks_kubernetes_version}')

print(f'aks_enable_monitoring = {str(aks_enable_monitoring)}')

print(f'aks_cluster_name = {aks_cluster_name}')

print(f'docker_registry = {docker_registry}')

print(f'docker_repository = {docker_repository}')

print(f'docker_image_tag = {docker_image_tag}')

print(f'docker_username = {docker_username}')

print(f'docker_password = {docker_password}')

print(f'docker_email = {docker_email}')

print(f'azcli_use_force_install_option = {str(azcli_use_force_install_option)}')

print(f'azcli_use_user_install_option = {str(azcli_use_user_install_option)}')

print(f'mssqlctl_url = {mssqlctl_url}')

print(f'mssqlctl_configuration_profile = {mssqlctl_configuration_profile}')

print(f'mssqlctl_configuration_file = {mssqlctl_configuration_file}')

print(f'mssqlctl_use_force_install_option = {str(mssqlctl_use_force_install_option)}')

print(f'mssqlctl_use_user_install_option = {str(mssqlctl_use_user_install_option)}')

print(f'mssqlctl_binary_location = {mssqlctl_binary_location}')

print(f'kubectl_windows_url = {kubectl_windows_url}')

print(f'kubectl_binary_location = {kubectl_binary_location}')

print(f'kubectl_use_user_install_option = {str(kubectl_use_user_install_option)}')

print(f'bdc_controller_username = {bdc_controller_username}')

print(f'skip_azure_login = {str(skip_azure_login)}')

print(f'skip_group_delete = {str(skip_group_delete)}')

print(f'skip_group_create = {str(skip_group_create)}')

print(f'skip_aks_create = {str(skip_aks_create)}')

print(f'skip_mssqlctl_uninstall = {str(skip_mssqlctl_uninstall)}')

print(f'skip_mssqlctl_install = {str(skip_mssqlctl_install)}')

print(f'skip_azcli_uninstall = {str(skip_azcli_uninstall)}')

print(f'skip_azcli_install = {str(skip_azcli_install)}')

print(f'skip_kubectl_install = {str(skip_kubectl_install)}')

print(f'include_bdc_delete = {str(include_bdc_delete)}')

print(f'')
```
</div>

</div>
