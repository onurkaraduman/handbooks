# Partially checkout a directory in git repository
```
mkdir repo -dir
cd repo -dir
git init
git config core.sparseCheckout true
git remote add -f origin git://repo-location
echo "required_subdir/*" > .git/info/sparse-checkout
git checkout [branchname]
git pull
```
