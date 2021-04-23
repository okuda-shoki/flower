<template>
<div class="container">
  <h1>花占いゲーム</h1>
  <p>花の枚数:{{item}}</p>
  <p>現在の状況:{{word}}</p>
  <button @click="dec()">花びらを減らす</button>
  </div>
</template>

<script>
export default {
  
  data(){
    function getRandomIntInclusive() {
      return Math.floor(Math.random()*9)+2;
}
      let a=["嫌い","好き"];
      let x;
      x=Math.floor(Math.random()*2); 
      let document=a[x]
return{
  item:getRandomIntInclusive(),
  document
}
  },
  methods:{
    dec(){
      if(this.item>0){
        this.item--;
      }
      return this.item
    }
  },
  computed:{
    word(){
      
    }
  }
}
</script>

<style scoped>
.container{
  text-align: left;
}

</style>
