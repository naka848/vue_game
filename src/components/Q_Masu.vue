<template>
  <p v-on:click="doAction">{{ block }}</p> 
</template>

<script>
export default {
  name: 'Masu',
  data(){
    return{
      block: "",
    };
  },
  props: {
    block: String,
    counter: Number,
  },
  // 子コンポーネント内でcounterを宣言
  // mounted(){
  //       this.counter = 0
  // },
  methods:{
    doAction(){
      this.$emit('result-event',this.counter)
      if(this.counter % 2 == 0){
        this.block = '×'
      }else{
        this.block = '×'
      }
    },
  }
}

</script>
