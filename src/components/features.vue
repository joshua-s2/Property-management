<template>
  <section class="features-section py-12">
    <v-container fluid class="secondary py-12">
      <v-container>
        <div class="text-h4 primary--text text-center mb-12">
          <h4>{{ sectionTitle }}</h4>
        </div>

        <v-row>
          <v-col
            v-for="feature in features"
            :key="feature.title"
            cols="12"
            sm="6"
            lg="6"
          >
            <feature-card
              :icon="feature.icon"
              :title="feature.title"
              :description="feature.description"
            />
          </v-col> </v-row
      ></v-container>
    </v-container>
  </section>
</template>

<script>
import { featuresData } from "@/data/features";
import FeatureCard from "@/components/FeatureCard.vue";

export default {
  name: "Features",

  components: {
    FeatureCard,
  },

  data() {
    return {
      sectionTitle: "What we have to offer",
      features: featuresData,
    };
  },
};
</script>

<style lang="scss" scoped>
.features-section {
  background-color: var(--v-lightNeutral-base);
}
</style>
