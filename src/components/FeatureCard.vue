<template>
  <v-card
    class="feature-card secondary primary--text"
    elevation="2"
    height="100%"
  >
    <v-card-title class="d-flex align-center">
      <v-icon color="primary" class="mr-md-4 mr-2 text-body-1">
        {{ icon }}
      </v-icon>
      {{ title }}
    </v-card-title>
    <v-card-text class="text-body-1">
      {{ description }}
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "FeatureCard",

  props: {
    icon: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.feature-card {
  transition: transform 0.3s ease;

  &:hover {
    transform: translateY(-8px);
  }

  .v-card__title {
    font-size: 1.25rem;
    font-weight: 700;

    @media (max-width: 768px) {
      font-size: 1.1rem;
    }
    @media (max-width: 400px) {
      font-size: 0.8rem;
    }
  }
}
</style> 