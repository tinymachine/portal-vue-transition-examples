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
  font-family: -apple-system, BlinkMacSystemFont,
               'avenir next', avenir,
               'helvetica neue', helvetica,
               ubuntu,
               roboto, noto,
               'segoe ui', arial,
               sans-serif;
}
</style>
