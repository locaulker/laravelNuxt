<template>
  <div class="container col-md-6 mt-5">
    <h2>Register</h2>
    <br>
    <form @submit.prevent="registerUser">
      <div class="form-group">
        <label>Full Name</label>
        <input v-model.trim="form.name" type="text" class="form-control" placeholder="Enter Your Name" autofocus>
        <small class="form-text text-danger">Show Errors Here</small>
      </div>

      <div class="form-group">
        <label>Email Address</label>
        <input v-model.trim="form.email" type="email" class="form-control" placeholder="Enter eMail">
        <small class="form-text text-danger">Show Errors Here</small>
      </div>
      <div class="form-group">
        <label>Password</label>
        <input v-model.trim="form.password" type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        <small class="form-text text-danger">Show Errors Here</small>
      </div>

      <button type="submit" class="btn btn-primary">Register</button>
    </form>
    <br>
    <p>Already have an Account? <nuxt-link to="/login">Login</nuxt-link></p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        password: ''
      }
    }
  },
  methods: {
    async registerUser() {
      await this.$axios.$post('register', this.form)
      await this.$auth.loginWith('local', {
        data: {
          email: this.form.email,
          password: this.form.password
        }
      })
      // redirect user
      this.$router.push('/')
    }
  }
}
</script>