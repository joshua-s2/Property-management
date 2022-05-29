<template>
  <v-container>
    <div class="text-h4 secondary--text">
      <h4>About Me.</h4>
    </div>
    <v-row align="center">
      <v-col cols="12" md="6">
        <p class="secondary--text py-5 my-2">
          I’m Joshua Odejide, a Frontend engineer with knowledge of a few
          backend technologies. I am vast in various Frontend technologies and
          frameworks. Over the years I have learnt new languages, worked on
          different projects and collaborated with teams.
        </p>
      </v-col>
      <v-col cols="12" md="6">
        <img src="/images/about.svg" />
      </v-col>
    </v-row>
    <div class="text-h5 my-4 secondary--text">
      <h5 class="secondary--text animate__animated animate__fadeInDown">
        How it all Started.
      </h5>
    </div>
    <Timeline />
  </v-container>
</template>
<script>
export default {};
</script>
