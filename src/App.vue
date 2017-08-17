<template>
  <div id="app">
  <h1>在线翻译</h1>
  <h5>简单 / 易用 /便捷</h5>
  <translateForm @formSubmit="translateText"></translateForm>
  <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'app',
  data:function(){
    return{
      translatedText:""
    }
  },
  components: {
    TranslateForm,TranslateOutput
  },
  methods:{
    translateText:function(text,language){
      //alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170817T063631Z.0e84147cbbfb9049.453a616c415745f30019d1545b58e1b5d2beb7b2&lang='+language+'&text='+text).then((response) =>{
        // console.log(response.body.text[0]);
        this.translatedText=response.body.text[0]
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
