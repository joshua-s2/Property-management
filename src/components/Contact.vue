<template>
  <v-container>
    <div class="text-h4 secondary--text py-4 my-8">
      <h4>Have a project or idea? Feel free to reach out</h4>
    </div>
    <v-row align="center" class="my-5">
      <v-col cols="12" md="6">
        <v-form
          ref="form"
          v-model="valid"
          lazy-validation
          action="https://formspree.io/f/myyoobgj"
          method="post"
          @submit.prevent="submit"
          id="form"
        >
          <v-text-field
            label="Your Name"
            placeholder="Noel"
            v-model="formData.name"
            :rules="rules.name"
            required
            class="secondary--text"
            name="name"
          />
          <v-text-field
            label="Your Email"
            placeholder="reach@mail.com"
            v-model="formData.email"
            :rules="rules.email"
            required
            class="secondary--text"
            name="email"
          />
          <v-textarea
            v-model="formData.message"
            class="secondary--text"
            name="message"
          />

          <v-btn
            @click.native="submit"
            :disabled="!valid"
            class="secondary--text"
            >Submit</v-btn
          >
        </v-form></v-col
      >
      <v-col cols="12" md="6" class="my-4">
        <v-img src="/images/contact.svg"></v-img>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        email: "",
        message: "",
        name: "",
      },
      valid: false,
      email: "",
      message: "",
      name: "",
      rules: {
        email: [
          (v) => !!v || "E-mail is required",
          (v) => /.+@.+/.test(v) || "E-mail must be valid",
        ],
        name: [(v) => !!v || "Your name is required 🙂"],
      },
    };
  },
  methods: {
    submit() {
      if (this.$refs.form.validate()) {
        form.submit();
        console.log(this.formData);
      }
    },
  },
};
</script>
