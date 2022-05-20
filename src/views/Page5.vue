<template>
  <div>
    <router-link :to="month == 1 ? `/Page5/${year-1}/12` : `/Page5/${year}/${month-1}`">＜</router-link>
    <span>{{year}}年{{month}}月</span>
    <router-link :to="month ==12? `/page5/${year+1}/1` : `/page5/${year}/${month+1}`">＞</router-link>
  </div>
</template>

<script>
export default {
 computed:{
   year(){
     return Number(this.$route.params.year)
   },
   month(){
     return Number(this.$route.params.month)
   }
 }
}
</script>

<style scoped>
*{
  font-size: 50px;
}
</style>