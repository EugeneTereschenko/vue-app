<template>
  <div class="hello" id="work">
    <h1>{{ msg }}</h1>
    <div id="parallelogram" ref="parallelogram" v-bind:style="{ width: computedWidth, height: computedHeight  }"></div>
    <div id="custom">
      <p>Height<input v-model="messageHeight" v-bind:placeholder="placeholderHeight"></p>
      <p>Weigth<input v-model="messageWidth" v-bind:placeholder="placeholderWidth"></p>
      <p>Square: {{ message }}</p>
      <p>Perimeter: {{ messagePerimeter }}</p>
      <button v-on:click="reverseMessage">Do it!</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Parallelogram",
  props: {
    msg: String
  },
  data() {
    return {
      messageHeight: '',
      messageWidth: '',
      message: '',
      messagePerimeter: '',
      width: '100px',
      height: '100px',
      placeholderHeight: '100px',
      placeholderWidth: '100px'
    }
  },
  computed: {
  computedWidth: function () {
      return this.width;
    },
  computedHeight: function () {
      return this.height;
    }
  },
  methods: {
    reverseMessage: function () {
      this.width = this.messageWidth + 'px';
      this.height = this.messageHeight + 'px';
      this.message = this.messageWidth*this.messageHeight;
      var tet = parseInt(this.messageHeight)/Math.sin(70);
      tet = Math.round(tet);
      this.messagePerimeter = 2*(parseInt(this.messageWidth) + parseInt(tet));
      this.placeholderHeight = this.messageWidth + "px";
      this.placeholderWidth = this.messageWidth + "px";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

#parallelogram {
  float: left;
  border: 2px solid;
	width: 100px;
	height: 50px;
	transform: skew(20deg);
  background: #555;
  resize: both;
  overflow: auto;
  background-color: #FFFFFF;
}

</style>