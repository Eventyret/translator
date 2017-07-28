<template>
  <div class="row" id="TranslateForm">
      <div class="col-md-6 col-md-offset-3">
      <form  id="transForm" class="form-inline well" v-on:submit="formSubmit">
          <input class="form-control" type="text" v-model="textToTranslate" v-on:input="formSubmit" placeholder="Please input an English word or sentence" style="min-width: 50%"></input>
          <select class="form-control" v-model="language" v-on:change="formSubmit">
              <option value="en">Translate to</option>
              <option value="no">Norwegian</option>
              <option value="es">Spanish</option>
              <option value="fr">French</option>
              <option value="ru">Russian</option>
              <option value="zh">Chinese</option>
              <option value="ja">Japanese</option>
              <option value="cz">Czech</option>
              <option value="sk">Slovakian</option>
              <option value="he">Hebrew</option>

          </select>
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
          language: 'en'
      }
  },
  created() {
      this.language = 'en';
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
#transForm {
    border-radius: 10px;
    bordeR: 1px solid #ccc;
}
</style>
