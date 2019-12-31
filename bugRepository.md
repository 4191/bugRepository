## 1. invalid value for prop on <td> tag either remove it from the element, or ...

解决方式&原因： 参照 antd 官方 demo，只在 edit 为 true 时触发 oncell，td 未非编辑状态时不必传参；

_tips: react antd table 20191217_

## 2. monitor-chart 组件在本机外曲线等不刷新；

解决方式&原因： 服务启动机器与访问页面机器时间不对应；代码中判断时间差大于一定频率才刷新；

_tips: 基础 算法 canvas chart 20191224_

## 3. react 引入 html 方法及编码错误乱码

解决方式&原因：

```
<iframe
    <!-- onLoad={() => {
		const obj = ReactDOM.findDOMNode(this);
		this.setState({
			"iFrameHeight":  obj.contentWindow.document.body.scrollHeight + 'px'
		});
    }}
    ref="iframe"
    src="/courses.html"
    width="100%"
    height={this.state.iFrameHeight}
    scrolling="no"
    frameBorder="0" -->
	title='resg'
	srcDoc={userManual}
	style={{width:'100%',boder:0,height:'100%'}}
	sandbox="allow-same-origin allow-scripts allow-popups allow-forms"
	scrolling="auto"
            />
```

乱码：vs 切换至 gb2313 保存，再切换回 utf-8，保存；

_tips:react iframe html 乱码 编码错误 20191231_
