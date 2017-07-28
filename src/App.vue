<template>
  <div id="app" class="text-center">
  <h1>Word Translator</h1>
  <h5>Powerd by Vue.js</h5>
  <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
  <TranslateOutput v-text="translatedText"></TranslateOutput>
  
  </div>
</template>

<script>
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'app',
  components: {
    TranslateForm,
    TranslateOutput
  },
  data: function(){
    return {
      translatedText:''
    }
  },
  methods: {
    translateText:function(text, language){
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170728T095610Z.8f73e84300b727c4.83c875c16795f0a74454dbd6dc91c384fd23de73&lang='+language+'&text='+text)
      .then((response) => {
       this.translatedText = response.body.text[0];
      });
    }
  }
}
</script>

<style>
body {
  background: #fefefe;
  
}
</style>
