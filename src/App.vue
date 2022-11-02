<template>
  <TypeMd/>
</template>

<script>
import TypeMd from './components/TypeMd.vue'

export default {
  name: 'App',
  components: {
    TypeMd,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@200&display=swap');

body{
  margin:0;
  padding: 0;
  font-family: "Roboto", sans-serif;
}

::-webkit-scrollbar{
width: 4px;
}
::-webkit-scrollbar-track{
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb{
  background: #999;
}

::-webkit-scrollbar-thumb:hover{
  background: #333;
}
</style>
