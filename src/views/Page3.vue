<template>
  <div>
    <input type="text" v-model="newTodo">
    <button @click="onClicked">add</button>
    <ul>
      <li v-for="(hoge,index) in todos" :key="index">{{hoge}}</li>
    </ul>
    <pre>{{$data}}</pre>
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
       this.todos.push(this.newTodo)
      }
  }

}
</script>

<style scoped>

</style>