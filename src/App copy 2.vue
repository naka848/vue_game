<template>
    <div class="board">
      <!--  v-bind:count="count"…子コンポーネントに渡すcountの宣言 -->
      <!-- v-on:result-event="appAction"…result-eventにappActionメソッドをバインド  -->
      <Masu
        v-bind:count="count"
        v-on:result-event="appAction" 
        v-for="n of 9"
        v-bind:key="n"
      />
    </div>
</template>

<script>
import Masu from "./components/Masu.vue";

export default {
  name: "App",
  data(){
    return{
      // 子コンポーネントに渡すcountの初期化
      count: 0,
      komasu: "",
    };
  },
  components: {
    Masu,
  },
  methods : {
    appAction(koMass){
      this.komasu = 'koMass'
    }
  }
};
</script>

<style>
.board {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  width: 450px;
}
</style>