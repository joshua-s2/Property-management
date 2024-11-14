<template>
  <section class="hero-section">
    <v-container>
      <v-row align="center" justify="center">
        <v-col cols="12" md="10" lg="12">
          <div class="text-center">
            <!-- Main Heading -->
            <h1
              class="secondary--text header__title text-h3 text-sm-h2 text-md-h1 animate__animated animate__tada"
            >
              For Owners, Managers, and Tenants:
              <br class="d-none d-md-block" />
              One App for Effortless Property
              <br class="d-none d-md-block" />
              Management
            </h1>

            <!-- Subtitle -->
            <p class="secondary--text subtitle mt-6 mb-8 text-subtitle-1">
              Get full control over listings, payments, and tenant communication
              with an app that simplifies it all.
            </p>

            <!-- CTA Button -->
            <v-btn
              href="#waitlist"
              color="secondary"
              class="primary--text px-6"
              height="48"
              :ripple="false"
              @click="trackCTAClick"
            >
              <span class="mr-2">Join the waitlist</span>
              <v-icon>mdi-arrow-down</v-icon>
            </v-btn>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>

<script>
export default {
  name: "HeroSection",

  methods: {
    trackCTAClick() {
      // Add analytics tracking here if needed
      console.log("CTA clicked");
    },
  },
};
</script>

<style lang="scss" scoped>
.hero-section {
  padding: 4rem 0;

  .header__title {
    margin-bottom: 1rem;
    font-weight: 800;
  }

  .subtitle {
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
    font-weight: 500;
  }
}
</style>

