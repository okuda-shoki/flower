<template>
<div class="container">
  <p>花の枚数:{{item}}</p>
  <p v-if="show">現在の状況:{{word}}</p>
  <p v-else>結果:{{word}}</p>
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
      var document=a[x]
return{
  list:[],
  item:getRandomIntInclusive(),
  word:document,
  show:true,
}
  },
  methods:{
    dec(){
      if(this.item>1){
        this.item--;
        if(this.word==="好き"){
          this.word="嫌い"
        }else{
          this.word="好き";
        }
      }else if(this.item>0){
        this.item--;
        this.show=false;
        if(this.word==="好き"){
          this.word="嫌い"
        }else{
          this.word="好き";
        }
          return this.word
      }else if(this.item==0){
        this.$router.go({
          path: this.$router.currentRoute.path,
              force: true,
            });
            }
      },
    },
  
    mounted(){
      this.list.push(this.item);
      this.list.push(this.word);
      localStorage.list="foo";
    },
}
  
</script>

<style scoped>
.container{
  text-align: left;
}

button{
  color: red;
}

button:hover{
  color: blue;
}

</style>
