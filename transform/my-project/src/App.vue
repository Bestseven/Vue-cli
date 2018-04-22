<template>
  <div id="app">
    <h1>映雪湖在线翻译</h1>
    <h5 class="text-muted">简单 / 易用 / 便捷</h5>
    <translateForm v-on:formSubmit="translateText"></translateForm>
    <translateOutput v-text="translatedText"></translateOutput>
  </div>
</template>

<script>
// 在页面定义一个属性将值保存起来然后传入输出的组件
//将子组件绑定给父组件，在模板上面就可以调用
//在TranslateOutput标签上绑定一个属性，将translatedForm传递给子组件
import TranslateForm from './components/TranslateForm'
import TranslateOutput from './components/TranslateOutput'
export default {
  name: 'App',
  data () {
    return {
      translatedText:""
    }
  },
  components: {
   TranslateForm,
   TranslateOutput
  },
  methods: {
    translateText:function(text,language){
      // alert(text);
      this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20180422T060616Z.09da6bc9e1715307.cb118878ab81e6d14aa30e4aa6ef7ee2008085dd&text='+ text +'&lang='+language)
      .then((response)=>{
        // console.log(response.body.text[0]);
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
  color: #922ea7;
  margin-top: 60px;
}
</style>
