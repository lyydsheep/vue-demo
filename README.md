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

### 列表渲染
1. 使用`v-for`指令来渲染一个基于原数组的列表
```vue
<li v-for="todo in todos" :key="todo.id">
  {{todo.text}}
</li>
```

### 计算属性
1. computed可以让创建一个计算属性ref，这个 ref 会动态的根据依赖的响应式数据动态的计算其`.value`

### 生命周期和模板引用
1. 模板应用：指向模板中一个 DOM 元素的 ref
```vue
<p ref="pElementRef">hello</p>

<!--当 script setup 执行时 DOM 元素还不存在，所以初始值为 null-->
const pElementRef = ref(null)
```

### 侦听器
1. `watch()可以直接侦听一个 ref，并且值发生改变就触发回调`

### 组件
1. 父组件可以在模板中渲染另一个组件作为子组件。

### Props
1. 子组件可以通过 props 从父组件接受动态数据
```vue
<script setup>
  const props = defineProps({
    msg: String
  })
</script>1
```

### Emits
1. 子组件可以向父组件触发事件
2. ·emit()的第一个参数是事件的名称，其他所有参数都传给事件监听器
```vue
const emit = defineEmits(['response'])
emit('response', 'hello')
```

### 插槽
1. 除了 props 传递数据外，父组件还可以通过插槽（slots）将模板片段传递给子组件
```vue
<childComp>
  This is some slot content!
</childComp>
```