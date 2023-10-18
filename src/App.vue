<template>
  <h1> {{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <HelloWorld theme="" @close = "toggleModal">
      <template v-slot:links>
        <a href="#">Sign up</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja Giveaway</h1>
      <p>Get yours today, enter the game to win a logitec mouse and keyboard</p>
    </HelloWorld>
  </div>
  <button @click.alt="toggleModal">Open Modal (alt)</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      title: 'My first Vue app :)',

      showModal: false
    }
  },

  methods: {
      toggleModal() {
        this.showModal = !this.showModal
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
</style>
