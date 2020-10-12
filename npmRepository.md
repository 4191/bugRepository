## 1. npm install 包失败
- 报错现象：
```
E:\testSpace\g6-in-react-master>npm i '@babel/core'
npm ERR! Error while executing:
npm ERR! C:\Program Files\Git\cmd\git.EXE ls-remote -h -t ssh://git@github.com/babel/core'.git
npm ERR!
npm ERR! fatal: remote error:
npm ERR!    is not a valid repository name
npm ERR!   Email support@github.com for help
npm ERR!
npm ERR! exited with error code: 128

npm ERR! A complete log of this run can be found in:
```
- 原因：包名加了引号
- 解决方式：把引号去掉（有时报错是因为该加引号时没加，反向处理即可）
```
npm i '@babel/core
```

## 2. Fail to install npm package “npm ERR! errno -4048”
- 原因：权限有问题
- 解决方式：
  - a. npm cache clean -f
  - b. 删掉package-lock.json后重新npm i
  _tips: 4048 permitted lock_

<!-- 图片写法  ![test](./test.png 'test') -->
 