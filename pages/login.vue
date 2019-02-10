<template>
  <div class="container col-md-6 mt-5">
    <h2>Login</h2>
    <br>
    <form @submit.prevent="loginUser">
      <div class="form-group">
        <label>Email Address</label>
        <input v-model.trim="form.email" type="email" class="form-control" placeholder="Enter eMail" autofocus>
        <small class="form-text text-danger">Show Errors Here</small>
      </div>
      <div class="form-group">
        <label>Password</label>
        <input v-model.trim="form.password" type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        <small class="form-text text-danger">Show Errors Here</small>
      </div>
      <button type="submit" class="btn btn-primary">Login</button>
    </form>
    <br>
    <p>Don't have an Account? <nuxt-link to="/register">Register</nuxt-link></p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    async loginUser() {
      await this.$auth.loginWith("local", {
        data: this.form
      })   
      // redirect after login to homepage
      this.$router.push('/')
    }
  }
}
</script>