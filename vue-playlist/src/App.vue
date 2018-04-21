<!-- 1模板:html结构 -->
<!-- 有且仅有一个根标签 -->
<template>
  <div id="app">
    <ur>
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/helloworld">Hello</router-link></li>
    </ur>
    <router-view></router-view>
  </div>
</template>

<!-- 2行为：处理逻辑 -->
<!-- 组件和组件之间联系需要注册 -->
<script>

export default {
  name: "app",
  data() {
    return {

    };
  },
  components: {
 
  },
  methods:{

  }
};
</script>

<!-- 3样式：解决样式 -->
<style>
h1 {
  color: rgb(226, 110, 43);
}
</style>
