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