<template>
  <div id="app">
    <Square msg="This is square"/>
    <Triangle msg="This is triangle"/>
    <Parallelogram msg="This is parallelogram"/>
    <Circlet msg="This is circle"/>
  </div>
</template>

<script>

import Square from "./components/Square.vue"
import Triangle from "./components/Triangle.vue"
import Parallelogram from "./components/Parallelogram.vue"
import Circlet from "./components/Circlet.vue"

export default {
  name: "app",
  components: {
        Square,
      Triangle,
  Parallelogram,
         Circlet
  }
};
</script>

<style lang="scss">

#app {
  float: left;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
