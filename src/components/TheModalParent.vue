<template>
  <div>
    <h1>portal-vue {{ portalVueVersion }}</h1>
    <p>
      Repo for this example:<br>
      <a :href="repoUrl">{{ repoUrl }}</a>
    </p>

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
    },
    repoBranchName: function () {
      return this.portalVueVersion === '1.3.0'
        ? 'master'
        : 'portal-vue-' + this.portalVueVersion
    },
    repoUrl: function () {
      return this.$options.repoBaseUrl + this.repoBranchName
    }
  },
  repoBaseUrl: 'https://github.com/tinymachine/portal-vue-transition-examples/tree/',
}
</script>