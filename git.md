#Git 操作步骤

## github 远程库关联

``` bash
$ git remote add origin git@github.com:[github_addr]
```

## git 初始化

``` bash
$ git init
```

## git 添加文件

``` bash
$ git add [ADD_FILE_PATH]
```

## git 提交到本地仓库

``` bash
$ git commit -m "comment"
```

## 上传至github

``` bash
$ git push -u origin master(branch)
```


--- 
##其他操作
| 操作 | 命令 |
|:-----|:-----|
| 创建SSH | ssh-keygen -t rsa -C "e-mail" |
| 配置github登陆名 | git config --global user.name "name" |
| 配置github邮箱 | git config --global user.email "mail@mail.com" |
