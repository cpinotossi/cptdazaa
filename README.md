# Azure Automation Account

## List blob storage

download the python packages needed.

~~~ bash
mkdir python
cd pyhton
pip download azure.identity
pip download azure.storage.blob
pip download typing_extensions
cd ..
~~~

You will need to upload the python packages via the portal.


### Create an Azure Storage Account with Private link
~~~bash
sudo hwclock -s
sudo ntpdate time.windows.com
prefix=cptdazaa
location=westeurope
myobjectid=$(az ad user list --query '[?displayName==`ga`].id' -o tsv)
myip=$(curl ifconfig.io)
tid=$(az account show --query tenantId -o tsv)
# az group delete -n $prefix -y
az automation account show -n $prefix -g $prefix
# Need to try to get this done via IaC
# az deployment sub create -n $prefix -l $location --template-file deploy.bicep -p myobjectid=$myobjectid myip=$myip prefix=$prefix
~~~

