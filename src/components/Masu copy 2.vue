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
      masu: "",
    };
  },
  // 親コンポーネントから値を受け取る
  props:{
    count: Number,
  },
  methods:{
    doAction(){
      // masuの値の更新
      if(this.count % 2 === 0 ){
        this.masu = "◯" ;
      } else {
        this.masu = "×";
      }
      // result-eventイベントをthis.masuの値付きで呼び出す
      // $emitでresult-eventを発火→（親コンポーネントへ）→result-eventが発生し、appActionメソッドを呼び出す
      this.$emit('result-event,this.masu')
    }
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
  /* color: red; */
}
</style>



// やりたいこと！クリックイベントがおきたらその情報を親に伝える！！