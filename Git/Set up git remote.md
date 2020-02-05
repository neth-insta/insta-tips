* Create git folder and navigate to git folder run below command line:

```php 
$ git init --bare --shared live.productivity.git 
```
```php 
$ cd live.productivity.git/hooks 
```
```php
$ touch post-receive
```
```php
$ chmod +x post-receive
```
```php
$ vim post-receive
```
* Edit file post-receive as below sample:
```php
#!/bin/bash

TARGET="/home/productivitystsk/public_html/live"
GIT_BARE="/home/productivitystsk/git/live.productivity.git"
BRANCH="master"

while read oldrev newrev ref
do
	# only checking out the master
	if [[ $ref = refs/heads/$BRANCH ]];
	then
		echo "Ref $ref received. Deploying ${BRANCH} branch to uat..."
		git --work-tree=$TARGET --git-dir=$GIT_BARE checkout -f
	else
		echo "Ref $ref received. Doing nothing: only the ${BRANCH} branch may be deployed on this server."
	fi
done

```
