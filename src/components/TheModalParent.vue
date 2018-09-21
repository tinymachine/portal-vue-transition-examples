<template>
  <div>
    <h1>portal-vue {{ portalVueVersion }}</h1>

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
import PackageLock from './../../package-lock.json'

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
  },
  computed: {
    portalVueVersion: () => {
      return PackageLock.dependencies['portal-vue'].version
    }
  }
}
</script>