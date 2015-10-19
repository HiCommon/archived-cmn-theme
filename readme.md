# Common Wordpress Theme

## About 
This is the Wordpress theme we use to power our blog. The blog is hosted at GoDaddy using their managed Wordpress product.

## Setup
You will need to add the remote repository details. You can get the login details from joel@hicommon.com

## Deploying
We use a git post-receive hook on the server to handle updating the theme on the filesystem. 

In order to deploy, simply use git push to send your updates to the server which will place the updated them in the rigth directory.

Update this repo with your changes:
```
$> git push origin master
```

Push changes to production. 
```
$> git push production master
```

