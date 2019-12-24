## 1. invalid value for prop on <td> tag either remove it from the element, or ...

解决方式&原因： 参照 antd 官方 demo，只在 edit 为 true 时触发 oncell，td 未非编辑状态时不必传参；

_tips: react antd table 20191217_

## 2. monitor-chart 组件在本机外曲线等不刷新；

解决方式&原因： 服务启动机器与访问页面机器时间不对应；代码中判断时间差大于一定频率才刷新；

_tips: 基础 算法 canvas chart 20191224_
