<template>
  <div id="app">
    <h1>在线翻译</h1>
    <h5 class="text-muted">简单／易用／便捷</h5>
      <translateForm v-on:formSubmit="translateText"></translateForm>
      <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm';
import TranslateOutput from './components/TranslateOutput';
export default {
  name: 'App',
  components:{
    TranslateForm,
    TranslateOutput
  },
  data:function(){
     return{
       translatedText:''
     }
  },
  methods:{
    translateText:function(text,lang){
      // alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180727T031550Z.9661f05f27ca3d05.456849a2b2e1cd93eecc0bdde5611b9ef1550d3c&lang='+lang+'&text='+text).then((response)=>{
        console.log(response.body.text[0]);
        this.translatedText=response.body.text[0];
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
