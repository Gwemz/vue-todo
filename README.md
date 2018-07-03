```
template:''
v-text
v-html
v-on:click="handleClick"    =>  @click="handleClick"

表达式: v-bind:title="title"  => :title="title"

双向数据绑定： v-model="content"

计算属性： 
computed:{
    fullName:function(){
        return this.firstName + this.lastName
    }
}

侦听器
watch:{
    firstName:function({
        this.count ++
    })
}

v-if 从DOM中移除
v-show  会隐藏，但不会从Dom中清除（性能更好一些）

v-for="(item,index) of list" :key="index"

自定义组件(全局组件)
<todo-item v-for="(item,index) of list" :key="index" :content="item"></todo-item>

Vue.component('todo-item',{
    props:['content'],
    template:'<li>{{content}}</li>'
})
<!-- 局部组件 -->
var TodoItem = {
    template:'<li>item</li>'
}

component:{
    'todo-item':TodoItem
}

每个组件就是一个实例

子组件向父组件传值，进而执行相关的操作

<!-- 全局安装 vue-cli -->
npm install --global vue-cli

vue init webpack my-project

cd my-project

npm run dev

```
## 每一个组件就是一个vue的实例，每一个实例下边有很多的属性和方法

vm.$destory()  实例被销毁

example:index2.html

## 生命周期就是Vue实例在某一个时间点会自动执行的函数
8个生命周期函数
beforeCreate
created
beforeMount
mounted
beforeUpdate
updated
beforeDestory
destroyed

## 模板语法：
{{name}} 差值表达式
v-text="name + ' Lee'"
v-html="name + ' Lee'"

## 计算属性、方法、侦听器
