<template >
  <v-container>
    <iframe
      class="clickup-embed clickup_custom"
      src="https://forms.clickup.com/9012493004/f/8cjzepc-52/JOSJ67O6AJW4IPPX6M"
      onwheel=""
      width="100%"
      height="500%"
      :style="{ background: currentBackground, border: 'none' }"
      sandbox="allow-scripts allow-same-origin allow-forms allow-popups"
      loading="lazy"
    ></iframe>
    <script
      async
      src="https://app-cdn.clickup.com/assets/js/forms-embed/v1.js"
    ></script>
  </v-container>
</template>

<script>
export default {
  computed: {
    currentBackground() {
      return this.$vuetify.theme.dark
        ? "var(--v-secondary-base)"
        : "var(--v-primary-base)";
    },
  },
};
</script>

<style lang="scss" scoped>
.clickup_custom {
  height: 100vh !important;
}
</style>
