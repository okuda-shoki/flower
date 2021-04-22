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
      var a=["嫌い","好き"];
      var x;
      x=Math.floor(Math.random()*2); 
return{
  item:getRandomIntInclusive(),
  word:a[x],
}
  },
  methods:{
    dec(){
      if(this.item>0){
        this.item--;
      }
    }
  }
}
</script>

<style scoped>
.container{
  text-align: left;
}

</style>
