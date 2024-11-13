<template >
  <v-container>
    <iframe
      class="clickup-embed clickup_custom"
      src="https://forms.clickup.com/9012493004/f/8cjzepc-52/JOSJ67O6AJW4IPPX6M"
      onwheel=""
      width="100%"
      height="500%"
      style="background: #f3e5ff; border: 1px solid #ccc"
    ></iframe>
    <script
      async
      src="https://app-cdn.clickup.com/assets/js/forms-embed/v1.js"
    ></script>
    <!-- <div class="text-h4 secondary--text py-4 my-8 text-center">
      <h4>Does this look like something you'd like to explore?</h4>
    </div>
    <v-row align="center" class="my-5">
      <v-col cols="12" md="6">
        <v-form
          ref="form"
          v-model="valid"
          lazy-validation
          action="https://formspree.io/f/"
          method="POST"
          @submit.prevent="submit"
          id="form"
        >
        
          <v-text-field
            label="First Name"
            v-model="formData.firstName"
            :rules="rules.required"
            required
            class="secondary--text"
            name="firstName"
          />
          <v-text-field
            v-model="formData.lastName"
            label="Last Name"
            :rules="rules.required"
            required
            class="secondary--text"
            name="lastName"
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
          <v-text-field
            v-model="formData.phoneNumber"
            label="Phone Number (Optional)"
            class="white--text"
            name="phoneNumber"
          />
          <v-select
            v-model="formData.userType"
            :items="userTypes"
            label="I am a"
            :rules="rules.required"
            required
            class="secondary--text"
            name="userType"
          />

          <v-btn
            @click.native="submit"
            :disabled="!valid"
            class="secondary--text my-5"
            >Submit</v-btn
          >
        </v-form></v-col
      >
      <v-col cols="12" md="6" class="my-4">
        <v-img src="/images/contact.svg"></v-img>
      </v-col>
    </v-row> -->
  </v-container>
</template>

<!-- <script>
export default {
  data() {
    return {
      formData: {
        firstName: "",
        lastName: "",
        email: "",
        phoneNumber: "",
        userType: "",
      },
      valid: false,
      email: "",
      message: "",
      name: "",
      userTypes: ["Property Owner", "Property Manager", "Tenant"],

      rules: {
        required: [(v) => !!v || "This field is required"],
        email: [
          (v) => !!v || "E-mail is required",
          (v) => /.+@.+/.test(v) || "E-mail must be valid",
        ],
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
</script> -->
<style lang="scss" scoped>
.clickup_custom {
  height: 100vh !important;
}
</style>

<!-- <template>
  <v-container>
    <div class="text-h4 secondary--text py-4 my-8 text-center">
      <h4>Does this look like something you'd like to explore?</h4>
    </div>
    <v-row align="center" class="my-5">
      <v-col cols="12" md="6">
        <v-form
          ref="form"
          v-model="valid"
          lazy-validation
          @submit.prevent="handleSubmit"
        >
          <v-text-field
            label="First Name"
            v-model="formData.firstName"
            :rules="rules.required"
            required
            class="secondary--text"
            name="firstName"
          />
          <v-text-field
            v-model="formData.lastName"
            label="Last Name"
            :rules="rules.required"
            required
            class="secondary--text"
            name="lastName"
          />
          <v-text-field
            v-model="formData.email"
            label="Email"
            :rules="rules.email"
            required
            class="secondary--text"
            name="email"
          />
           <v-text-field
            label="Your Email"
            placeholder="reach@mail.com"
            v-model="formData.email"
            :rules="rules.email"
            required
            class="secondary--text"
            name="email"
          /> -
          <v-text-field
            v-model="formData.phoneNumber"
            label="Phone Number (Optional)"
            class="white--text"
            name="phoneNumber"
          />
          <v-select
            v-model="formData.userType"
            :items="userTypes"
            label="I am a"
            :rules="rules.required"
            required
            class="secondary--text"
            name="userType"
          />

          <v-btn
            type="submit"
            @click.native="submit"
            :disabled="!valid"
            class="secondary--text"
          >
            Join Waitlist
          </v-btn>
          <v-btn type="submit" :disabled="!valid" class="secondary--text">
            Join Waitlist2
          </v-btn> 
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
  name: "Waitlist",
  data() {
    return {
      valid: false,
      formData: {
        firstName: "",
        lastName: "",
        email: "",
        phoneNumber: "",
        userType: "",
      },
      userTypes: ["Property Owner", "Property Manager", "Tenant"],

      email: "",
      message: "",
      name: "",
      rules: {
        required: [(v) => !!v || "This field is required"],
        email: [
          (v) => !!v || "E-mail is required",
          (v) => /.+@.+/.test(v) || "E-mail must be valid",
        ],
      },
    };
  },
  methods: {
    async handleSubmit() {
      if (this.$refs.form.validate()) {
        try {
          const response = await fetch("https://formspree.io/f/myyoobgj", {
            method: "POST",
            headers: {
              "Content-Type": "application/json",
            },
            body: JSON.stringify(this.formData),
          });

          if (response.ok) {
            // Reset form after successful submission
            this.$refs.form.reset();
            // You might want to show a success message here
          }
        } catch (error) {
          console.error("Submission error:", error);
          // You might want to show an error message here
        }
      }
    },
  },
};
</script>
 -->