# Azure Automation Account

## List blob storage

download the python packages needed.

~~~ bash
touch .gitignore
echo "python/" >> .gitignore
mkdir python
cd pyhton
pip download azure.identity
pip download azure.storage.blob
pip download typing_extensions
pip download msal
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

## MISC

### github
~~~ bash
gh repo create $prefix --public
git init
git status
git add .gitignore
git add *
git commit -m"Initial commit"
git remote add origin https://github.com/cpinotossi/$prefix.git
git remote -v
git push origin main
git rm README.md # unstage
git config advice.addIgnoredFile false
git pull origin main
git merge 
origin main
git config pull.rebase false

git log --oneline --decorate // List commits
git tag -a v1 e1284bf //tag my last commit
git push origin master


git tag //list local repo tags
git ls-remote --tags origin //list remote repo tags
git fetch --all --tags // get all remote tags into my local repo

git log --pretty=oneline //list commits


git checkout v1
git switch - //switch back to current version
co //Push all my local tags
git push origin <tagname> //Push a specific tag
git commit -m"not transient"
git tag v1
git push origin v1
git tag -l
git fetch --tags
git clone -b <git-tagname> <repository-url> 
~~~

