<template>
  <div class="hello">
    <h1>Register</h1>

    <input
      type="email"
      name="email"
      v-model="email"
      placeholder="email" />

    <input
      type="password"
      name="password"
      v-model="password"
      placeholder="password" />

    <button
      @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/authentication_service'
export default {
  name: 'hello',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  watch: {
    email (value) {
      console.log('email has changed', value)
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style scoped>

</style>
