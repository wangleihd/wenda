# Meteor + mantra + Reactjs 开发问答系统


使用最新的`Meteor`框架 + 用`mantra`和最流行的前端框架`React`实现wenda系统.


## 项目要求

功能模块 | 前端设计页面 | 功能点说明
--------|------------|-----------
用户模块 | 登陆页面和个人页面 | 1. 做温馨登陆和普通注册登录
 | | 2. 用户用微信登陆并完善信息呢
 | | 3. 登录之后跳转到个人页面并可完善个人信息
 | | 4. 个人页面显示我关心的， 我回应的 ，我发表的问题列表
 | | 5. 点击我关心， 我回应，我发表显示相应问题列表
 | | 6. 从个人页面可以进入到其他人的个人页面
 | | 7. 用户可发表问题，可对其它问题进行回答，关注
 | | 8. 用户可对他人对于问题的答案进行点赞
 | | 9. 用户进行加急问题的奖励金额提问者自定义
问题模块 | 问题列表页面 | 1. 问题分为普通问题和加急问题， 普通问题只显示问题描述，加急问题提问创建新问题时需要定义问题打赏的金额， 问题发布后2个小时内问题答案的赞数最多的一位自动获得此问题的打赏金额
 | | 2. 按标签分类显示问题支持问题关键字搜索功能， 显示问题的发布者头像，昵称，问题标签， 问题描述，发布时间， 浏览量， 回答数，回答者的头像(无交互)， 加急标签， 红包以及红包金额，提供问题的发起功能
 | | 3. 问题列表页数据的优化处理
 | 问题详情页面 | 1. 显示提问者头像，时间，红包以及金额， 紧急标签，问题描述， 问题标签，多少人帮助过她，多少浏览量 ， 多少人关心，回答者的头像 
 | | 2. 我来答跳转到回答页面， 帮你问提示分享 
 | | 3. 答案列表， 包括回答者头像， 昵称， 回答时间， 点赞数，回答内容，点击可进入到答案详情 
 | | 4. 答案详情页可对此答案进行点赞
 | 问题编辑页面 | 1. 可选择普通问题或者加急问题， 可选问题标签，可定义加急问题的红包金额， 问题标题和详细描述
 | 我来答页面 | 1. 输入框 ， 可提交问题问题答案
微信支付和红包模块 | 需要支付以及红包页面 | 1. 微信支付功能 2. 微信红包功能
后台模块 | 后台页面 | 1. 可以对所有的问题进行删除操作 
 | | 2. 可以对所有的答案进行删除操作
 | | 3. 可以对问题进行搜索功能 
 | | 4. 所有打赏的记录(包括打赏的问题， 提问者， 被打赏者，答案赞数，打赏金额)
 | | 所有前端页面的HTML/CSS/JS实现及调整



## 开发流程

### 说明
Github传统的流程。也就是：
* 开发者各自fork项目的repo到自己Github账户下
* 每次开发同步到项目的repo然后开发
* push自己的开发分支到自己Github账户下面的fork的项目repo
* 发送pull request给项目管理员
* 等待review或者merge

## 分支规划
采用git remote add命令给自己本地的开发repo添加分支，我们用一下约定来处理分支的名字
* origin - 直接指向项目的repo
* dev_name - 指向自己fork出来的repo例如我的叫cooloney
* reaction - 指向reaction 原版的repo

