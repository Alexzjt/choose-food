<template>
  <div id="app">
    <MyCarousel/>
    <ChooseFood></ChooseFood>
  </div>
</template>

<script>

import MyCarousel from "./components/MyCarousel";
import ChooseFood from "./components/ChooseFood";
export default {
  name: 'app',
  components: {
    ChooseFood,
    MyCarousel
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
