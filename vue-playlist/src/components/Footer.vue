<template>
    <footer>
       <p>{{copyright}} {{title}}</p>
    </footer>
</template>

<script>
export default {
  name: "app-footer",
  props:{
      title:{
          type:String
      }
  },
  data() {
    return {
        copyright:"copyright 2017 Vue Demo"
    };
  }
};
</script>

<style scoped>
footer{
    background: rgb(3, 3, 3);
    padding: 6px;
}
footer p{
    color:rgb(53, 165, 72);
    text-align:center;
}
</style>
