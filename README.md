---
title: Meteor + mantra + Reactjs 开发问答系统
---
使用最新的`Meteor`框架 + 用`mantra`和最流行的前端框架`React`实现教学教育网站的制作过程.

<!-- more -->


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
