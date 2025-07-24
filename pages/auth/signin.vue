<template>
  <div class="d-flex align-center justify-center signin-bg">
    <v-card max-width="460" class="pa-6 elevation-10 rounded-xl" color="#1e1e1e">
      <v-card-text>
        <!-- Header -->
        <div class="text-center mb-6">
          <h2 class="text-h5 font-weight-bold mb-2">🔐 Secure Login</h2>
          <p class="text-body-2 text--secondary">Access your QR tools and dashboard</p>
        </div>

        <!-- Sign-in Form -->
        <v-form>
          <v-text-field
            v-model="name"
            label="Username"
            outlined
            dense
            rounded
            prepend-inner-icon="mdi-account"
            class="mb-4"
            color="primary"
          />

          <v-text-field
            v-model="email"
            label="Password"
            type="password"
            outlined
            dense
            rounded
            prepend-inner-icon="mdi-lock"
            class="mb-4"
            color="primary"
          />

          <v-btn
            color="primary"
            block
            large
            class="mb-4 text-none"
            rounded
          >
            Sign In
          </v-btn>

          <div class="text-center my-3 grey--text text-caption">— or continue with —</div>

          <!-- Google Sign-In -->
          <v-btn
            block
            outlined
            rounded
            color="white"
            elevation="2"
            class="google-btn text--dark"
            @click="signinWithGoogle"
          >
            <v-icon left color="red darken-1">mdi-google</v-icon>
            Sign in with Google
          </v-btn>
        </v-form>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  layout: "auth",
  middleware: "guest",
  data() {
    return {
      name: '',
      email: ''
    }
  },
  methods: {
    signinWithGoogle() {
      this.$auth.loginWith('google')
    }
  }
}
</script>

<style scoped>
.signin-bg {
  min-height: 100vh;
  background: linear-gradient(to bottom right, #121212, #1f1f1f);
  padding: 20px;
}
.google-btn {
  font-weight: 500;
  text-transform: none;
}
</style>
