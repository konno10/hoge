<template>
  <div>
    <input type="text" v-model="newTodo">
    <button @click="onClicked">add</button>
    <ul>
      <li v-for="(hoge,index) in todos" :key="index">
        <input type="checkbox" v-model="hoge.isDone">
        <span :class="{done:hoge.isDone}">{{hoge.name}}</span>
      </li>
    </ul>
    <pre>{{$data}}</pre>
  </div>
</template>

<script>
export default {
  data(){
    return{
      newTodo:'',
      todos:[]
    }
  },
  methods:{
      onClicked(){
        const newItem = {
          name:this.newTodo,
          isDone:false
        }
        this.todos.push(newItem)
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
                