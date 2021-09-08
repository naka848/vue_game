
<template>
  <div id="app">
    <!-- ①定数に値をいれる -->
    <!-- <Que title="問題"
    message="奈良公園の？"/> -->
    <!-- ②変数に値をいれる -->
    <!-- v-bindをつけないとうまくいかない！ -->
    <!-- <Que title="mondai"
    message="奈良公園の？"/> -->
    <Que title="問題"
    v-bind:message="mondai"/>
    <Choices v-bind:choice="kotae.A" />
    <Choices v-bind:choice="kotae.B" />
    <Choices v-bind:choice="kotae.C" />
    <Choices v-bind:choice="kotae.D" />
  </div>
</template>

<script>
import Que from './components/Que.vue'
import Choices from './components/Choices.vue'

export default {
  name: 'App',
  components: {
    Que,
    Choices,
  },
  // mondai変数を使ってみようとする
  data(){
    return{
      mondai:"奈良公園の？",
      // sentakushi1:"なまず",
      // sentakushi2:"ねずみ",
      // sentakushi3:"きつね",
      // sentakushi4:"しか",
      // オブジェクトの中にオブジェクトをいれる
      kotae:{
        A:"なまず",
        B:"ねずみ",
        C:"きつね",
        D:"しか",
      }
    }
  },
}
</script>
