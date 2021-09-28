<template>
  <v-container>
    <v-layout style="height: 100vh" row wrap justify-center align-center>
      <v-flex md9>
        <v-card class="pa-14">
          <h4>Create new account</h4>
          <v-form lazy-validation ref="form" v-model="valid" class="mt-8">
            <v-text-field
              v-model="form.email"
              placeholder="example@mail.com"
              :rules="emailRules"
              required
              label="Email Address"
            ></v-text-field>
            <v-text-field
              label="Password"
              v-model="form.password"
              type="password"
              required
              :rules="[(v) => !!v || 'Password field is required']"
            >
            </v-text-field>

            <v-text-field
              label="Create username"
              v-model="form.username"
              placeholder="chrissteve"
              required
              :rules="[(v) => !!v || 'Password field is required']"
            >
            </v-text-field>
            <vue-tel-input-vuetify
              v-model="form.phone"
              label="Enter your phone number"
              required
            ></vue-tel-input-vuetify>

            <p class="small my-10">Got referral code?</p>

            <v-btn class="register-btn" x-large text block>sign up</v-btn>

            <p class="sm mt-9 text-center">Have an account? <nuxt-link class="font-weight-bold" to="/login">Sign in to explore</nuxt-link></p>
          </v-form>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import VueTelInputVuetify from 'vue-tel-input-vuetify/lib/vue-tel-input-vuetify'
export default {
  layout: 'auth',
  components: {
    VueTelInputVuetify,
  },
  data() {
    return {
      valid: true,
      form: {},
      emailRules: [
        (v) => !!v || 'Please enter your email',
        (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
    }
  },
}
</script>
<style lang="scss" scoped>
h4 {
  text-align: left;
  letter-spacing: 0px;
  color: #000000;
  font: normal normal bold 25px/29px Rubik;

}
p.small {
  text-align: left;
  font: normal normal bold 14px/16px Rubik;

  letter-spacing: 0px;
  color: #2e1963;
}
p.sm {
  font: normal normal normal 14px/16px Rubik;
  letter-spacing: 0px;
}
.register-btn {
  background: transparent linear-gradient(90deg, #432b7b 0%, #6a4bbc 100%) 0% 0%
    no-repeat padding-box;
  border-radius: 6px;
  font: normal normal bold 12px/14px Basis Grotesque Pro;
  letter-spacing: 0px;
  color: #ffffff;
  text-transform: uppercase;
}
</style>
