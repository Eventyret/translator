<template>
  <div class="row" id="TranslateForm">
      <div class="col-md-6 col-md-offset-3">
      <form class="well" v-on:submit="formSubmit">
          <input class="form-control"type="text" v-model="textToTranslate" placeholder="Enter a word">
          <select class="form-control" v-model="language">
              <option value="no">Norwegian</option>
              <option value="es">Spanish</option>
              <option value="fr">French</option>
              <option value="ru">Russian</option>
              <option value="ja">Chinese</option>
          </select>
          <br>
          <input class="btn btn-primary" type="submit" value="Translate">
      </form>
    </div>
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