## 具体操作
### Fork 项目repo到自己Github账户（只需要setup一次）
* 用自己账户登录Github
* 进入wenda项目repo[主页](https://github.com/wangleihd/wenda)
* 点击右上角的[*fork*按钮](https://github.com/wangleihd/wenda#fork-destination-box)
* 1分钟不到，就会在自己的Github项目下面建立一个私有的项目

### 本地开发的配置（以我的账户示例，也只要setup一次）
* 从wenda的项目repo clone最新的代码
```
git clone --recursive https://github.com/wangleihd/wenda.git
```
* 添加自己fork的repo用来发布代码和发送pull request
```
cd wenda
git remote add youname https://github.com/youname/wenda.git
git fetch youname
git fetch origin
git checkout -b develop origin/develop (create a new branch for development)
git reset --hard origin/develop (reset the local branch to latest origin development branch)
```

### 开发流程（每次开发都要运行）
```
git rebase origin/develop (rebase local change onto origin development branch)
do some work ...
git commit changes
git push --force youname develop
```

### 发送pull request（每次push都需要）
* 登录自己repo的Github主页
* 点击pull request
* 按照下图配置好pull request

<img width="947" alt="screen shot 2015-10-06 at 12 23 08 am" src="https://cloud.githubusercontent.com/assets/758488/10302377/b2d14b5e-6bc0-11e5-9395-b72e0b98616e.png">

## Package Git使用指南
### 说明
* 每一个Package也是一个单独的repo
* 我们只是加入了那些我们需要修改的package，没有修改的package我们用reaction原版的代码。
* 请登陆自己的Github账户fork相应的package repo到自己的Github账户



## 标准PR流程

以我的账号dev1为例，首先需要在master下Fork到自己账户下

### 首次运行，只需要运行一次
```
git clone https://github.com/dev1/h5.git
git remote add upstream https://github.com/master/h5.git
git checkout -b dev upstream/dev
```
### 每次都需要运行
```
git fetch upstream
git reset --hard upstream/dev
```
### ... work
```
git rebase upstream/dev
git push -f origin master
```



## 开发环境
下面我们使用到的开发环境及相关的版本号信息.

* Meteor 1.4
* Mantra
* React 0.15
* semantic-ui
* flow-router

### 创建项目
首先我的项目创建在`github`上. [源码下载地址](https://github.com/wangleihd/wenda.git)

使用`mantra`命令创建`wenda`项目, 在使用`mantra`前, 需要安装`mantra`.

* 安装`mantra`工具

```bash
 $ npm install -g mantra-cli
```

* 创建`wenda`项目

`mantra`会调用本地安装好的`meteor`进行创建项目, 然后再根据需求对项目进行规范化.

```bash
 $ mantra create wenda
```

#### 删除没用的包

* 删除`meteor`自带的包.

```bash
 $ meteor remove insecure
```

* 删除默认的CSS

```bash
 $ meteor remove standard-minifier-css
```

* 删除自动发布包, 这是测时使用, 实际开发的时候推荐使用, 他会把server的代码都发给client端.

```bash
 $ meteor remove autopublish
```

#### 安装 React
``` bash
 $ meteor npm install --save react react-dom
 $ meteor npm install --save react-mounter
```
#### 安装 semantic ui

```bash
 $ meteor add semantic:ui juliancwirko:postcss less jquery
```

#### 安装 facebook包
```bash
 $ meteor add accounts-facebook
```

#### 安装 flow-router
安装命令:

```bash
 $ meteor add kadira:flow-router    
 $ meteor add kadira:dochead
```
需要在 package.json 加入:

```
{
  "devDependencies": {
    "autoprefixer": "^6.3.1"
  },
  "postcss": {
    "plugins": {
      "autoprefixer": {"browsers": ["last 2 versions"]}
    }
  }
}
```
然后再执行:
```bash
 $ meteor npm install
```
* 需要执行下面的两步骤:

1. 必须在项目中的`client/lib/semantic-ui/`目录下创建一个新的空文件`custom.semantic.json`, 注意需要特别提示不要改更目录名和文件名, 因为Meteor的规定. 然后执行 `meteor`.

参考下面的命令:
```bash
 $ pwd
 ~/wenda
 $ touch  client/lib/semantic-ui/custom.semantic.json
 $ meteor
```
1. 然后`meteor`启动后, 会再`client/lib/semantic-ui/`目录下自动创建一个`.custom.semantic.json`的隐藏文件, 需要先把`meteor`停掉. 然后删除这个`meteor`自动生成的文件.再重新启动`meteor`. 会再`client/lib/semantic-ui/`目录下创建出semantic-ui相应的文件. 如果

参考下在的命令:
```bash
 $ 按键盘上的 ctrl + c 停止 meteor.
 $ rm client/lib/semantic-ui/.custom.semantic.json
 $ meteor
```

* 使用时需要用`className`.







## 参考
* [semantic 官网](http://semantic-ui.com/)
* [semantic 中文](http://www.semantic-ui-cn.com/)
* [React 官网](https://facebook.github.io/react/)
* [React 中文](http://reactjs.cn/)
* [Meteor 官网](http://www.meteor.com)
* [FlowRouter](https://github.com/kadirahq/flow-router)
