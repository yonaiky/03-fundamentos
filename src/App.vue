<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-md-5">
        <div class="card">
          <div class="card-body">
            <div class="text-center">
              <img src="logo.png" alt="Logo" class="mb-4">
            </div>
            <h4 class="text-center mb-4">Log in to your account</h4>
            <form v-if="!showSignUpForm" @submit.prevent="login">
              <div class="form-group">
                <input type="text" class="form-control input-lg" v-model="username" placeholder="Email or Phone">
              </div>
              <div class="form-group">
                <input type="password" class="form-control input-lg" v-model="password" placeholder="Password">
              </div>
              <button type="submit" class="btn btn-primary btn-lg btn-block">Log In</button>
              <div class="text-center mt-3">
                <a href="#" class="text-primary" @click="showSignUp()">Create New Account</a>
              </div>
            </form>
            <form v-else @submit.prevent="register">
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
              <div class="text-center mt-3">
                <a href="#" class="text-primary" @click="showSignUp()">Already have an account? Log In</a>
              </div>
            </form>
            <div class="alert" v-if="showAlert" :class="alertClass">
              {{ alertMessage }}
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
      showSignUpForm: false,
      username: '',
      password: '',
      name: '',
      email: '',
      showAlert: false,
      alertMessage: '',
      alertClass: '',
    };
  },
  methods: {
    login() {
      // Simulación de verificación de credenciales
      if (this.username === 'example@example.com' && this.password === 'password123') {
        this.showAlert = true;
        this.alertMessage = 'Inicio de sesión exitoso';
        this.alertClass = 'alert-success';
        // Redirigir al usuario a la página de dashboard
        setTimeout(() => {
          this.$router.push('/dashboard');
        }, 1000);
      } else {
        this.showAlert = true;
        this.alertMessage = 'Credenciales inválidas';
        this.alertClass = 'alert-danger';
      }
    },
    register() {
      // Simulación de registro de usuario
      // Aquí puedes realizar acciones como enviar los datos de registro al servidor
      this.showAlert = true;
      this.alertMessage = 'Registro exitoso';
      this.alertClass = 'alert-success';
    },
    showSignUp() {
      this.showSignUpForm = !this.showSignUpForm;
    },
  },
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

.alert {
  margin-top: 20px;
  padding: 10px;
  border-radius: 5px;
  color: #fff;
  font-weight: bold;
}

.alert-success {
  background-color: #4caf50;
}

.alert-danger {
  background-color: #f44336;
}


.container {
  background-image: url('./images/JjUjya.jpg');
  background-size: cover;
  background-position: center;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
