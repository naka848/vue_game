<template>
  <div class="masu" v-on:click="doAction">
    {{ masu }}
  </div>
</template>

<script>
export default {
  name: "Masu",
  data(){
    return{
      // {{ masu }} の初期値の設定
      masu: "",
    };
  },
  // 親コンポーネントから値を受け取る
  props:{
    count: Number,
    number: Number,
  },
  methods:{
    doAction(){
      if(this.masu === ""){
        // masuの値の更新
        this.masu = this.count % 2 === 0? "○" : "×"
      // result-eventイベントをthis.masuの値付きで呼び出す
      // $emitでresult-eventを発火→（親コンポーネントへ）→result-eventが発生し、appActionメソッドを呼び出す
      // $emitは引数なくてもいい！その時は「,」不要
      this.$emit('result-event')
      }
      // 確認用
      // console.log(this.count)
      // console.log(this.number)
    },
  },
};
</script>

<style>
.masu {
  width: 150px;
  height: 150px;
  border: 1px solid black;
  text-align: center;
  font-size: 80px;
}
</style>

