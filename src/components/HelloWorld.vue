<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-md-5">
        <div class="card">
          <div class="card-body">
            <div class="text-center">
              <img src="logo.png" alt="Logo" class="mb-4">
            </div>
            <h4 class="text-center mb-4">Create an Account</h4>
            <form @submit.prevent="register">
              <div class="form-group">
                <input type="text" class="form-control input-lg" v-model="name" placeholder="Full Name">
              </div>
              <div class="form-group">
                <input type="text" class="form-control input-lg" v-model="email" placeholder="Email">
              </div>
              <div class="form-group">
                <input type="password" class="form-control input-lg" v-model="password" placeholder="Password">
              </div>
              <button type="submit" class="btn btn-primary btn-lg btn-block">Sign Up</button>
            </form>
            <hr>
            <div class="text-center">
              <p>By signing up, you agree to our Terms, Data Policy, and Cookies Policy.</p>
              <p>Already have an account? <a href="#" class="text-primary">Log In</a></p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      password: ''
    };
  },
  methods: {
    register() {
      // Aquí puedes realizar las acciones necesarias para registrar al usuario
      console.log('Name:', this.name);
      console.log('Email:', this.email);
      console.log('Password:', this.password);
    }
  }
};
</script>

<style scoped>
.card {
  border: none;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.btn-primary {
  background-color: #1877f2;
  border-color: #1877f2;
}

.btn-primary:hover {
  background-color: #166fe5;
  border-color: #166fe5;
}

.text-primary {
  color: #1877f2;
}

.text-primary:hover {
  text-decoration: underline;
}

input[type="text"],
input[type="password"] {
  border: 1px solid #ddd;
  border-radius: 5px;
  padding: 10px;
}

input.input-lg {
  font-size: 18px;
  height: 50px;
}

.container {
  background-color: #f0f2f5;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
