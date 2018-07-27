<template>
  <div class="container" id="translateForm">
    <div>
      <form id="transForm" class="well form-inline" v-on:submit="formSubmit">
        <input calss="form-control" type="text" placeholder="请输入需要翻译到内容" 
        v-model="textToTranslate">
        <select v-model="lang">
          <option value="en" selected>English</option>
          <option value="ru">Russian</option>
          <option value="ko">Korean</option>
          <option value="ja">Janpanese</option>
        </select>
        <input class="btn btn-primary" type="submit" value="翻译">
      </form>
    </div>
  </div>
</template>

<script>
export default {
   name:'translateForm',
   data:function(){
     return{
       textToTranslate:"",
       lang:''
     }
   },
   methods:{
     formSubmit:function(e){
      //  alert(this.textToTranslate);
      this.$emit("formSubmit",this.textToTranslate,this.lang);
       e.preventDefault();
     },
     created:function(){
       this.lang='en';
     }
   }
}
</script>

<style>
    .container{
      padding:20px;
      display: flex;
      align-items: center;
      justify-content: space-around;
    }
    #transForm{
      padding:20px;
      border:1px rgb(168, 164, 164) solid;
      border-radius: 10px;
    }
</style>
