<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      right
      class="primary secondary--text"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
          class="secondary--text primary"
        >
          <v-list-item-content class="secondary--text">
            {{ item.linkText }}
            <v-list-item-title class="secondary--text">{{
              item.title
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar
      class="primary"
      :clipped-left="clipped"
      fixed
      app
      elevate-on-scroll
    >
      <v-container class="d-flex justify-end align-center">
        <div class="d-flex align-center">
          <div :key="links.id" v-for="links in navLinks">
            <a
              text
              :href="links.to"
              class="nav__link d-none d-sm-flex mx-3 secondary--text"
            >
              {{ links.linkText }}
            </a>
          </div>
        </div>
        <v-btn
   color="secondary"
          class="primary--text d-none d-sm-flex"
          :ripple="true"
          href="#waitlist"
        >
          Join the Waitlist
        </v-btn>
      </v-container>

      <v-btn
        text
        plain
        icon
        @click.stop="drawer = !drawer"
        class="d-flex d-sm-none secondary primary--text"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main class="primary">
      <v-btn
        icon
        large
        @click="switchTheme"
        class="theme-button secondary"
        v-show="showThemeButton"
        :class="{ 'fade-out': !showThemeButton }"
      >
        <v-icon
          class="animate__animated animate__swing animate__infinite animate__slow"
          >mdi-theme-light-dark</v-icon
        >
      </v-btn>
      <!-- <v-container> -->
      <Nuxt />
      <!-- </v-container> -->
    </v-main>
    <!-- <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer> -->
    <v-footer :absolute="!fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: false,
      drawer: false,
      btnText: false,
      fixed: false,
      showThemeButton: false,
      scrollTimeout: null,
      navLinks: [
        {
          linkText: "Features",
          to: "/#features",
        },
      ],

      items: [
        {
          linkText: "Features",
          to: "/#features",
        },

        {
          linkText: "Join the Waitlist",
          to: "#join-waitlist",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  beforeDestroy() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      this.showThemeButton = true;

      // Clear any existing timeout
      if (this.scrollTimeout) {
        clearTimeout(this.scrollTimeout);
      }

      // Hide button after 4 second of no scrolling
      this.scrollTimeout = setTimeout(() => {
        this.showThemeButton = false;
      }, 4000);
    },
    switchTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    },
  },
};
</script>
