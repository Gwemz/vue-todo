<template>
  <div>
    <!-- <img src="./assets/logo.png">
    <HelloWorld/> -->
    <input type="text" v-model="value">
    <button @click="handleSubmit">提交</button>
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
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
