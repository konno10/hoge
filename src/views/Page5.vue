<template>
  <div>
    <input type="text" v-model="newTodo">
    <button @click="onClicked">add</button>
    <ul>
      <li v-for="(hoge,index) in todos" :key="index">
        <input type="checkbox" v-model="hoge.isDone">
        <span :class="{done:hoge.isDone}">{{hoge.name}}</span>
        <button @click="delate(hoge.name,index)">delate</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      newTodo:"",
      todos:[]
    }    
  },
  methods:{
    onClicked(){
      let newItem={
        name:this.newTodo,
        isDone:false,
      }
      if(this.newTodo!=""){
        this.todos.push(newItem)
      }
      this.newTodo="";
    },
    delate(name,index){
      if(confirm(name+"を削除しますか")){
      this.todos.splice(index,1)
      }
    }
  }
}
</script>

<style scoped>
.done {
    opacity: 0.5;
    text-decoration: line-through;
}
li {
    list-style: none;
    margin-bottom: 10px;
}
span,
input,
button {
    margin-right: 5px;
}
hr {
    margin: 20px 0;
}
</style>