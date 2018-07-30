# project

> 我的VUE测试工程

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run e2e tests
npm run e2e

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).


1、（先进入项目文件夹）通过命令 git init 把这个目录变成git可以管理的仓库
>git init

2、把文件添加到版本库中，使用命令 git add .添加到暂存区里面去，不要忘记后面的小数点“.”，意为添加文件夹下的所有文件
>git add .

3、用命令 git commit告诉Git，把文件提交到仓库。引号内为提交说明
>git commit -m 'first commit'

4、关联到远程库
>git remote add origin 你的远程库地址
如：git remote add origin https://github.com/cade8800/ionic-demo.git

5、获取远程库与本地同步合并（如果远程库不为空必须做这一步，否则后面的提交会失败）
>git pull --rebase origin master

6、把本地库的内容推送到远程，使用 git push命令，实际上是把当前分支master推送到远程。执行此命令后会要求输入用户名、密码，验证通过后即开始上传。
>git push -u origin master

*、状态查询命令
>git status