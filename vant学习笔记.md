# Vant 学习笔记

    注：所用组件默认已正确引入
## 1. 基础组件
### Button
基本写法
```html
<van-button>按钮</van-button>
```
可以添加type属性改变button样式，type默认为default，可选primary、warning、danger。
```html
<van-button type="default">默认按钮</van-button>
<van-button type="primary">主要按钮</van-button>
<van-button type="warning">警告按钮</van-button>
<van-button type="danger">危险按钮</van-button>
```
添加plain属性按钮样式将变为镂空样式，disabled将按钮设置为禁用状态，loading将按钮设置为加载状态，loading状态将不显示文字。添加square将按钮设置为方形按钮，此时与普通按钮区别为按钮的border-radius为0，添加round属性将变为圆形按钮，此时border-radius为50%。按钮有四种尺寸分别为large、normal、small、mini。其中size设为large按钮将独占一行。
所有可设置属性如下表：    
|     参数      |      说明      |    类型     |     默认  值 |
| --- | ---- | ---- | ----- |
|type |类型，可选值为primary、warning、danger | String | default |
|size |尺寸，可选值为 large small mini | String | normal |
|text |文字   | String |   
|tag  |HTML 标签 | String | button 
|native-type| 原生 type 属性 | String | - |
|disabled| 是否禁用按钮	| Boolean | false |
|loading| 是否显示为加载状态 |Boolean	| false
|block | 是否为块级元素	 |Boolean | false
|plain| 是否为朴素按钮	|Boolean | false
|square| 是否为方形按钮	|Boolean | false
|round| 是否为圆形按钮	|Boolean | false
### Cell 单元格
需要配合CellGroup使用，基本用法代码示例如下
```html
<van-cell-group>
  <van-cell title="单元格" value="内容" />
  <van-cell title="单元格" value="内容" label="描述信息" />
</van-cell-group>
```
其中Cell单元格title内容<font color="#f25">与官网文档示例不同</font>，官网示例为靠左对齐，实际是居中的，如果要靠左对齐可以全局设置一下样式
```css
.van-cell__title {
  text-align: center;
}
```
**CellGroup 参数**
| 参数 | 说明 | 类型 | 默认值 |
| --- | ---- |-----| ----- |
|border|是否显示外边框|Boolean| true
**Cell参数**
| 参数 | 说明 | 类型 | 默认值 |
| --- | ---- |-----| ----- |
|icon |左侧图标名称或图片链接，<br>可选值见Icon组件 |
|title|左侧标题 |String \| Number | - |
|value|右侧标题 |String \| Number | - |
|label|标题下方的描述信息 | String | - |
|size |单元格大小，可选值为 large | String | -
|url  |	跳转链接 | String | -
|to    |路由跳转对象，同 vue-router 的 to| String \| Object | - |
|border|是否显示内边框| Boolean | true
|replace|跳转时是否替换当前页面历史| String | false
|clickable|是否开启点击反馈| Boolean | false
|is-link |是否展示右侧箭头并开启点击反馈| Boolean | false
|require|是否显示表单必填星号| Boolean | false
|center |是否使内容垂直居中| Boolean | false
|arrow-<br>direction|箭头方向，可选值为 left up down|String|-
|title-class|左侧标题额外类名|String|-
|value-class|右侧内容额外类名|String|-
|label-class|右侧内容额外类名|String|-
   **Cell slot 插槽**
|名称&nbsp;&nbsp;&nbsp;|说明|
|-|-|   
|-|匿名插槽，自定义value内容
|title|自定义title内容
|icon|自定义icon
|right-icon|自定义右侧按钮，默认为arrow
### **<font color="#69f" >icon字体图标</font>**
基本用法代码示例
```html
<van-icon name="close" />
<van-icon name="https://b.yzcdn.cn/vant/icon-demo-1126.png" />
```      
其中name为vant内置icon的名称，也可以是图片链接。