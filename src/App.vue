<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" class="border border-primary"/><hr>
  <StartingWithVue msg="Welcome to Your Starter Component" class="border border-success"/><hr>
  <review-form class="border border-primary"/><hr>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import HelloWorld from './components/HelloWorld.vue'
import StartingWithVue from './components/StartingWithVue.vue'
import ReviewForm from './components/ReviewForm.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    StartingWithVue,
    ReviewForm 
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
</style>
