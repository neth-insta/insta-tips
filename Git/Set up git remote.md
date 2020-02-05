* Create git folder and navigate to git folder run below command line:

1,  

```php
$ git branch
```


```php 
$ git init --bare --shared live.productivity.git 
```

2, $ cd live.productivity.git/hooks

3, $ touch post-receive

4, $ chmod +x post-receive

5, $ vim post-receive and Edit file post-receive as below sample:
