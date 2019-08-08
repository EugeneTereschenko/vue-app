<template>
  <div class="hello" id="work">
    <h1>{{ msg }}</h1>
    <div id="circlet" ref="circlet" v-bind:style="{ width: computedWidth, height: computedHeight  }"></div>
    <div id="custom">
      <p>Radius<input v-model="messageWidth" v-bind:placeholder="placeholder" class="radius"></p>
      <p>Square: {{ message }}</p>
      <p>Perimeter: {{ messagePerimeter }}</p>
      <button v-on:click="reverseMessage">Do it!</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "circlet",
  props: {
    msg: String
  },
  data() {
    return {
      messageHeight: '',
      messageWidth: '',
      message: '',
      messagePerimeter: '',
      width: '200px',
      height: '200px',
      placeholder: '200px'
    }
  },
  computed: {
  computedWidth: function () {
    this.placeholder = this.width;
      return this.width;
    },
  computedHeight: function () {
      return this.height;
    }
  },
  methods: {
    reverseMessage: function () {
      this.width = this.messageWidth + 'px';
      this.height = this.messageWidth + 'px';
      this.message = Math.round(Math.PI*parseInt(this.messageWidth)*parseInt(this.messageWidth));
      this.messagePerimeter = Math.round(2*Math.PI*parseInt(this.messageWidth));
      this.placeholder = this.messageWidth + "px";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

#circlet {
  float: left;
  background-color: #FFFFFF;
  border:1px solid black;
  height: 100px;
  border-radius: 50%;
  -moz-border-radius: 50%;
  -webkit-border-radius: 50%;
  width: 100px;
}


</style>
