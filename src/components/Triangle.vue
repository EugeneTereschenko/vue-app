<template>
  <div class="hello" id="work">
    <h1>{{ msg }}</h1>
    <div id="triangle" ref="triangle" v-bind:style="{ width: computedWidth, height: computedHeight  }"></div>
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
  name: "triangle",
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
      placeholderHeight: '200px',
      placeholderWidth: '200px'
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
      let diagonal = Math.sqrt(parseInt(this.messageWidth)*parseInt(this.messageWidth) + parseInt(this.messageHeight)*parseInt(this.messageHeight));
      diagonal = Math.round(diagonal);

      var sum = parseInt(this.messageWidth) + parseInt(this.messageHeight) + parseInt(diagonal);
      var Poluperimeter = parseInt(sum)/2;
      var square = Math.sqrt(parseInt(Poluperimeter)*(parseInt(Poluperimeter) - parseInt(this.width))*(parseInt(Poluperimeter) - parseInt(this.height))*(parseInt(Poluperimeter) - parseInt(diagonal)));
      square = Math.round(square);

      this.message = square;
      this.messagePerimeter = sum;

      this.placeholderHeight = this.messageWidth + "px";
      this.placeholderWidth = this.messageWidth + "px";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

#work {
  display: inline-block;
}

#custom {
  float: left;
  padding-left: 10px;
}

#triangle {
  float: left;
  background-color: #000000;
  clip-path: polygon(0 100%, 0 0, 100% 100%, 0 100%, 3% 98%, 95% 98%, 2% 5%, 2% 99%);
  width: 100px;
  height: 100px;
  justify-content: center;
  align-items: center;
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>
