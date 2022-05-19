<template>
  <div>
    <datepicker :language="ja" v-model="newDate"  :clear-button="true" format="yyyy.MM.dd"/>
    <div v-if="newDate">{{newDate|date}}が選択されました</div>
  </div>
</template>

<script>
import Datepicker from "vuejs-datepicker";
import moment from "moment";
 import { ja } from "vuejs-datepicker/dist/locale";

export default {
  components: {
    Datepicker
  },
  computed: {
    ja(){
        return ja;
    }
  },
  data(){
    return{
      newDate:"",
    }
  },
  filters:{
    date(newDate) {
      return moment(newDate).format("y年M月D日");
    }
  }

};
</script>