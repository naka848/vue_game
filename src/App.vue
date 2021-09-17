<template>
    <div class="board">
      <!--  v-bind:count="count"…子コンポーネントに渡すcountの宣言 -->
      <!-- v-on:result-event="appAction"…result-eventにappActionメソッドをバインド  -->
      <!-- v-bind:key="n"
        v-bind:number="n" …KEYをPROPSで渡したらコンソールログはundefinedになってしまう。ナゼ？→keyは決まっている用語でVUEが使うもの。numberはこちらが適当につけたものなので、こちらで扱うことができる-->
      <Masu
        v-bind:count="count"
        v-on:result-event="appAction" 
        v-for="n of 9"
        v-bind:key="n"
        v-bind:number="n"
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
    };
  },
  components: {
    Masu,
  },
  methods: {
    appAction(){
      // カウントの増やし方
      // this.count++
      this.count += 1;
    },
  },
};
</script>

<style>
.board {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  width: 450px;
}
</style>