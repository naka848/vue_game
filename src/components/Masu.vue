<template>
  <p ref="msg" v-on:click="doAction">{{ block }}</p> 
</template>

<script>
export default {
  name: 'Masu',
  props: {
    block: String,
  },
  // 子コンポーネント内でcounterを宣言
  // mounted(){
  //       this.counter = 0
  // },
  methods:{
    doAction(){
      this.$emit('result-event',)
    }
  }
}

</script>
