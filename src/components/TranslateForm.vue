<template>
  <div class="row" id="translateForm" >
    <div class="col-md-6 col-md-offset-3">
      <form id="tranForm" class="well form-inline" @submit="formSubmit">
        <input class="form-control" type="text" placeholder="输入需要翻译的内容" v-model="textToTranslate">
        <select class="form-control form-inline" v-model="language">
          <option value="en">English(英语)</option>
          <option value="ru">Russian(俄语)</option>
          <option value="ko">korean(韩语)</option>
          <option value="de">German(德语)</option>
          <option value="fr">French(法语)</option>
        </select>
        <input class="btn btn-primary" type="submit" value="翻译">
      </form>
    </div>
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
#transForm{
  border:1px #ccc solid;
  border:1px #ccc solid;
}
</style>