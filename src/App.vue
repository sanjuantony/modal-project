<template>
<!-- 
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
-->

<h1>{{title}}</h1>
<!--
<br>
<input type="text" ref="txt" width="100px">
<button @click="handleClick">Click Me</button>
-->
<Modal :header="header" :text="text"/>

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
        text: "Grab your ninja swag for half price"
      }
  },
  methods: {
    handleClick() {
      console.log(this.$refs.txt)
      this.$refs.txt.classList.add("active")
      this.$refs.txt.focus()
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
