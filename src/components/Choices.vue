<template>
  <div class="alert alert-info m-3">
    <!-- 箱のどこをおしても判定が返る -->
    <h5 v-on:click="doAction" ref="ans">{{ choice }}</h5>
    <!-- ボタンつくった -->
    <!-- <h5>{{ number }}.{{ choice }}</h5>
    <div>
      <button class="btn btn-info mt-2" v-on:click="doAction">Click</button>
    </div> -->
  </div>
</template>

<script>
export default {
  name: 'Choices',
  props: {
    // App.vueの中のnumber=""をみている
    // number: String,
    choice: String,
  },
  methods:{
    doAction(){
      // this.number…propsのnumber: Stringをみにいく
      // this.choiceでも正解を指定できる
      if(this.choice=="しか"){
      this.$refs.ans.innerHTML = '<h5>正解</h5>'
      // propsの値は直接変更できない→テンプレート参照
      // this.answer = "正解"
      }else{
        console.log("不正解")
        this.$refs.ans.innerHTML = '<h5>不正解</h5>'
      }
    }
  }
}
</script>
