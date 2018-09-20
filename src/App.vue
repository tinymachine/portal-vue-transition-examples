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
