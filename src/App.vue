<template>
  <div id="app">
    <HelloWorld msg="Pokemons on VUE CLI"/>
    <MyTitle title="Hola"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyTitle from './components/MyTitle.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    MyTitle
  }
}
</script>

<style>

</style>
