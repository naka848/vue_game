
<template>
  <div id="app" class="container">
    <!-- v-bind：属性名＝"設定する値" -->
    <Masu 
      class="kakou" 
      v-for="n of 9" 
      v-bind:key="n"  
      v-bind:count="counter" 
      v-on:result-event="appAction" />
  </div>
</template>

<script>
import Masu from './components/Masu.vue'

export default {
  name: 'App',
  data(){
    return{
      counter: 0,
    };
  },
  components: {
    Masu,
  },
  // mounted(){
  //       this.counter = 0
  // },
  methods:{
    appAction(){
      this.counter++
    }
  },
}
</script>

<style>
.container{
  display: grid;
  grid-template-columns: 180px 180px 180px;
  grid-template-rows: 180px 180px;
}
.kakou{
  border: 1px solid;
  margin: 10px;
  padding: 50px;
  width: 150px;
  height: 150px;
}
</style>
