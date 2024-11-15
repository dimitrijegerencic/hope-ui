<script setup>
import PrimaryButton from '@/components/buttons/PrimaryButton.vue'
import { ref } from 'vue'
import router from '@/router/index.js'

const firstName = ref('')
const lastName = ref('')

const emailAddress = ref('')
const phoneNumber = ref('')

const password = ref('')
const confirmPassword = ref('')

const agreements = ref(false)

const signUp = () => {
  const user = {
    first_name: firstName.value,
    last_name: lastName.value,
    email_address: emailAddress.value,
    phone_number: phoneNumber.value,
    password: password.value,
    confirm_password: confirmPassword.value,
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
      <v-col class="left-column">
        <img src="@/assets/images/login-background.png" alt="Background" />
      </v-col>
      <v-col class="right-column d-flex align-center">
        <v-container class="form-container">
          <img src="@/assets/images/logo.png" alt="Logo" />
          <div class="text-center mt-5">
            <h1>Sign Up</h1>
            <p class="create-account-text mt-3">Create your Hope UI account</p>
          </div>

          <v-row class="mt-5">
            <v-col class="mt-0">
              <v-label>First Name</v-label>
              <v-text-field
                v-model="firstName"
                color="primary"
                variant="outlined"
                class="mt-2"
              ></v-text-field>
            </v-col>
            <v-col>
              <v-label>Last Name</v-label>
              <v-text-field
                v-model="lastName"
                color="primary"
                variant="outlined"
                class="mt-2"
              ></v-text-field>
            </v-col>
          </v-row>

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
            <v-col>
              <v-label>Phone No.</v-label>
              <v-text-field
                v-model="phoneNumber"
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
            <v-col>
              <v-label>Confirm password</v-label>
              <v-text-field
                v-model="confirmPassword"
                color="primary"
                variant="outlined"
                class="mt-2"
                type="password"
              ></v-text-field>
            </v-col>
          </v-row>
          <div class="d-flex justify-center">
            <v-checkbox
              v-model="agreements"
              color="primary"
              label="I agree with the terms of use"
              hide-details
            ></v-checkbox>
          </div>
          <div class="text-center mt-3">
            <PrimaryButton label="Sign up" width="188" height="44" @click="signUp" />
            <p class="mt-7">or sign up with other accounts?</p>
            <img src="@/assets/images/social-links.png" alt="Social links" class="mt-6" />
            <p class="mt-2">
              Already have an account? <RouterLink to="/login">Sign in</RouterLink>
            </p>
          </div>
        </v-container>
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
      padding-left: 150px;
      padding-right: 150px;

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
