<template>
  <div>
    <input type="text" v-model="newTodo">
    <button @click="onClicked">登録</button>
    <pre>{{$data}}</pre>
  </div>
</template>

<script>
export default {
  data(){
    return {
      newTodo:'新しいタスク3',
      todos:["洗濯物","勉強"]
    }
  },
  methods:{
    onClicked(){
      this.todos.push(this.newTodo);
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