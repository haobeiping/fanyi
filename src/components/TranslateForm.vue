<template>
  <div id="translateForm">
    <form @submit="formSubmit">
      <input type="text" placeholder="输入需要翻译的内容" v-model="textToTranslate">
      <select v-model="language">
        <option value="en">English(英语)</option>
        <option value="ru">Russian(俄语)</option>
        <option value="ko">korean(韩语)</option>
        <option value="de">German(德语)</option>
        <option value="fr">French(法语)</option>
      </select>
      <input type="submit" value="翻译">
    </form>
  </div>
</template>

<script>

export default {
  name: 'translateForm',
  data:function(){
    return {
      textToTranslate:'',
      language:''
    }
  },
  methods: {
    formSubmit:function(e){
      //alert(this. textToTranslate);
      this.$emit('formSubmit',this.textToTranslate,this.language);//传递
      e.preventDefault()
    }
  }
}
</script>

<style>

</style>