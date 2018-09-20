<template>
  <div>
    <button @click="showModalA = true">
      Launch Regular Modal
    </button>

    <the-modal
      v-if="showModalA"
      @close="showModalA = false"
    >
      I transition out correctly.
    </the-modal>

    <button @click="showModalB = true">
      Launch Modal via Portal
    </button>

    <portal to="modalDestination">
      <the-modal
        v-if="showModalB"
        @close="showModalB = false"
      >
        I don't transition out.
      </the-modal>
    </portal>

  </div>
</template>

<script>
import TheModal from './TheModal.vue'

export default {
  name: 'TheModalParent',
  data: function () {
    return {
      showModalA: false,
      showModalB: false
    }
  },
  components: {
    TheModal
  }
}
</script>
