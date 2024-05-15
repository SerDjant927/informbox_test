<template>
  <HeaderComponent></HeaderComponent>
  <ContentComponent></ContentComponent>
</template>

<script>
import HeaderComponent from './components/Header.vue'
import ContentComponent from './components/Content.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    ContentComponent
  }
}
</script>

<style>
*{
  box-sizing: border-box;
}
body, html{
  margin:0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
}
</style>
