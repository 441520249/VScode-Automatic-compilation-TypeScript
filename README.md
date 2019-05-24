# TypeScript 安装及开发环境配置

## 1.TypeScript 是 Node 的超集，使用需要先安装 Nodejs

英文官网：nodejs.org

中文官网：nodejs.org/zh-cn

查看是否安装完成： node -v 查看 node 版本 npm -v 查看 npm版本

## 2.安装 TypeScript

全局安装：npm install typescript -g

查看是否安装完成：tsc --version 查看版本

## 3.node 项目初始化生成 package.json

npm init

npm init -y (-y 跳过配置)

## 4.typescript 生成 node 文件的配置需要生成配置文件 tsconfig.json

tsc --init

## 5.模块的声明文件问题需要一个 node 包 @types/node

npm install @types/node --dev-save (--dev-save 安装在开发文件)

## 6.构建

先创建 ts 文件，在文件中声明内容

var a:string = "Hello World!"
console.log(a)
ts 需要转换成 js 使用

编译命令：tsc .ts文件

VSCode 中点击任务选择 运行生成任务 （Ctrl + Shift + B）

# VScode 自动编译TypeScript的方式

选中 tsc：构建-tsconfig.json
## 1、首先进入nodejs里安装typescript
```js
npm install -g typescript
```

## 2、创建相应的项目目录，打开nodejs 进入当前项目目录
```
例：我的项目地址E:\example\ts，nodejs里 e:回车，复制地址(E:\example\ts)，点击nodejs右键，粘贴，回车，即进入项目目录E:\example\ts。
```

## 3、创建tsconfig.json文件
```js
tsc --init
```

## 4、打开tsconfig.json文件修改和删除相应配置（如果想快速修改配置，请复制下列配置）
```js
{
  "compilerOptions": {
   "target": "es5",
   "noImplicitAny": false,
   "module": "amd",
   "removeComments": false,
   "sourceMap": false,
   "outDir": "src/js"//你要生成js的目录
  }
}
```

## 5、创建src目录，打开vscode新建文件，保存到src下扩展名为.html的文件，然后在编辑器里代码区输入此快捷方法，快速创建html布局代码
```
！+tab
```
## 自行添加js引入代码
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script type="text/javascript" src="js/test.js"></script><!--自行添加js引入-->
</head>
<body>
     
     
</body>
</html>
```

## 6、回到E:\demo\ts 目录，创建ts文件夹，然后新建ts为扩展名的ts文件(test.ts)，测试代码如下：
```js
class Student {
    firstName : string;
    lastName : string;
 
    constructor(fiestName : string,  lastName : string) {
        this.firstName = fiestName;
        this.lastName = lastName;
    }
    greeter() {
        return `Hello,您好${this.firstName}${this.lastName}`;
    }
}
var user = new Student("刘","小健");
var ele = document.body || document.documentElement;
ele.innerHTML = user.greeter();
```

## 7、点击菜单 任务-运行任务，点击 tsc:构建-tsconfig.json
```
VSCode 中点击任务选择 运行生成任务 （Ctrl + Shift + B）
tsc:构建 - typescript\tsconfig.json
```

## 8、此时src目录下会自动生成js/test.js文件了；打开test.js文件，点击编辑器的拆分编辑器菜单，即把js和ts文件拆开，自行编辑ts文件的时候，右侧会自动生成js代码。
```
VSCode 中点击任务选择 运行生成任务 （Ctrl + Shift + B）
tsc:监视 - typescript\tsconfig.json
```
