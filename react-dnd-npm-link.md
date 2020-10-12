# 问题： 使用npm link 本地测试react-dnd组件报错
## 报错信息： 
    react-dom.development.js:11102 Uncaught Error: Could not find the drag and drop manager in the context of XXXX(组件名).

## 问题分析：
### 1. react-dnd不是同一个实例
    在项目中引用的react-dnd和npm link后组件中的react-dnd不是一个实例。导致这个问题的原因是因为npm link作用
### 2. npm link 的作用
    这是也是为什么会出现上述问题的原因。因为npm link的作用是将本地项目和本地npm模块之间进行连接，而不是将dist中build后的文件进行连接。
    那么就导致了两个node_modules存在；项目中引用的react-dnd是从项目根目录下的node_modules中引出的我们称为dnd1。
    然而在link 组件中的dnd是由组件项目中的node_modules引用的-dnd2。
    所以dnd1和dnd2是完全两个不同的实例（尽管dnd版本和HTML5-backend版本完全一致）所以才会出现上述报错。
## 解决方案：
### 直接在dist中引用测试，而不使用npm link
    1. 确保在组件项目路径中
    2. npm run build (获得dist文件夹)
    3. 将dist文件夹复制到引用项目中（引用dnd组件的项目）
    4. 通过相对路径的方式进行import

## 例子
(例子请查看drag-box/test/example.jsx)   
内网连接：xxxxx.git

### 问题复现：

1. git clone
2. 文件中有两项目：drag-box, test-box
3. 进入test-box项目的根目录:npm run link
4. 进入drag-box项目的根目录: npm run link test-box  /名字由package.json中的name属性决定
5. 直接在node_modules中引用: import {Box} from 'test-box' 

### 解决方案：
1. 在test-box项目路径中执行：npm run build（在根目录下会产生dist文件夹）
2. 将dist文件夹复制到应用项目drag-box中，通过相对路径的方式直接引用，进行测试