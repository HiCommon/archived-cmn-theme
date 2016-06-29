# Common Wordpress Theme

## About 
This is the Wordpress theme we use to power our blog. The blog is hosted at GoDaddy using their managed Wordpress product.

## Local development
1. Install VirtualBox
https://www.virtualbox.org/

2. Install Vagrant
http://www.vagrantup.com/

3. Install the vagrant-hostsupdater plugin. (Optional)
```
$ vagrant plugin install vagrant-hostsupdater
```

4. Download the vccw vagrant box
https://github.com/vccw-team/vccw/archive/2.21.0.zip

6. Unzip and cd into the direcoty
```
$ cd vccw-x.x.x
```

7. Launch the vagrant machine
```
$ vagrant up
```

8. Log into wp-admin
Visit http://vccw.dev/wp-admin

user: admin
password: admin

9. Change the theme to `common-theme`

10. Install fswatch
```
$ brew install fswatch
```

11. Watch and sync the theme directory
From within the `common-theme` directory (remember to replace the path for vccw).
```
$ fswatch -o ./ | xargs -n1 sh -c 'rsync -a ./ /PATH/TO/YOUR/BOX/vccw-2.21.0/www/wordpress/wp-content/themes/common-theme'
```


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

Clear cache in GoDaddy console.
Login to Wordpress Admin page. Click `Flush Cache`.

