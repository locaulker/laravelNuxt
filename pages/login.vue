<template>
  <div class="container col-md-6 mt-5">
    <h2>Login</h2>
    <br>
    <form>
      <div class="form-group">
        <label>Email Address</label>
        <input type="email" class="form-control" placeholder="Enter eMail">
        <small class="form-text text-danger">Show Errors Here</small>
      </div>
      <div class="form-group">
        <label>Password</label>
        <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Password">
        <small class="form-text text-danger">Show Errors Here</small>
      </div>
      <button type="submit" class="btn btn-primary">Login</button>
    </form>
    <br>
    <p>Don't have an Account? <nuxt-link to="/register">Register</nuxt-link></p>
  </div>
</template>
