<template>
  <div class="row" id="translateForm">
    <div class="col-md-6 col-md-offset-3">
      <form id="transForm" class="well form-inline" v-on:submit="formSubmit"><!-- 点击事件 -->
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="输入需要翻译的内容">
        <select class="form-control" v-model="language">
            <option value="en">English</option>
            <option value="ru">Russian</option>
            <option value="ko">Korean</option>
            <option value="ja">Janpenese</option>
        </select>
        <input class="btn btn-primary" type="submit" value="翻译">
      </form>
    </div>
  </div>
</template>

<script>
// 使用data方法定义一个属性，然后使用v-model的形式，
// 将值绑定在属性上，先默认给定一个空值然后将这个属性
// 绑定在input标签之中

/*
  用事件注册this.$emit()的方法将内容传递给根组件
*/
export default {
  name: 'translateForm',
  data: function() {
    return {
      textToTranslate:"",
      language:"en"
    }
  },
  methods: {
    formSubmit:function(e){
      // alert(this.textToTranslate);
      this.$emit("formSubmit",this.textToTranslate,this.language);
      e.preventDefault();//取消默认事件
    },
    created () {
      this.language = "en";
    }
  }
}
</script>

<style>
#transForm{
  border-radius:10px;
  border:1px #ccc solid;

  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
