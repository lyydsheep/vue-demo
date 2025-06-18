# Vue Demo

> 学习 Vue 过程中的一些 demo，以及知识点记录。

## 基本内容
### 01-demo
1. 一个页面中只能有一个 Vue 实例。
2. el 属性表示 Vue 实例的作用域，一般使用 id 选择器，因为 Vue 实例只能有一个作用域。
3. 不建议选择在html、body 当做作用域的标签，因此需要一个 div 标签包裹。
4. 在作用域范围内通过{{}}，获取 Vue 实例中 data 成员的属性值，并且可以进行算数逻辑运算。

### 声明式渲染
1. 可以根据 JavaScript 的状态来描述 HTML 应该是什么样子的。当状态改变时，HTML 会自动更新。
2. 能在改变时触发更新的状态被称作是响应式的。可以使用`reactive()` 或 `ref()` 来声明响应式状态。

### Attribute 绑定
1. 为了给 attribute 绑定一个动态值，需要使用`v-bind`指令。
```vue
<h1 :class="titleClass">Make me red</h1>
```

### 事件监听 
1. 可以使用`v-on`指令监听 DOM 事件
```vue
<button @click="incr"> Count is {{count}}</button>
```

### 表单绑定
1. 可以同时使用`v-bind`指令和`v-on`指令来在表单的输入单元上创建双向绑定。
2. 上述操作可以换成`v-model`指令。
```vue
<input :bind="text" @input="onInput">

<input v-model="text">
```


