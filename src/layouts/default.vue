<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      right
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
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
      <v-container class="d-flex justify-space-between align-center">
        <h1 class="secondary--text">Josh.</h1>

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
      </v-container>

      <v-btn
        text
        plain
        icon
        @click.stop="drawer = !drawer"
        class="d-flex d-sm-none"
      >
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main class="primary">
      <v-btn icon large @click="switchTheme" class="theme-button">
        <v-icon
          class="animate__animated animate__swing animate__infinite animate__slow"
          >mdi-theme-light-dark</v-icon
        >
      </v-btn>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" temporary fixed>
      <v-list>
        <v-list-item @click.native="right = !right">
          <v-list-item-action>
            <v-icon light> mdi-repeat </v-icon>
          </v-list-item-action>
          <v-list-item-title>Switch drawer (click me)</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
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
      navLinks: [
        {
          linkText: "About",
          to: "/#about",
        },
        {
          linkText: "Projects",
          to: "/#projects",
        },

        {
          linkText: "Contact",
          to: "/#contact",
        },
      ],

      items: [
        {
          icon: "mdi-home",
          title: "Home",
          to: "/",
        },
        {
          icon: "mdi-information-outline",
          title: "About",
          to: "/#about",
        },
        {
          icon: "mdi-flag-checkered",
          title: "Goals",
          to: "/#goal",
        },
        {
          icon: "mdi-human-male-board",
          title: "Mentors",
          to: "/#mentors",
        },
        {
          icon: "mdi-comment-quote-outline",
          title: "Testimonials",
          to: "/#testimonials",
        },
        {
          icon: "mdi-human-greeting-proximity",
          title: "Contact us",
          to: "/#contact",
        },
        {
          icon: "mdi-account-plus-outline",
          title: "Get Started",
          to: "/course",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
    };
  },
  methods: {
    switchTheme() {
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark;
    },
  },
};
</script>
