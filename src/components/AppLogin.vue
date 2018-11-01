<template>
  <v-container>
    <v-alert
      :value="alert"
      type="warning"
      color="red"
    >
      Please fill in email and password
    </v-alert>
    <v-form @submit.prevent="submit">
      <v-text-field
        v-model="email"
        label="E-mail"
        required
      ></v-text-field>
      <v-text-field
        label="Password"
        v-model="password"
        type="password"
        required
      ></v-text-field>
      <v-btn class="green" type="submit">Submit</v-btn>
    </v-form>
  </v-container>
</template>
<script>
export default {
  data () {
    return {
      email: null,
      password: null,
      alert: false
    }
  },
  methods: {
    submit () {
      if (!this.email && !this.password) {
        this.alert = true
      }
      console.log(`Email is ${this.email} and password is ${this.password}`)
    }
  }
}
</script>
