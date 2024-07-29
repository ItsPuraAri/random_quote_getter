<template>



  <HeaderComp/>
  <ZitatBox/>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import ZitatBox from './components/ZitatBox.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    ZitatBox

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
}
</style>
