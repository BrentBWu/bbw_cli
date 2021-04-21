# bbw_cli

## 自定义脚手架

### 主要依赖包说明

#### **commander**
用于编写指令以及处理命令行, 用法如下:
```javascript
const program = require("commander");
// 定义指令
program
  .version('0.0.1')
  .command('init', 'Generate a new project from a template')
  .action(() => {
    // 回调函数
  })
// 解析命令行参数
program.parse(process.argv);

```
#### **inquirer**
交互式命令行工具，用法如下：
```javascript
const inquirer = require('inquirer');
inquirer
  .prompt([
    // 一些交互式的问题
  ])
  .then(answers => {
    // 回调函数，answers 就是用户输入的内容，是个对象
  });
```

#### **chalk**
这是用来修改控制台输出内容样式的，比如颜色啊，具体用法如下：
```javascript
const chalk = require('chalk');
console.log(chalk.green('success'));
console.log(chalk.red('error'));
```

#### **ora**
加载动画，用法如下：
```javascript
const ora = require('ora')
let spinner = ora('downloading template ...')
spinner.start()
```

#### **download-git-repo**
git相关，用法如下：
```javascript
const download = require('download-git-repo')
download(repository, destination, options, callback)
```

### 目录搭建
1. 新建一个bin文件夹
    - 新建一个无后缀名的xr文件(入口文件，主要是为了兼容Mac，系统看到第一行会沿着路径查找node并执行)，并写上：
    ```js
    #!/usr/bin/env node
    console.log('hello');
    ```