<template>
  <v-form v-model="valid">
    <v-col cols="12">
      <v-text-field v-model="password" :rules="passwordRules" label="Password" :counter="10" required></v-text-field>
      <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
      <v-row class="w-250" justify="space-around">
        <v-btn>{{ isLogin ? 'Sign In' : 'Sign Up' }}</v-btn>
        <v-btn @click="switchMode" text>Switch to {{ isLogin? 'Sign Up' : 'Sign In' }}</v-btn>
      </v-row>
    </v-col>
  </v-form>
</template>
<script>
export default {
  data: () => ({
    valid: false,
    password: '',
    passwordRules: [
      v => !!v || 'Password is required',
      v => v.length <= 10 || 'Password must be less than 6 characters',
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+/.test(v) || 'E-mail must be valid',
    ],
    isLogin: true
  }),
  methods: {
    switchMode() {
      this.isLogin = !this.isLogin
    }
  }
}
</script>
<style>
</style>