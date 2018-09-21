<template>
  <div id="app">
    <the-modal-parent/>
    <portal-target name="modalDestination"/>
  </div>
</template>

<script>
import TheModalParent from './components/TheModalParent.vue'

export default {
  name: 'app',
  components: {
    TheModalParent
  }
}
</script>

<style>
body {
  font-family: sans-serif;
  line-height: 1.4;
}

button {
  margin: .5rem .5rem .5rem 0;
  padding: 1rem 2rem;
  font-size: 1rem;
  border: 1px solid lightgray;
  background-color: white;
}
</style>
