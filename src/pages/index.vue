<template>
  <div>
    <Heading />
    <!-- <About class="my-10" id="about" /> -->
    <Features class="my-10" id="features" />
    <Waitlist id="waitlist" />
  </div>
</template>

<script>
import Heading from "../components/Heading.vue";
import Features from "../components/features.vue";
import Waitlist from "../components/Waitlist.vue";

export default {
  name: "IndexPage",
  components: {
    Heading,
    Features,
    Waitlist,
  },
};
</script>
