<template>
  <div>
    <ul>
      <li>チーム名 ......{{heroTeam.data.squadName}} </li>
      <li>活動範囲 ...... {{heroTeam.data.homeTown}}</li>
      <li>結成 ...... {{heroTeam.data.formed}}</li>
      <li>拠点 ......{{heroTeam.data.secretBase}}</li>
      <li>活動しているか ......{{heroTeam.data.active}}</li>
      <li>隊員 ......
        <ul v-for="(member,index) in heroTeam.data.members" :key="index">
          <li>名前 ...... {{member.name}}</li>
          <li>年齢 ...... {{member.age}}</li>
          <li>正体 ...... {{member.secretIdentity}}</li>
          <li>能力 ......
            <ul v-for="(power,index) in member.powers" :key="index">
              <li>{{power}}</li>
            </ul>
          </li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data(){
    return{
      heroTeam:[]
    }
  },
  mounted(){
    axios.get("https://mdn.github.io/learning-area/javascript/oojs/json/superheroes.json")
    .then((res)=>{
      this.heroTeam = res;
    })
  }

}
</script>

<style>

</style>