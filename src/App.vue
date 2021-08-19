<template>
<!-- 
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
-->

<h1>{{title}}</h1>
<br>
<button @click="toggleModal">Show Modal Window #1</button>
<button @click="toggleModal2">Show Modal Window #2</button>
<!--
<br>
<input type="text" ref="txt" width="100px">
<button @click="handleClick">Click Me</button>
-->
<div v-if="showModal">
  <Modal  @closeModal="toggleModal">
      <h2>{{header}}</h2>
      <p>{{text}}</p>
      <template v-slot:links >
        <a href="#">Link 1</a><br>
        <a href="#">Link 2</a>
      </template>
  </Modal>
</div>

<div v-if="showModal2">
  <Modal  @closeModal="toggleModal2">
      <h2>Modal 2</h2>
      <p>Welcome to model # 2</p>
      <template v-slot:links >
        <a href="#">Link 1</a><br>
        <a href="#">Link 2</a>
      </template>
  </Modal>
</div>

</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
        title: "Welcome to VueJS!",
        header: "Sign up for the giveaway!",
        text: "Grab your ninja swag for half price",
        showModal: false,
        showModal2: false
      }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.txt)
      this.$refs.txt.classList.add("active")
      this.$refs.txt.focus()
    },
    toggleModal() {
      this.showModal = !this.showModal
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid green;
  display: inline-block;
  padding: 5px;
}
</style>
