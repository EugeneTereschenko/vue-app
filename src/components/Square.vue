<template>
  <div class="hello" id="work">
    <h1>{{ msg }}</h1>
      
    <div id="square" ref="square" v-bind:style="{ width: computedWidth, height: computedHeight  }"></div>
    <div id="custom"
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
  name: "Square",
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
      this.message = this.messageWidth*this.messageHeight;
      this.messagePerimeter = parseInt(this.messageWidth) + parseInt(this.messageWidth) + parseInt(this.messageHeight) + parseInt(this.messageHeight);
      this.placeholderHeight = this.messageWidth + "px";
      this.placeholderWidth = this.messageWidth + "px";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
#work {
  margin-top: -90px;
}

#custom {
  float: left;
   margin-top: 0px;
}

#square {
  margin-top: 0px;
  float: left;
  border: 2px solid;
  width: 50px;
  height: 50px;
  background-color: #FFFFFF;
  resize: both;
  overflow: auto;
}

</style>
