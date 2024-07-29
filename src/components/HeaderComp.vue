<template>
  <header class="headerComp">
    <p>Adrianas super tolle erste Vue.js App</p>
    <h1>Random Quote Getter</h1>
  </header>
</template>


<script>
export default {
  name: 'HeaderComp',
}
</script>


<style scoped>

.headerComp {
  background-color: #ffaec9;
  border-radius: 4px;
  width: 100%;
  box-sizing: border-box;
  padding: 20px;
  margin: 0;
}

p, h1 {
  margin: 0;
  line-height: 1.5;
}

p{
  font-size: 20px;
}

h1{
  font-size: 22px;
}



</style>