<template>
  <div id="translateOutput">
      {{translatedText}}
  </div>
</template>

<script>
export default {
  name: 'translateOutput',
  props: ["translatedText"]//获取父组件的值
}
</script>

<style>

</style>
