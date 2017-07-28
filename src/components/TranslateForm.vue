<template>
  <div id="TranslateForm">
      
      <form v-on:submit="formSubmit">
          <input type="text" v-model="textToTranslate" placeholder="Enter a word">
          <select v-model="language">
              <option value="no">Norwegian</option>
              <option value="es">Spanish</option>
              <option value="fr">French</option>
              <option value="ru">Russian</option>
              <option value="ja">Chinese</option>

          </select>
          <input type="submit" value="Translate">
      </form>

  </div>
</template>

<script>
export default {
  name: 'TranslateForm',
  data(){
      return {
          textToTranslate:'',
          language: ''
      }
  },
  created() {
      this.language = 'no';
  },
  methods: {
      formSubmit(e){
          this.$emit('formSubmit', this.textToTranslate, this.language);
          e.preventDefault();
      }
  }
}
</script>

<style>
#app {
  
}
</style>
