<template>
  <div id="app">
    <h2>TodoList</h2>
    <!-- <img src="./assets/logo.png">
    <HelloWorld/> -->
    <input class="input" type="text" v-model="value">
    <button class="btn" @click="handleSubmit">提交</button>
    <ul>
      <todo-item v-for="(item,index) of list" :content="item" :key="index" :index="index" @delete="handleDelete"></todo-item>
    </ul>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import TodoItem from "./components/TodoItem";

export default {
  components: {
    "todo-item": TodoItem
    // HelloWorld
  },
  data: function() {
    return {
      value: "",
      list: []
    };
  },
  methods: {
    handleSubmit: function() {
      this.list.push(this.value);
      this.value = "";
    },
    handleDelete:function(index){
      this.list.splice(index,1);
    }
  }
};
</script>

<style>
*{
  list-style: none;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width:1200px;
  margin:60px auto 0;
}
ul,li{
  list-style: none;
}
/* .input{
  width:150px;
  height:45px;
}
.btn{
  width:75px;
  height: 45px;
  background:#ff7875;
  color:#fff;
  padding:0;
  margin:0;
} */
ul{
  display: flex;
  flex-direction: column;
  width:700px;
  margin:10px auto;
}
</style>
