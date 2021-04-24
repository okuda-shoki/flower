<template>
<div class="container">
  <h1>花占いゲーム</h1>
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
  item:getRandomIntInclusive(),
  word:document,
  show:true
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
      saveword(){
        const parsed=JSON.stringify(this.word);
        localStorage.setItem('word',parsed)
      },
      saveitem(){
        const stored=JSON.stringify(this.item);
        localStorage.setItem('item',stored)
        },
    },


    mounted(){
     if(localStorage.getItem('word')){
       try{
         this.word=JSON.parse(localStorage.getItem('word'))
       }catch(e){
         localStorage.removeItem('word')
       }
     }
     if(localStorage.getItem('item')){
       try{
         this.item=JSON.parse(localStorage.getItem('item'))
       }catch(e){
         localStorage.removeItem('item')
       }
     }
     var a = new Date();
var b = new Date();
console.log(b - a); //this works
localStorage.a = a;
localStorage.b = b;
a = Date.parse(localStorage.a); // parse to date object
b = Date.parse(localStorage.b);
console.log(b - a);
    },
}
  
</script>

<style scoped>
.container{
  text-align: left;
}

</style>
