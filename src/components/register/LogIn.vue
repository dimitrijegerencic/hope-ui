<script setup>
import PrimaryButton from '@/components/buttons/PrimaryButton.vue'
import { ref } from 'vue'
import router from '@/router/index.js'

const emailAddress = ref('')
const password = ref('')

const logIn = () => {
  const user = {
    email_address: emailAddress.value,
    password: password.value,
  }

  console.log('User', user)

  setTimeout(() => {
    router.push('/dashboard')
  }, 2000)
}
</script>

<template>
  <div class="main-container">
    <v-row>
      <v-col class="right-column d-flex align-center">
        <v-container class="form-container">
          <img src="@/assets/images/logo.png" alt="Logo" />
          <div class="text-center mt-5">
            <h1>Sign In</h1>
            <p class="create-account-text mt-3">Sign in to stay connected.</p>
          </div>

          <v-row class="mt-0">
            <v-col>
              <v-label>Email</v-label>
              <v-text-field
                v-model="emailAddress"
                color="primary"
                variant="outlined"
                class="mt-2"
              ></v-text-field>
            </v-col>
          </v-row>

          <v-row class="mt-0">
            <v-col>
              <v-label>Password</v-label>
              <v-text-field
                v-model="password"
                color="primary"
                variant="outlined"
                class="mt-2"
                type="password"
              ></v-text-field>
            </v-col>
          </v-row>
          <v-row class="mt-0">
            <v-col> Remember me </v-col>
            <v-col class="d-flex justify-end">
              <RouterLink to="/reset">Forgot your password?</RouterLink>
            </v-col>
          </v-row>

          <div class="text-center mt-7">
            <PrimaryButton label="Sign in" width="188" height="44" @click="logIn" />
            <p class="mt-7">or sign up with other accounts?</p>
            <img src="@/assets/images/social-links.png" alt="Social links" class="mt-6" />
            <p class="mt-2">
              Don't have an account? <RouterLink to="/">Click here to sign up.</RouterLink>
            </p>
          </div>
        </v-container>
      </v-col>
      <v-col class="left-column">
        <img src="@/assets/images/register-background.png" alt="Background" />
      </v-col>
    </v-row>
  </div>
</template>

<style scoped>
.main-container {
  height: 100vh;

  .left-column img {
    width: 100%;
    height: 100vh;
  }

  .right-column {
    .form-container {
      padding-left: 250px;
      padding-right: 250px;

      h1 {
        font-size: 33px;
      }

      .create-account-text {
        font-size: 16px;
        color: #8a92a6;
      }
    }

    a {
      color: #3a57e8;
      text-decoration: none;
    }
  }
}
</style>
